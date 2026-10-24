# Firestorm Integration — Backend Requirements
**Project:** Mavric Mens Health Checkout  
**Date:** July 25, 2026  
**Prepared for:** Backend Development Team  

---

## Overview

The Mavric Health checkout (React frontend) is being integrated with the **Firestorm® MLM platform** by Trinity Software. This document outlines everything the backend team needs to implement to complete this integration.

The Firestorm system lives at:
> **https://mavrictrailblazer.com**

Test Dealer ID: `43096`  
Test Dealer URL alias: `MAVRICHEALTH`

---

## Current Architecture

```
User (Browser)
    │
    ▼
React Checkout App  ──────────►  WLMD Backend API
    │                           (panel.whitelabelmd.com/mavricmenshealth/api/)
    │
    ▼
[NEW] Firestorm API
    (mavrictrailblazer.com)
```

---

## Blocker — IP Whitelist (Must Do First)

> **Firestorm Web Services will reject all API calls until your server's public IP is whitelisted by Trinity Software.**

**Action:** Send your server's **public outbound IP address** to:
- Email: `support@trinitysoft.net`
- Subject: `IP Whitelist Request — Mavric Health Integration`

Nothing in Tasks 2, 3, or 4 below can be built or tested until this is done.

---

## Task 1 — Store Firestorm Dealer ID on Orders (No Whitelist Needed)

### What changed on the frontend

The checkout now reads a `?ref=` URL parameter (e.g. `https://checkout.mavricmenshealth.com/?ref=MAVRICHEALTH`) and automatically calls the Firestorm lookup API:

```
GET https://mavrictrailblazer.com/MemberToolsDotNet/Utils/GetReplicatedDetails.aspx?DealerURL=MAVRICHEALTH
```

Response (pipe-delimited):
```
Success|43096|Mavric Health|Corporate Position|Mavric Health Corporate Position|||||GOLD|0|GOLD|...|MAVRICHEALTH|
```

The frontend parses `DealerID = 43096` and appends it to every order submission as:
```
firestorm_dealer_id = 43096
```

### What backend needs to do

1. **Add column to orders table:**
```sql
ALTER TABLE orders ADD COLUMN firestorm_dealer_id VARCHAR(20) NULL;
```

2. **Accept and store `firestorm_dealer_id`** in the `createOrder_test` endpoint — save it alongside the order record.

3. **Return it in the order response** so it can be used for downstream Firestorm calls.

---

## Task 2 — Submit Orders to Firestorm Web Services (Requires IP Whitelist)

After a successful order is saved in the WLMD database, a secondary call must be made to Firestorm to record the order in their system so commissions and genealogy tracking work correctly.

### Firestorm Web Services Endpoint

```
POST https://mavrictrailblazer.com/MemberToolsDotNet/WebServices/FirestormWS.asmx
```

Authentication: IP-based (no API key — your server IP must be whitelisted).

### Method: `FirestormOrderWS.SaveOrderExtended`

| Firestorm Field | Source |
|---|---|
| `referringDealerId` | `firestorm_dealer_id` from order record |
| `firstName` | `first_name` from order |
| `lastName` | `last_name` from order |
| `email` | `email` from order |
| `address1` | `address` from order |
| `city` | `city_name` from order |
| `state` | `state_name` (2-letter code) |
| `zip` | `zip_code` from order |
| `country` | `US` (hardcoded) |
| `phone` | `phone` from order |
| `productID` | Firestorm product SKU (see Task 5 below) |
| `productQty` | `1` per line item |
| `productPrice` | `product_price` from order |
| `promoCode` | `promo_codes` (coupon code if applied) |
| `creditCardNumber` | Card number (PCI caution — see note) |
| `cvv` | CVV |
| `expMonth` | `ex_month` |
| `expYear` | `ex_year` |
| `cardType` | `visa` / `mastercard` / `discover` / `american express` |

> **PCI Note:** If you are not storing raw card data (which you should not be), coordinate with Trinity on how Firestorm handles payment — they may accept a gateway transaction token instead of raw card details.

### Success Response

Firestorm returns an XML response. On success, extract and store `OrderID` (Firestorm's internal order ID) back in your DB.

---

## Task 3 — Enroll New Members in Firestorm (Requires IP Whitelist)

When a brand new customer completes their first purchase, they need to be **enrolled as a member** in Firestorm so they appear in the distributor's downline and can access a backoffice.

### Method: `FirestormEnrollmentWS.EnrollMemberExtended`

| Field | Value |
|---|---|
| `referringDealerId` | `firestorm_dealer_id` from order |
| `enrollmentCode` | `DEALER` |
| `firstName` | from order |
| `lastName` | from order |
| `email` | from order |
| `address1` | from order |
| `city` | from order |
| `state` | from order |
| `zip` | from order |
| `phone` | from order |
| `dealershipType` | TBD — confirm with Mavric Health (membership tier) |
| `enrollmentProductID` | Firestorm enrollment SKU — confirm with Trinity |
| `enrollmentProductPrice` | Enrollment product price |

### Logic

```
On order success:
  IF customer email does NOT exist in Firestorm:
    → Call EnrollMemberExtended
    → Store returned Firestorm DealerID in your DB against the user record
  ELSE:
    → Skip enrollment, just record the order (Task 2)
```

You can check if a member exists using:
**`FirestormDealerWS.GetDealerDetail`** — pass email, returns dealer info or "not found".

---

## Task 4 — Seamless Login / SSO After Purchase (Requires Trinity Keys)

After a successful purchase, the thank-you page will have a **"Go to your Firestorm Backoffice"** button. Clicking it should auto-log the user in without entering credentials.

### How it works

1. Backend receives a request with the user's `firestorm_dealer_id`
2. Backend builds this JSON payload:
```json
{
  "fsDealerID": 43096,
  "externalSystemID": "user@email.com",
  "createdAt": "2026-07-25T16:00:00+05:30",
  "secretKey": "YOUR_SECRET_KEY_FROM_TRINITY"
}
```
3. Encrypt the payload with **RSA OAEP SHA-1** using Trinity's Public RSA Key
4. Base64 encode → URL encode the result
5. Return the final redirect URL to the frontend:
```
https://mavrictrailblazer.com/MemberToolsDotNet/Login/FirestormSSO.aspx?tok=<ENCODED_TOKEN>
```
6. Frontend redirects the user to this URL

### Required from Trinity Software

Before this can be built, email `support@trinitysoft.net` requesting:
- **Secret Key** — identifies your integration, treat like a password
- **Public RSA Key (XML format)** — used to encrypt the login token

> **Security:** The Secret Key must be stored server-side only, never exposed to the browser or frontend.

---

## Task 5 — Product SKU Mapping (Coordination Required)

Each product in your WLMD system needs a corresponding **Firestorm SKU** for orders and enrollment to work.

### What you need

Ask the Mavric Health team to provide a product spreadsheet with the following columns:

| Column | Description |
|---|---|
| `wlmd_product_id` | Your internal product ID |
| `firestorm_product_sku` | The SKU in Firestorm's system (must be unique) |
| `product_name` | Display name |
| `retail_price` | Customer-facing price |
| `wholesale_price` | Member price |
| `psv` | Personal Sales Volume |
| `commissionable_volume` | CV for commission calc |

Store this mapping in a `product_firestorm_map` table and use it when building Firestorm API calls.

---

## Task 6 — Coupon API Update (Already Done on Frontend)

The coupon validation endpoint has been updated on the frontend.

**New endpoint:**
```
POST https://panel.whitelabelmd.com/wlmdbackend/api/check_coupons_v3
```

**Payload sent:**
```json
{
  "site_id": 352,
  "promo_codes": "COUPON_CODE",
  "product_id": "PRODUCT_ID",
  "email": "user@email.com"
}
```

**Expected response:**
```json
{
  "status": 1,
  "message": "Promo code applied successfully.",
  "data": {
    "code": "TESTCHECKOUT",
    "discount_amount": "188.10"
  }
}
```

**Backend must ensure** this endpoint is live and returns the above format. The frontend reads `data.code` and `data.discount_amount`.

---

## Implementation Order

| Priority | Task | Blocker | Estimated Effort |
|---|---|---|---|
| 1 | Send IP to Trinity for whitelist | None — do immediately | 5 min |
| 2 | Store `firestorm_dealer_id` on orders (Task 1) | None | ~2 hrs |
| 3 | Ensure coupon v3 API works (Task 6) | None | ~1 hr |
| 4 | Product SKU mapping table (Task 5) | Need spreadsheet from Mavric Health | ~2 hrs |
| 5 | Submit orders to Firestorm (Task 2) | IP whitelist | ~1 day |
| 6 | Enroll new members in Firestorm (Task 3) | IP whitelist + SKU mapping | ~1 day |
| 7 | Seamless login SSO (Task 4) | Secret Key + RSA Key from Trinity | ~4 hrs |

---

## Test URLs

| Purpose | URL |
|---|---|
| Dealer lookup | `https://mavrictrailblazer.com/MemberToolsDotNet/Utils/GetReplicatedDetails.aspx?DealerURL=MAVRICHEALTH` |
| Enrollment form (test) | `https://mavrictrailblazer.com/MemberToolsDotNet/EnrollmentV4/StartPublicEnrollment.aspx?EnrollmentCode=DEALER&referringDealerId=43096` |
| Dealer profile picture | `https://mavrictrailblazer.com/MemberToolsDotNet/Utils/ReturnDealerImage.aspx?DealerID=43096` |
| Checkout with ref param | `http://localhost:3000/?ref=MAVRICHEALTH` |

---

## Contacts

| Contact | Purpose |
|---|---|
| `support@trinitysoft.net` | IP whitelist + SSO keys request |
| Bryce (Mavric Health) | Domain, SSL, product spreadsheet |

---

*Document generated from codebase analysis of `mavricmenshealth_checkout`. Frontend changes already applied in `Checkout2.js`.*
