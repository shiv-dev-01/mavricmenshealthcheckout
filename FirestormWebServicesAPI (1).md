# Firestorm® Web Services 

# API 

Copyright 2014-2023 Trinity Software Incorporated 

**Version 2.2.33** 

Firestorm® Web Services API | Version 2.2.33 

### Table of Contents 

|Revision History ........................................................................................................................................................... 7|
|---|
|Introduction ................................................................................................................................................................. 9|
|Notational Conventions Used in this Document ....................................................................................................... 10|
|System Architecture and Requirements .................................................................................................................... 11|
|Web Services Summary and WSDL ............................................................................................................................ 12|
|Obtaining Access to the Web Services....................................................................................................................... 18|
|Logging ....................................................................................................................................................................... 19|
|Country Specific Restrictions ..................................................................................................................................... 20|
|Field Level Restrictions .............................................................................................................................................. 21|
|General Rules ............................................................................................................................................................. 22|
|**Return Values**............................................................................................................................................................ 23|
|Errors and Internal Logs ............................................................................................................................................. 25|
|Firestorm Coupon Service .......................................................................................................................................... 26|
|FirestormCouponWS.CreateShoppingCartCoupon ............................................................................................... 27|
|Firestorm Dealer Web Service ................................................................................................................................... 29|
|FirestormDealerWS.GetDealerDetail ..................................................................................................................... 30|
|FirestormDealerWS.GetDealerDetailExtended ..................................................................................................... 33|
|FirestormDealerWS.GetDealerDetailExtended2 ................................................................................................... 36|
|FirestormDealerWS.DealerSearch ......................................................................................................................... 39|
|FirestormDealerWS.SaveDealerDetail ................................................................................................................... 42|
|FirestormDealerWS.GetDealerListByDealerIDRange ............................................................................................. 44|
|FirestormDealerWS.UpdateTaxpayerNumber ....................................................................................................... 45|
|FirestormDealerWS.DealerLocator ........................................................................................................................ 46|
|FirestormDealerWS.GetUnpaidCommissions ........................................................................................................ 48|
|FirestormDealerWS.GetDealerCommissionsByDate ............................................................................................. 49|
|FirestormDealerWS.SaveDealerOption ................................................................................................................. 51|
|FirestormDealerWS.GetDealerOptions ................................................................................................................. 53|
|FirestormDealerWS.GetCustomerListByDealerID ................................................................................................. 55|
|FirestormDealerWS.ActivateDealer ....................................................................................................................... 57|
|FirestormDealerWS.DeActivateDealer .................................................................................................................. 59|
|FirestormDealerWS.GetRankWidgetData ............................................................................................................. 61|
|FirestormDealerWS.GetRankWidgetRankPath ...................................................................................................... 68|
|C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c .P a g e2 | 317|



Firestorm® Web Services API | Version 2.2.33 

|FirestormDealerWS.CreditProductPoints .............................................................................................................. 73|
|---|
|FirestormDealerWS.DebitProductPoints ............................................................................................................... 74|
|FirestormDealerWS.GetDealerProductPointBalance ............................................................................................ 75|
|FirestormDealerWS.GetDealerKPIData ................................................................................................................. 76|
|Firestorm Dealership Web Service ............................................................................................................................ 77|
|FirestormDealershipWS.GetDealershipTypes ....................................................................................................... 78|
|FirestormDealershipWS.GetDealershipsByDealer ................................................................................................. 80|
|FirestormDealershipWS.ActivateDealership ......................................................................................................... 83|
|FirestormDealershipWS.DeActivateDealership ..................................................................................................... 85|
|FirestormEnrollmentWS ............................................................................................................................................ 87|
|FirestormEnrollmentWS.EnrollMember ................................................................................................................ 88|
|FirestormEnrollmentWS.EnrollMemberExtended ................................................................................................. 92|
|FirestormEnrollmentWS.EnrollMemberAsOrphan ................................................................................................ 97|
|FirestormEnrollmentWS.EnrollCustomer ............................................................................................................ 101|
|FirestormEnrollmentWS.EnrollMemberInHoldingTank....................................................................................... 104|
|FirestormGenealogyWS ........................................................................................................................................... 109|
|FirestormGenealogyWS.GetDownlineByDealerID ............................................................................................... 110|
|FirestormInventoryWS ............................................................................................................................................. 112|
|FirestormInventoryWS.AdjustInventory .............................................................................................................. 113|
|FirestormInventoryWS.GetCatalogueList ............................................................................................................ 115|
|FirestormInventoryWS.GetCatalogueContents ................................................................................................... 117|
|FirestormInventoryWS.GetCatalogueContentsV4Cart ........................................................................................ 121|
|FirestormInventoryWS. GetVariationPathsForParentProduct ............................................................................ 127|
|FirestormInventoryWS.GetProductItemDetail .................................................................................................... 129|
|FirestormInventoryWS.GetProductItems ............................................................................................................ 131|
|FirestormInventoryWS.GetCurrentInventoryCounts .......................................................................................... 133|
|FirestormInventoryWS.GetInventoryCountsByProductID ................................................................................... 134|
|FirestormInventoryWS.GetShoppingCartGroupCodeDetail ................................................................................ 136|
|FirestormInventoryWS.GetEnrollmentSpecialsByDealershipType ...................................................................... 138|
|FirestormInventoryWS.SaveProduct ................................................................................................................... 139|
|FirestormInventoryWS.SaveCatalogueProductDetail .......................................................................................... 144|
|FirestormInventoryWS.GetProductList................................................................................................................ 148|
|FirestormInventoryWS.GetInventoryGroupCodes .............................................................................................. 150|
|C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c .P a g e3 | 317|



Firestorm® Web Services API | Version 2.2.33 

|FirestormOrderWS ................................................................................................................................................... 151|
|---|
|FirestormOrderWS.SaveOrder ............................................................................................................................. 152|
|FirestormOrderWS.SaveOrderExtended ............................................................................................................. 157|
|FirestormOrderWS.SaveOrderExtendedWithOptions ......................................................................................... 163|
|FirestormOrderWS.ValidatePurchase .................................................................................................................. 171|
|FirestormOrderWS.GetFirestormTaxRate ........................................................................................................... 173|
|FirestormOrderWS.GetOrders ............................................................................................................................. 174|
|FirestormOrderWS.GetOrdersByDealerID ........................................................................................................... 180|
|FirestormOrderWS.GetOrderDetail ..................................................................................................................... 186|
|FirestormOrderWS.PayForOrderWithCommissions ............................................................................................ 192|
|FirestormOrderWS.PostTrackingNumber ............................................................................................................ 194|
|FirestormOrderWS.PostTrackingNumberWithEmail ........................................................................................... 195|
|FirestormOrderWS.PostMultipleTrackingNumbers............................................................................................. 196|
|FirestormOrderWS.PreCalculateOrderTotals ...................................................................................................... 199|
|FirestormOrderWS.VoidOrder ............................................................................................................................. 205|
|FirestormOrderWS.VoidOrderDetail ................................................................................................................... 207|
|FirestormOrderWS.GetShipperListWithRates ..................................................................................................... 208|
|FirestormOrderWS.GetShipperList ...................................................................................................................... 213|
|FirestormOrderWS.FulfillOrder ........................................................................................................................... 215|
|FirestormPartyWS .................................................................................................................................................... 217|
|FirestormPartyWS.AssignGuestToParty .............................................................................................................. 218|
|FirestormPartyWS.FindPartyGuest ...................................................................................................................... 219|
|FirestormPartyWS.GetOpenPartiesByDealer ...................................................................................................... 221|
|FirestormPartyWS.GetGuestListByPartyID .......................................................................................................... 222|
|FirestormPartyWS.GetPartiesByDate .................................................................................................................. 223|
|FirestormPartyWS.SavePartyOrder ..................................................................................................................... 225|
|FirestormPartyWS.SavePartyGuest ..................................................................................................................... 231|
|FirestormPartyWS.GetPartyHostDetail ............................................................................................................... 233|
|FirestormPartyWS.SavePartyHost ....................................................................................................................... 235|
|FirestormPartyWS.SaveParty ............................................................................................................................... 237|
|FirestormPartyWS.GetPartyTypeList ................................................................................................................... 239|
|FirestormPartyWS.GetPartyStatusList ................................................................................................................. 240|
|FirestormPartyWS.CloseParty .............................................................................................................................. 241|
|C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c .P a g e4 | 317|



Firestorm® Web Services API | Version 2.2.33 

|FirestormRecurringOrderWS ................................................................................................................................... 242|
|---|
|Recurring Order Status Codes .............................................................................................................................. 243|
|FirestormRecurringOrderWS.DeactivateRecurringOrder .................................................................................... 244|
|FirestormRecurringOrderWS.GetRecurringOrdersForDealer .............................................................................. 245|
|FirestormRecurringOrderWS.SaveRecurringOrder .............................................................................................. 248|
|FirestormRecurringOrderWS.SaveRecurringOrderPayment ............................................................................... 251|
|FirestormRecurringOrderWS.GetRecurringOrdersByDealer ............................................................................... 253|
|FirestormRecurringOrderWS.GetRecurringOrderProductList ............................................................................. 255|
|FirestormRecurringOrderWS.GetRecurringOrderHistory .................................................................................... 257|
|FirestormRecurringOrderWS.GetRecurringOrderDetail ...................................................................................... 258|
|FirestormRecurringOrderWS.GetRecurringOrder ............................................................................................... 260|
|FirestormRecurringOrderWS.DeleteRecurringOrderPayment ............................................................................ 263|
|FirestormRecurringOrderWS.DeleteRecurringOrderDetail ................................................................................. 264|
|FirestormRecurringOrderWS.DeleteRecurringOrder .......................................................................................... 265|
|FirestormRecurringOrderWS.DeleteItemFromRecurringOrder .......................................................................... 266|
|FirestormRecurringOrderWS.AddItemToRecurringOrder ................................................................................... 267|
|FirestormRecurringOrderWS.ActivateTemplate .................................................................................................. 269|
|FirestormRecurringOrderWS.GetRecurringOrderPayment ................................................................................. 270|
|FirestormShoppingCartWS ...................................................................................................................................... 272|
|FirestormInventoryWS.AssignShoppingCartGrouping ........................................................................................ 273|
|FirestormInventoryWS.UnAssignShoppingCartGrouping .................................................................................... 275|
|FirestormShoppingCartWS.GetShoppingCartMasterGroupCodes ...................................................................... 277|
|FirestormShoppingCartWS.GetShoppingCartLevel1GroupCodes ....................................................................... 278|
|FirestormShoppingCartWS.GetShoppingCartLevel2GroupCodes ....................................................................... 279|
|FirestormWebWS ..................................................................................................................................................... 280|
|FirestormWeb.UpdateWebPassword .................................................................................................................. 281|
|FirestormWebWS.UpdateDealerURL ................................................................................................................... 282|
|FirestormWebWS.AuthenticateLogin .................................................................................................................. 284|
|FirestormWebWS.AuthenticateSession .............................................................................................................. 285|
|FirestormWebWS.UpdateDealerWebGreeting ................................................................................................... 286|
|FirestormWebWS.UpdateDealerWebAccess ....................................................................................................... 287|
|FirestormWebWS.AssignDealerWebOption ........................................................................................................ 289|
|FirestormWebWS.UnAssignDealerWebOption ................................................................................................... 291|
|C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c .P a g e5 | 317|



Firestorm® Web Services API | Version 2.2.33 

|External Order Gateway .......................................................................................................................................... 293|
|---|
|FirestormMobileWS ................................................................................................................................................. 302|
|FirestormMobileWS.RunCommand ..................................................................................................................... 303|
|Firestorm Lookups Web Service .............................................................................................................................. 312|
|FirestormLookupsWS.GetLookupTableData ........................................................................................................ 313|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 6 | 317 

Firestorm® Web Services API | Version 2.2.33 

### Revision History 

|Date|Revision|Who|Comments|
|---|---|---|---|
|3/3/2014|2.0|JTR|Initial Re-Write|
|3/18/2014|2.0.1|JTR|Added FirestormInventoryWS.GetCatalogueList()|
|3/21/2014|2.0.2|JTR|Added FirestormPartyWS.GetOpenPartiesByDealer()|
|4/21/2014|2.0.3|JTR|Added documentation for external ordergateway|
|4/24/2014|2.0.4|JTR|Modified the FirestormEnrollmentWS.EnrollCustomer() web method to allownomail/bill address to be<br>passed in|
|4/24/2014|2.0.5|JTR|Added new web service FirestormDealerWS.GetDealerOptions()|
|7/3/2014|2.0.06|JTR|Added newplacement option for binaryenrollment web services|
|7/17/2014|2.0.07|JTR|Added support for linkedproducts in external ordergateway|
|8/14/2014|2.0.08|JTR|Added “ShoppingCartID” to external order gateway and added special return XML document when<br>passingin a ShoppingCartID.|
|11/12/2014|2.0.09|JTR|Modified EnrollCustomer()web service to use default values for specific fields.|
|1/21/2015|2.0.10|JTR|Changed SoldTo to ShipTo on SaveOrder()and SaveOrderExtended()|
|2/19/2015|2.0.11|JTR|Added VAT tax fields to FirestormOrderWS.GetOrders()|
|4/26/2016|2.0.12|ATR|Added method FirestormDealerWS. GetDealerDetailExtended2()|
|6/1/2016|2.0.13|JTR|Added support for TLS 1.2|
|7/21/2016|2.1.0|JTR|Added new web service FirestormMobile|
|12/21/2016|2.2.0|ATR|Added new methods AdjustInventory() and GetProductItemDetail() to FirestormInventoryWS. Added<br>new web service FirestormCouponWS.|
|08/07/2017|2.2.1|JTR|Added new method GetCurrentInventoryCounts()|
|12/18/2017|2.2.2|JTR|Added new web service FirestormDealershipWS|
|02/15/2018|2.2.3|ATR|Added documentation for FirestormOrderWS.GetOrderDetail|
|02/16/2018<br>|2.2.4|JTR|Added New Web Service methods to FirestormPartyWS<br>|
|12/13/2018|2.2.5|JTR|Added new web service method to FirestormOrderWS(PostTrackingNumberWithEmail)|
|1/21/2019|2.2.6|JTR|Added new web service SaveOrderExtendedWithOptions()|
|3/4/2019|2.2.7|JTR|Rolled out support for RecurringOrders|
|3/19/2019|2.2.8|JTR|Added CDATA declarations around order detail elements for SaveOrder*()functions|
|3/21/2019|2.2.9|JTR|Added support for ReportCode to FirestormGenealogyWS.GetDownlineByDealerID()|
|4/2/2019|2.2.10|ATR|Added new method FirestormInventoryWS.GetProductItems()<br>Added new definitions to GetCatalogContents()for GroupString,Group1 and Group2|
|4/3/2019|2.2.11|JTR|Added new web services|
||||FirestormDealerWS.GetCustomerListByDealerID()|
|5/23/2019|2.2.12|JTR|Added new web service<br>FirestormOrderWS.PreCalculateOrderTotals|
|5/23/2019|2.2.13|ATR|Added new web services<br>FirestormWebWS.UpdateDealerWebAccess<br>FirestormWebWS.AssignDealerWebOption<br>FirestormWebWS.UnAssignDealerWebOption<br>FirestormDealerWS.ActivateDealer<br>FirestormDealerWS.DeActivateDealer<br>FirestormDealershipWS.ActivateDealership|
||||FirestormDealershipWS.DeActivateDealership|
|6/6/2019|2.2.14|JTR|AddedQtyAssigned to the ouput of FirestormInventoryWS.GetProductItems()|
|7/23/2019|2.2.15|JTR|Added trackingnumber to the return of FirestormOrderWS.PostMultipleTrackingNumbers()|
|7/31/2019|2.2.16|JTR|Clarified information on getting QtyAssigned in the output of<br>FirestormInventoryWS.GetProductItems()|
|11/22/2019|2.2.17|ATR|Added Birthdate as aparameter for FirestormPartyWS.SavePartyHost()|
|04/07/2020|2.2.18|JTR|Added new functions to FirestormDealerWS(GetRankWidgetData and GetRankWidgetRankPath)|
|07/07/2021|2219|JTR|Updated copyright notice|
|10/14/2021|..<br>2.2.20|ATR|<br>Added new method FirestormEnrollmentWS.EnrollMemberInHoldingTank()|
|10/20/2021|2.2.21|JTR|Added clarifying descriptions to FirestormInventoryWS.GetCatalogueContents|
|10/22/2021|2.2.22|JTR|Corrected typos and added clarification to FirestormPartyWS.SavePartyOrder()|
|11/02/2021|2.2.23|JTR|Corrected return XML document on FirestormOrderWS.PreCalculateOrderTotals()|
|11/22/2021|2.2.24|JTR|Added new output fields to FirestormInventoryWS.GetCatalogueContents()<br>Added new web service FirestormInventoryWS. GetVariationPathsForParentProduct()|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 7 | 317 

Firestorm® Web Services API | Version 2.2.33 

|11/24/2021|2.2.25|JTR|Added new web service FirestormOrderWS.GetShipperListWithRates()|
|---|---|---|---|
|11/29/2021|2.2.26|JTR|Added “IsStreaming” to output of FirestormInventoryWS.GetCatalogueList()<br>Added DealershipID, PaidAsDealershipTypeID, PaidAsRankCode to output of<br>FirestormDealerWS.GetDealerDetailExtended2()|
|11/30/2021|2.2.27|JTR|Added new web service FirestormInventoryWS.GetInventoryCountsByProductID()|
|12/6/2021|2.2.28|JTR|Added documentation for FirestormInventoryWS.GetCatalogueContentsV4Cart()|
|12/13/2021|2.2.29|JTR|Corrected a documentation error in FirestormInventoryWS.GetCatalogueContentsV4Cart()|
|05/20/2022|2.2.30|ATR|Added FirestormOrderWS.GetShipperList()|
|10/13/2022|2.2.31|ATR|Added new methods FirestormInventoryWS.SaveProduct(),<br>FirestormInventoryWS.SaveCatalogueProductDetail(), FirestormInventoryWS.GetProductList(), and<br>FirestormInventoryWS.GetInventoryGroupCodes(). Added new web service FirestormShoppingCartWS.|
|01/17/2023|2.2.32|ATR|Added FirestormDealerWS.CreditProductPoints(), FirestormDealerWS.DebitProductPoints(),<br>FirestormDealerWS.GetDealerProductPointBalance(), FirestormDealerWS.GetDealerKPIData(),<br>FirestormOrderWS.FulfillOrder().|
|06/30/2026|2.3.33|JTR|Added new web service FirestormLookupWS.asmx|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 8 | 317 

Firestorm® Web Services API | Version 2.2.33 

### Introduction 

The Firestorm web services API is designed to allow you to pull information from your system on demand, using SOAP/XML web services that expose the internal Programmers API for use on the web. It is a comprehensive platform that supports a wide variety of features and functionality that can be used to integrate external system with Firestorm®. The web services are grouped together based on the area of the system that will be accessed (Enrollments, Orders, etc). 

Who Should Read This Document? 

This document provides an overview of the services offered by Firestorm® available through the API. The target audience of this document is IT personnel of companies interested in integrating external systems with Firestorm®. 

##### Scope of the Document 

This document provides the list of services that are offered by Firestorm® that can be accessed using the Firestorm Web service API. It includes the methods used and their signatures through which an external system can communicate with Firestorm®. This document provides an overview and high level technical details about how external systems can communicate and exchange messages using the Web services API. 

##### FEPS 

If your system integration needs dictate that you need to have data “pushed” to you system in response to an event that occurs within Firestorm® rather than pulled through web services, please contact your sales representative for more information about our FEPS™ Event Push System. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 9 | 317 

Firestorm® Web Services API | Version 2.2.33 

### Notational Conventions Used in this Document 

Code Samples 

`Courier New` represents the code sample. **`Bold`** elements in code samples indicate mandatory fields. 

Abbreviations 

Data type abbreviations: 

A – Alphabetic value. 

AN – Alphanumeric values. 

D – Date values. 

DT – Date and time values. 

N – Numeric values. String = All value accepted. 

Abbreviations used for required/optional data 

Y – Yes (Mandatory) 

N – No (Not Required) 

O – Optional 

C – Conditional 

N/A – Not Available/Not Applicable 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 10 | 317 

**~~e~~** ~~ee~~ <u>reer reer e eee</u> ~~erence~~ 

~~ee~~ 



<!-- Start of picture text -->
ApplicationClient  "J SOAP Request<br>Web Service SOAP Response<br>Proxy Firestorm Web Services<br><!-- End of picture text -->

Firestorm® System 

Firestorm® Web Services API | Version 2.2.33 

### Web Services Summary and WSDL 

The following web services are provided as part of the Firestorm Web Services API. Each available web service is grouped by major area of functionality. Each service definition contains a URL that may be used to obtain the full WSDL documentation for that service. 

Your company must authorized properly for each specific web service and method. Each web service is detailed in its own section that will provide guidance on proper calls and **<u>Return Values</u>** <u>.</u> 

##### **_NOTE: If you have opted for a dedicated server platform, then the web services API will be located at the primary URL designated for your server (NOT firestormwebservices.com). Please contact our support department for the proper URL to use for each web service._** 

Please note that when there is an “Extended” version of a method, it should be used for all new implementations. The non-extended version is only in place for backwards compatibility. 

|Coupons<br>**WSDL:** https://www.fire<br>Web Service Name|stormwebservices.com/FirestormWeb<br>Available Methods|Services/FirestormCouponWS.asmx<br>Description|
|---|---|---|
|FirestormCouponWS|CreateShoppingCartCoupon|Allows for the creation of a Firestorm<br>Shopping Cart Coupon which can be<br>used in the ShoppingCart.|



|Dealers<br>**WSDL:** https://www.fire<br>|stormwebservices.com/FirestormWe<br>|bServices/FirestormDealerWS.asmx<br>|
|---|---|---|
|Web Service Name|Available Methods|Description|
|FirestormDealerWS|GetDealerDetail|Searches for and retrieves detailed<br>information about a single dealer<br>(human being) that is registered in the<br>system.|
||GetDealerDetailExtended|Retrieves detailed information about a<br>single dealer (human being) that is<br>registered in the system. Adds the<br>abilityto search by phone number.|
||GetDealerDetailExtended2|Retrieves detailed information about a<br>single dealer (human being) that is<br>registered in the system. Adds the<br>ability to search by phone number. Adds<br>ability to filter by Dealers only (non-<br>customers)and Active status.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 12 | 317 

Firestorm® Web Services API | Version 2.2.33 

|DealerSearch|Retrieves detailed information about all<br>dealers in the system that match the<br>search criteria specified. Returns a<br>recordset that contains all matching<br>records.|
|---|---|
|SaveDealerDetail|Allows a single dealer record to be<br>updated|
|GetDealerListByDealerIDRange|Returns a list of dealers whose DealerID<br>numbers fall within a specified range|
|UpdateTaxPayerNumber|Allows a single dealer’s Tax Payer<br>Number to be updated|
|DealerLocator|Returns a list of dealers who are<br>geographically close to a specified zip<br>code. Also allows searching by last<br>name.|
|GetUnpaidCommissions|Returns the amount of commissions that<br>a given dealer has available in their<br>account.|
|GetDealerCommissionsByDate|Returns a list of commission records for<br>a single dealer that were generated<br>between a specified date range|
|SaveDealerOption|Allows updating of a custom field for a<br>specified dealer|
|GetCustomerListByDealerID|Returns a list of all customers for a given<br>member|
|GetRankWidgetData|Returns a complex XML document<br>containing all the rank requirements and<br>a particular members status for each<br>requirement|
|GetRankWidgetRankPath|Returns an XML document containing<br>thepromotionpath for agiven member|



|Enrollments<br>**WSDL:** https://www.firestor<br>|mwebservices.com/FirestormWe<br>|bServices/FirestormEnrollmentWS.asmx<br>|
|---|---|---|
|Web Service Name|Available Methods|Description|
|FirestormEnrollmentWS|EnrollMember|This method is used to enroll a new<br>member that will be participating in the<br>compensation plan of the company. This<br>is a single step enrollment that will create<br>a structure position as well as a dealer<br>record for the individual.|
||EnrollMemberAsOrphan|This method is used to enroll a new<br>member that will be participating in the<br>compensation plan of the company but<br>theproperplacement or sponsorshipis|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 13 | 317 

Firestorm® Web Services API | Version 2.2.33 

||not known. This method will perform all<br>the same steps as EnrollMember(), but<br>will not attach the new structure position<br>into theprimarytree..|
|---|---|
|EnrollCustomer|This method will create a new dealer<br>record in the system and will flag them as<br>a customer of the specified customer<br>type(retail,etc)|
|EnrollMemberExtended|Performs all the same steps as<br>EnrollMember() but also accepts a<br>specific order via an embedded XML<br>document.|
|EnrollMemberInHoldingTank|Allows a member to be enrolled directly<br>into the holding tank of a specified<br>sponsor.|



|Genealogy<br>|||
|---|---|---|
|**WSDL:** https://www.firestor<br>|mwebservices.com/FirestormWe<br>|bServices/FirestormGenealogyWS.asmx<br>|
|Web Service Name|Available Methods|Description|
|FirestormGenealogyWS|GetDownlineByDealerID|Retrieves the entire downline of a<br>specific dealer/position. The output of<br>this services is controlled by genealogy<br>management tool in the Firestorm®<br>administrative application.|



|Inventory<br>**WSDL:** https://www.firest<br>|ormwebservices.com/FirestormWebServices/F<br>|irestormInventoryWS.asmx<br>|
|---|---|---|
|Web Service Name|Available Methods|Description|
|FirestormInventoryWS|AdjustInventory|Allows for adjustments to be made<br>to inventory levels for a specified<br>item|
||GetCatalogueContents|Retrieves the detailed records for<br>all products assigned to a given<br>catalog. Includes pricing and<br>productpicture URLs.|
||GetCatalogueContentsV4Cart|Retrieves the detailed records for<br>all products assigned to a given<br>catalog. Includes pricing and<br>product picture URLs as well as<br>enhanced parent/child information.<br>Also returns grouping data specific<br>to the v4 cart.|
||GetEnrollmentSpecialsByDealershipType|Returns a list of products that have<br>been designated as enrollment|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 14 | 317 

Firestorm® Web Services API | Version 2.2.33 

||specials by the administrator. The<br>products are catalog and dealership<br>type(rank)specific.|
|---|---|
|GetProductItemDetail|Returns detailed information about<br>a specific Item defined in Firestorm|
|GetShoppingCartGroupCodeDetail|Returns detailed information about<br>a shoppingcartgroupingcode|
|GetVariationPathsForParentProduct|Returns variation pathing for a<br>givenparentproduct|



|Orders|||
|---|---|---|
|**WSDL:** https://www.fires<br>|tormwebservices.com/FirestormWebServic<br>|es/FirestormOrderWS.asmx<br>|
|Web Service Name|Available Methods|Description|
|FirestormOrderWS|SaveOrder|Saves a single order into the<br>Firestorm® system, allowing the<br>caller to specify an order with a<br>detailed XML document which<br>describes all elements of the order.|
||SaveOrderExtended|Same functions as SaveOrder(), but<br>also includes the ability to pay for<br>the order with commissions|
||SaveOrderExtendedWithOptions|Same functions as<br>SaveOrderExtended() but includes<br>an ability to pass an xml document<br>to control several optional<br>capabilities.|
||ValidatePurchase|Verifies that a specific product was<br>purchased by a dealer within a<br>specified date range|
||GetOrders|Returns a list of orders that were<br>placed between a specified start<br>and end date. Also allows the<br>specification of a specific product<br>number to filter the result with.<br>(i.e.: All orders placed between<br>start and end date that contained<br>product X)|
||PostTrackingNumber|Allows a single order to be updated<br>with a tracking number and ship<br>date.|
||PostMultipleTrackingNumbers|Allows multiple orders to be<br>updated with their own tracking<br>number and ship date. A special<br>XML document is used to pass in a<br>list of orders and tracking<br>information.|
||PayForOrderWithCommissions<br>GetFirestormTaxRate||



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 15 | 317 

Firestorm® Web Services API | Version 2.2.33 

GetShipperListWithRates Returns a list of available shippers for a given order along with the actual calculated shipping charge for the order 

## <mark>Parties</mark> 

|**WSDL:**https://www.fires<br>Web Service Name|tormwebservices.com/FirestormWeb<br>Available Methods|Services/FirestormPartyWS.asmx<br>Description|
|---|---|---|
|FirestormPartyWS|GetGuestListByPartyID|Return a listing of all party guests that<br>have been assigned to agivenparty|
||SavePartyOrder|Supplies the same functionality as<br>FirestormOrderWS.SaveOrderExtended,<br>but also allows the specification of a<br>PartyID and a PartyGuestID so allow<br>this order to be credited to a specific<br>party|
||AssignGuestToParty||
||FindPartyGuest||
||GetOpenPartiesByDealer||
||GetGuestListByPartyID||
||GetPartiesByDate||
||SavePartyOrder||
||SavePartyGuest||
||GetPartyHostDetail||
||SavePartyHost||
||SaveParty||
||CloseParty||
||GetPartyTypeList||
||GetPartyStatusList||
||GetCampaignList||



## <mark>Recurring Orders (Autoships)</mark> 

**<mark>WSDL:</mark>** <mark>https://www.firestormwebservices.com/FirestormWebServices/FirestormRecurringOrderWS.asmx</mark> 

|Web Service Name|Available Methods|Description|
|---|---|---|
|FirestormRecurringOrderWS|DeactivateRecurringOrder|Terminates shipment of a specified<br>recurringorder|
||GetRecurringOrdersForDealer|Returns a list of recurring orders for a<br>specified DealerID|
||SaveRecurringOrder||
||SaveRecurringOrderPayment||
||GetRecurringOrdersByDealer||
||GetRecurringOrderProductList||
||GetRecurringOrderHistory||
||GetRecurringOrderDetail||
||GetRecurringOrder||
||DeleteRecurringOrderPayment||
||DeleteRecurringOrderDetail||



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 16 | 317 

Firestorm® Web Services API | Version 2.2.33 

|DeleteRecurringOrder<br>|
|---|
|DeleteItemFromRecurringOrder|
|AddItemToRecurringOrder|
|ActivateTemplate|
|GetRecurringOrderPayment|



## <mark>Web</mark> 

**<mark>WSDL:</mark>** <mark>https://www.firestormwebservices.com/FirestormWebServices/FirestormWebWS.asmx</mark> 

|Web Service Name|Available Methods|Description|
|---|---|---|
|FirestormWebWS|UpdateWebPassword|Updates the password used by a dealer<br>when logginginto their virtual office|
||UpdateDealerURL|Updates the replicated website URL for<br>a dealer|
||AuthenticateLogin|Used to authenticate the login<br>credentials of a dealer|
||AuthenticateSession|Used to verify that the session that a<br>dealer is currently using actually<br>belongs to them. Prevents hijacking of a<br>session bya malicious user.|
||UpdateDealerWebGreeting|Updates the personal greeting used on<br>replicated website for the dealer. This<br>feature must be enabled on your<br>company’s replicated websites first.|



## <mark>Mobile</mark> 

|**WSDL:**https://www.fire<br>|stormwebservices.com/Firestorm<br>|WebServices/FirestormMobileWS.asmx<br>|
|---|---|---|
|Web Service Name|Available Methods|Description|
|FirestormMobileWS|RunCommand|A highly customizable general web<br>service for pulling data in a client<br>specific format for use by mobile<br>applications|



## <mark>Lookups</mark> 

|**WSDL:** https://www.firest<br>|ormwebservices.com/FirestormW<br>|ebServices/FirestormLookupWS.asmx<br>|
|---|---|---|
|Web Service Name|Available Methods|Description|
|FirestormLookupWS|GetLookupTableData|Depending on what code is supplied as<br>an argument, this web service will return<br>all valid values for a given type. (For<br>example: Customer Types, Countries,<br>States,etc)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 17 | 317 

Firestorm® Web Services API | Version 2.2.33 

### Obtaining Access to the Web Services 

Each of the web services incorporates multiple layers of security to ensure that only properly authorized parties will be able to access your information. All access to the web services should be through a valid SSL (https) connection. While the web services can be accessed without a secure connection, this mode is for development purposes only and should not be used for production. 

_Note: In order to use the web services API, you must have purchased the correct module from our sales department. Please contact sales@trinitysoft.net for more information._ 

##### Enable Each Method for Access 

In order to be able to use any method in the web services API, you must be granted permission to do so by our support department. After reviewing the API, make a list of the methods you wish to use and contact out support department. Our team will “turn on” each method you desire to use. 

##### Token 

Each web service will require as its first argument a unique secret key called a token, that has been assigned to your company by our support department.  You must use this token on all calls to any method in the web services API. 

Once you have been assigned your token, keep it in a safe place, as this is your key to being able to use the web services successfully. 

If your token is lost or compromised contact our support department immediately so we can invalidate your old token and issue you a new one. You may also wish to change your token on a regular interval. You may do so at any time by calling our support department to be issued a new token. 

##### Context 

Each web services call will require a special context value that will be assigned to you by our support department. This context value in an additional security key that is used by the system validate your access level. 

##### Whitelisting Your IP Address 

Each IP Address that will be used to access the web services must be whitelisted (allowed access) on our servers. If this is not done, ALL web service PAI requests will be denied. Please contact out support department with a list of specific IP addresses that you wish to allow access. Please note that we will need a complete list. Ranges of IP addresses are not allowed. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 18 | 317 

Firestorm® Web Services API | Version 2.2.33 

### Logging 

All access to the web APIs are documented in logs that are maintained on our servers.  Since the web API calls will fail silently if security credentials are not valid, sometimes it may be necessary to dig into the logs to see what is happening. 

While you will not have direct access to these logs, if you are having a problem during implementation that you need assistance with, our support department will be glad to assist in your implementation by reviewing the logs for you to see if your call is making it to our servers. 

##### Transaction Logging 

Once you are up and running successfully, the system will record all transactions in your database along with argument values that are supplied and the result of the call. The system will also record the IP address and various other pieces of information regarding the call. If you are on a dedicated server, you will have direct access to this table. If you are on the shared platform, you will need to submit a support request to have someone review this data for you. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 19 | 317 

Firestorm® Web Services API | Version 2.2.33 

### Country Specific Restrictions 

The Firestorm web services API may be restricted to allow specific services to only return or modify data from specific countries. This allows the system to enforce returned datasets to be filtered to only return data from a specific country or to only allow an update to data in a specific country, based on who is calling the web service. 

In other words, if a company has a division in Japan who will be using the web API to retrieve data, this feature will allow that caller to see data only from Japan even if records from other countries (i.e.: USA) would normally be returned by the specific call. Each authorized user may be restricted to any number of specific countries. 

**_This capability does not apply to all services_** . Please refer to the specific documentation for each method to determine if this feature is available. 

If the country restrictions are used in a manner other than described here, the method description will include this information in the “Additional Restrictions” section for that method. 

If you desire to use this capability, you must first compile a list of all authorized users, along with the methods they are authorized to access. Once you have that, you must decide on which countries each user will be allowed to see data for. Once you have this list, please contact our support department for assistance in setting up these restrictions. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 20 | 317 

Firestorm® Web Services API | Version 2.2.33 

### Field Level Restrictions 

The Firestorm® web services API allows the returned results to be restricted to only a defined sub-set of fields that would normally be returned from a method call. This restriction can be put in place for each authorized user of the web services. 

This functionality is very useful for restricting access to data that may be considered sensitive in nature. 

If you desire to use this capability, you must first compile a list of all authorized users, along with the fields they are authorized to access for each method call. Once you have this list, please contact our support department for assistance in setting up these restrictions. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 21 | 317 

Firestorm® Web Services API | Version 2.2.33 

### General Rules 

When calling one of the web services that are included in the API, the following general rules will apply to each call: 

##### **1. You must have proper credentials to access the API** 

Please refer to earlier sections of this document to understand all requirements. If any of the elements are incorrect, you will be denied access to the API. 

##### **2. You must provide a value for each argument to a method** 

When calling a method on the API, there are no optional arguments. You must provide a value for all arguments in order to call the web service successfully. If the argument is a string type, then you must at least provide an empty string (“”) for that argument. 

##### **3. Any string argument that you don’t want to use should be passed as a zero length string** 

If a given method has an argument that is expecting a string value and you are not going to use it, they you should pass in a zero length string. (This is NOT a NULL value). 

**WARNING: SPECIAL EXCEPTION:** Some of the web services that update values will require a special value to be passed in to preserve a prior value that already exists in the database. A zero length string is used to delete an existing value. These instances are notated clearly in the documentation for that method. 

##### **4. Return types can be complex or scalar** 

May of the functions of the API will return an XML document that will contain elements to indicate the success or failure of the call. If a failure occurred, the xml document will contain a list of error elements that describe all errors that occurred during the call. 

##### **5. All SSL Connections must be made with TLS 1.2 or higher** 

Due to PCI Compliance requirements, all SSL connections made to our servers must support TLS 1.2 or higher. Your server must also use TLS 1.2 or higher, or our system will silently reject your attempt to communicate. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 22 | 317 

Firestorm® Web Services API | Version 2.2.33 

### <u>Return Values</u> 

All of the web service API methods will return either a numeric value, a Boolean value or a complex XML document. The return types are documented below: 

Numeric Value 

A web service that returns a numeric value will always return a number, either positive or negative (depending on what it is used for). You must interpret this result to determine success or failure. 

##### Boolean Value 

These web service methods will return a Boolean TRUE (-1) if the call was successful, or will return a Boolean FALSE (0) if the call failed. 

##### DataTable 

These methods will return a list containing the results of the request. Please note that many times, the returned result is the output from a query that is run against a database, and as such the output can change as new fields are added to a table. It is important that you make some test calls and look at the result to ensure that you have a full list of fields that will be returned. Each method that will return a list will have a defined output in its documentation, but changes could occur that are not reflected in the documentation that you have. ALWAYS do a test call to ensure you have a full understanding of the actual returned values for each field in the result set. 

##### Complex Return 

Many of the web API calls support the return of a complex XML document that will describe the result of the call. When a method supports this type of return value, it will be clearly notated in the definition of the method. 

The base version of this XML document is described below, along with an example. 

**WARNING:** Some web methods will return additional elements that are relevant to the call. Please see the documentation for each specific method for full details. 

Example Return XML : 

```
'/////////////////////
'// Sample Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ID>integer</ID>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 23 | 317 

Firestorm® Web Services API | Version 2.2.33 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||If the method created a new record (as in SaveOrder()) this element will contain the<br>ID number that was assigned by the system when the record was created. In the<br>example of SaveOrder(),it would be the new OrderID.|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 24 | 317 

Firestorm® Web Services API | Version 2.2.33 

### Errors and Internal Logs 

Whenever an internal error occurs during processing of a web services request, any resulting error messages are suppressed, and the web service will fail silently. This is a security feature designed to prevent inadvertently presenting any system specific information to the outside world that could be used by unscrupulous persons in attempting to gain unauthorized access. Types of errors that this will occur on are Access validation errors, SQL errors, database errors and the like. 

When these types of error occur, the system will record them in a special log maintained on the Firestorm® system. This log will contain the date and time of the error along with the full text of any error messages that were returned. This log is not accessible from the outside world but must be accessed by administrative personnel who have unrestricted access to the database. 

If you need access to these logs during your integration development efforts, you will need to coordinate with our support department (support@trinitysoft.net). A team member will be assigned to you to assist in your troubleshooting efforts. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 25 | 317 

Firestorm® Web Services API | Version 2.2.33 

### Firestorm Coupon Service 

|General Inform<br>Name|ation<br>FirestormCouponWS.asmx|
|---|---|
|WSDL|https://www.firestormwebservices.com/FirestormWebServices/FirestormCouponWS.asmx|
|Description|This web service will contain all methods necessaryto create new ShoppingCart Coupons|



|Method Summary||
|---|---|
|Method Name|Return Type|
|CreateShoppingCartCoupon|Boolean|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 26 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormCouponWS.CreateShoppingCartCoupon 

Allows a remote system to create a single shopping cart coupon which can be used within the Firestorm Shopping Cart. 

|Method Definition|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|Code|Y|The Coupon Code to be assigned to the new coupon.<br>Must be unique.|String||
|Description|Y|A description for the coupon. Will be viewable in the<br>Coupon manager.|String||
|CustomProcName|Y|The custom process name for when the IsCustom<br>flag is set to true. If this value is set,<br>CustomClassName cannot also be set.|String|Contact support for<br>valid values.|
|CustomClassName|Y|The custom class name for when the IsCustom flag is<br>set to true. If this value is set, CustomProcName<br>cannot also be set.|String|Contact support for<br>valid values.|
|ExpirationDate|Y|The expiration date of the coupon in MM/DD/YYYY<br>format.|Date|Any valid date in the<br>future in<br>MM/DD/YYYY<br>format.|
|OneTimeUseOnly|Y|A flag indicating if the coupon may only be used<br>once. This is a global value. If true, once the coupon<br>has been used 1 time,it maynot be used again.|Boolean|TRUE/FALSE|
|DealerUseOnly|Y|A flag indicating whether this coupon is only useable<br>bydistributors.|Boolean|TRUE/FALSE|
|PublicUseOnly|Y|A flag indicating whether or not this coupon is only<br>useable byretail customers.|Boolean|TRUE/FALSE|
|IsCustom|Y|A flag to indicate if this is a “custom” coupon. Please<br>contact support to determine if you need to use this<br>coupon type or not.|Boolean|TRUE/FALSE|
|IsDiscount|Y|A flag to indicate whether or not this coupon will<br>applya discount to an order.|Boolean|TRUE/FALSE|
|IsFreeProduct|Y|A flag to indicate if this coupon will award a free<br>product on an order.|Boolean|TRUE/FALSE|
|DiscountAmount|Y|The discount dollar amount for a discount coupon.|Double|Any valid positive<br>dollar amount|
|DiscountPercentage|Y|The discountpercentage for a discount coupon.|Double|0.01 – 1.00|
|FreeProductNumber|Y|The product number to be awarded as free product<br>when this coupon is redeemed. Only applicable<br>when IsFreeProduct is true.|String|Any valid Firestorm<br>Product Number.|
|IndividualOneTimeUse|Y|A flag to indicate if this coupon may only be used by<br>a specific dealer in firestorm, a maximum of one<br>time.|Boolean|TRUE/FALSE|
|IssuedToDealerID|Y|The Dealer ID in Firestorm to issue this coupon to<br>when IndividualOneTimeUse is true. The Dealer<br>must be logged in to redeem the coupon.|Integer|Any valid Firestorm<br>Dealer ID|
|IssuedToPartyHostID|Y|This field is not currently used and is reserved for<br>future functionality. A value of -1 must be passed in<br>this field.|Integer|-1|
|IssuedToPartyGuestID|Y|This field is not currently used and is reserved for<br>future functionality. A value of -1 must be passed in<br>this field.|Integer|-1|
|ValidForCatalogueID|Y|The Catalogue ID in Firestorm to restrict this coupon<br>to. This is the only catalogue this coupon will be<br>useable in.|Integer|Any valid Firestorm<br>Catalogue ID|
|Comment|Y|A descriptive comment for the coupon.|String||
|CustomProcArguments|Y|A string specifying any custom argument values<br>required for a custom coupon. Please contact<br>support to see ifyou need to use this field.|String|Contact support for<br>valid values.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 27 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

Coupon Codes must be unique in the system. This means that you may not create coupons with the same coupon code. If you attempt to create a coupon that uses a coupon code that already exists, the request will fail. 

##### <u>Coupon Types</u> 

There are three main coupon types available in the system. Discount, Free Product, and Custom. 

The Discount coupon type can have either a flat discount applied (e.g. $50) or can have a discount to be applied to the order (e.g. 20%). If using a discount coupon, only one type of discount may be specified. 

The Free Product coupon type will add a product to a shopping cart order for no cost. 

The Custom coupon type allows for additional functionality to be implemented in the coupon system, such as conditional discount levels, special restrictions, and more. If you need to use a custom coupon type, please contact our support department for more details. 

Only one coupon type may be specified for any given coupon. If you specify more than one type for a coupon, the creation request will fail. 

##### **<u>Return Values</u>** 

The web service will return a Boolean value indicating whether or not the creation of the coupon was successful. If a value of False is returned, you will need to review the web service transaction logs for details on the failure. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 28 | 317 

Firestorm® Web Services API | Version 2.2.33 

### Firestorm Dealer Web Service 

<mark>General Information</mark> Name FirestormDealerWS.asmx WSDL https://www.firestormwebservices.com/FirestormWebServices/FirestormDealerWS.asmx Description This web service will contain all methods necessary to edit and maintain records for a Dealer. Each method is described below, along with the definition of each argument and valid values where appropriate. 

|Method Summary||
|---|---|
|Method Name|Return Type|
|GetDealerDetail|DataTable|
|GetDealerDetailExtended|DataTable|
|GetDealerDetailExtended2|DataTable|
|DealerSearch|DataTable|
|SaveDealerDetail|Boolean|
|GetDealerListByDealerIDRange|DataTable|
|UpdateTaxPayerNumber|Boolean|
|DealerLocator|DataTable|
|GetUnpaidCommissions|Numeric(Double)|
|GetUnpaidCommissionsByDate|DataTable|
|SaveDealerOption|Boolean|
|GetDealerOptions|DataTable|
|GetCustomerListByDealerID|DataTable|
|ActivateDealer|Complex XML Document|
|DeActivateDealer|Complex XML Document|
|CreditProductPoints|Boolean|
|DebitProductPoints|Boolean|
|GetDealerProductPointBalance|Numeric(Double)|
|GetDealerKPIData|DataTable|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 29 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.GetDealerDetail 

Searches for a dealer record based on the passed in search criteria. The system will pull all matching records and will return a datatable that will have an entry for each matching record. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|C|The unique DealerID you are searching for. This<br>values will take precedence over any other search<br>parameters! If you supply this, all other parameters<br>are ignored.|Numeric|Any non-negative<br>DealerID|
|TaxPayerNumber|C|Generally in the USA, this is a SSN or an EIN.<br>International clients mayuse different values.|String||
|FirstName|C|First name of the Dealer|String||
|LastName|C|Last name of the Dealer|String||
|CompanyName|C|Companyname of the Dealer|String||
|PrimaryEmail|C|Primaryemail address of the Dealer or Customer|String||
|SecondaryEmail|C|Secondaryemail address of the Dealer or Customer|String||
|IsCustomer|C|Flag indicating whether or not this dealer is flagged<br>as a customer|String|0 = false, -1 = true<br>*see note below|



* At least one of the conditional arguments must have a value to search on 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes(Returned data is filtered byauthorized countries)|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

If no records are returned as a result of the search, the system will return an empty datatable. 

##### <u>IsCustomer Flag</u> 

When this flag is set to a non-zero value, the system will filter the output by only returning records where this flag is set to TRUE in the system (i.e.: Customer records only). If this flag is omitted, OR set to 0 (false), the system will perform NO filtering by this flag. All customer and member records will be returned that match the other criteria that was used. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|Account|varchar|Internal Firestorm® account number|
|Active|smallint|Flag to indicate if the dealer record is flagged as active or not.<br>(NOTE: This is not the same as the BCQ flag!) 0 = not active, -1 =<br>Active. This field should only be used if your specific compensation<br>plan makes use of it. Ifyou are unsure,call support.|
|AffiliateSponsoringDealerID|int|If this is a CUSTOMER who was sponsored by another customer, this<br>is the DealerID of the sponsoring customer. Will only be populated<br>for affiliate records.|
|AllowWebAccess|smallint|Flag to indicate if this dealer is to be allowed to log into the virtual<br>office|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 30 | 317 

Firestorm® Web Services API | Version 2.2.33 

|APDealershipNumber|int|When the default placement web tool is used to set up a default<br>|
|---|---|---|
|||placement for new enrollments, this is the dealership number to use<br>for thoseplacements(NOT the same as a dealerhsipID!)|
|APLineage|char|When the default placement web tool is used to set up a default<br>placement for new enrollments for BINARY systems, this will be the<br>lineage to use. Valid values are “L” or  “R”(left or right)|
|APPlacementDealerID|int|When the default placement web tool is used to set up a default<br>placement for new enrollments, This is the Dealer ID of the<br>placement position. This field in combination witl<br>APDealershipNumber is used to derive the DealershipID.|
|BirthDate|datetime||
|CellPhone|nvarchar||
|CompanyName|nvarchar||
|CurrencyTypeID|int|Default currency type for this Dealer. Values are stored in<br>tblCurrencyType.CurrencyTypeID|
|CustomerStatusID|int|Status code for the customer. Values are stored in<br>tblCustomerStatus.CustomerStatusID|
|CustomerTypeID|int|FK for tblCustomerType|
|DateEmailPrimaryLastValidated|datetime|When email validation is in use, this is the date this email address<br>was last validated|
|DateExported|datetime|DO NOT USE|
|DealerID|int|Unique identifier for this dealer. Generated byFirestorm®|
|DealerStatusCodeID|int|Status code for the DEALER (non-customer aka Member). FK to<br>tblDealerStatusCode|
|DealerURL|varchar|Replicated website name.(This is NOT a fully qualified URL)|
|DEFSponsorDealerID|int|When the default sponsor web tool is being used, this field will<br>contain the default sponsoringdealer ID specified bythat tool.|
|DEFSponsorDealershipNumber|int|When the default sponsor web tool is being used, this field will<br>contain the default dealership number (not DealershipID!) of the<br>sponsoringdealer specified bythat tool.|
|DeleteBy|varchar|DO NOT USE|
|Deleted|smallint|DO NOT USE|
|DeleteDate|datetime|DO NOT USE|
|EMailFormatTextOnly|smallint|Flag to indicate that the Dealer has requested email to be sent as<br>text only (no HTML) (0 = false,non-zero = true)|
|EmailOptOutGlobal|smallint|Flag to indicate this use has requested that no email be sent (0 =<br>false,non-zero = true)|
|EmailOptOutUpline|smallint|Flag to indicate this use has requested that no email from their<br>upline be sent(0 = false,non-zero = true)|
|EmailPrimary|nvarchar|Main email address|
|EmailPrimaryValidated|smallint|Flag to indicate that this email has been validated. Only used if<br>email validation engine is turned on)|
|EmailPrimaryValidationResult|varchar|The result of the email validation expressed as a  message|
|EmailSecondary|nvarchar|Second email address|
|EnrollDate|datetime|Date that thisperson enrolled into the system|
|FaxPhone|nvarchar||
|Firstname|nvarchar||
|HomePhone|nvarchar||
|IsCustomer|smallint|Flag to indicate that this dealer record is a CUSTOMER (non-|
|||member)|
|IsSentinal|smallint|DO NOT USE|
|LastName|nvarchar||
|MailAddress1|nvarchar|Mailingaddress is also used as the default billingaddress|
|MailAddress2|nvarchar|“|
|MailCity|nvarchar|“|
|“MailCountry|nvarchar|“|
|MailState<br>|nvarchar<br>|“<br>|
|MailZip<br>MiddlIitil|nvarchar<br>h|“|
|ena<br>NPO|nvarcar<br>smallint|Flagto indicate that this is a Nonprofit organization|
|OldID|varchar|If this record was imported from another system, this field will<br>contain the uniue identifier for this record in the old sstem|
|Password|nvarchar|q y.<br>Dealer’spassword used when logginginto the system|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 31 | 317 

Firestorm® Web Services API | Version 2.2.33 

|PayCurrencyTypeID|int|Type of currency this dealer wishes to be paid in. FK to<br>tblCurrencyType)|
|---|---|---|
|ShipAddress1|nvarchar||
|ShipAddress2|nvarchar||
|ShipCity|nvarchar||
|ShipCountry|nvarchar||
|ShipState|nvarchar||
|ShipZip|nvarchar||
|SMSTextInfoAlerts|smallint|Flagto enable/disable SMS Alerts|
|SMSTextOnEnroll|smallint|Flag to enable/disable SMS notification when someone enrolls in<br>their downline|
|SMSTextOnOrder|smallint|Flag to enable/disable SMS notification when an order is placed in<br>their downline|
|SMSTextOptOut|smallint|Flagto opt out of all SMS texts|
|SponsoringDealerID|int|If this is a customer, this is the sponsoring member’s dealer ID. If<br>this is NOT a customer, use the field “StructureSponsoringDealerID”<br>below to determine the sponsor of the member.|
|SubAccount|varchar|Sub account number used internallybyFirestorm®|
|TaxExempt|smallint|Flagindicatingthat this dealer is tax exempt or not|
|TaxPayerNumber|nvarchar|SSN/EIN or some othergovernment ID|
|UseEWalletOnly|int|Flag to indicate that this person does not want any paper checks.<br>Theywill retrieve their commissions from the e-wallet system.|
|WebCatalogueID|int|DO NOT USE|
|WebGreeting|ntext|Greetingto be used on the dealer’s replicated website|
|WebPhoto|image|DO NOT USE. If you want to see this dealer’s photo, use the web<br>tool GetDealerImage.aspx|
|WebProductID|int|DO NOT USE|
|CustomerType|Nvarchar|Code representing type of customer (RETAIL, PREFERRED, etc) These<br>values are configured through the administrative interface for<br>Firestorm®|
|CustomerStatus|Nvarchar|Code representingthe status of a customer(Active,etc)|
|StructureSponsoringDealerID||For a member, this is the dealer that sponsored them into the<br>system|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 32 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.GetDealerDetailExtended 

Searches for a dealer record based on the passed in search criteria. The system will pull all matching records and will return a datatable that will have an entry for each matching record. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|C|The unique DealerID you are searching for|Numeric|Any non-negative<br>DealerID|
|TaxPayerNumber|C|Generally in the USA, this is a SSN or an EIN.<br>International clients mayuse different values.|String||
|FirstName|C|First name of the Dealer|String||
|LastName|C|Last name of the Dealer|String||
|CompanyName|C|Companyname of the Dealer|String||
|PrimaryEmail|C|Primaryemail address of the Dealer or Customer|String||
|SecondaryEmail|C|Secondaryemail address of the Dealer or Customer|String||
|IsCustomer|C|Flag indicating whether or not this dealer is flagged<br>as a customer|String|0 = false, -1 = true<br>* see note below|
|OldID|C|If the data in the system was imported  from another<br>software vendor, then this field it the unique ID that<br>was assigned to this dealer on the OLD system|String|Dependant on the<br>format used by the<br>old system|
|HomePhone|C|Homephone number(format must match exactly)|||
|WorkPhone|C|Workphone number(format must match exactly)|||
|FaxPhone|C|Faxphone number(format must match exactly)|||
|CellPhone|C|Cellphone number(format must match exactly)|||



* At least one of the conditional arguments must have a value to search on 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes(Returned data is filtered byauthorized countries)|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

If no records are returned as a result of the search, the system will return an empty datatable. 

##### <u>IsCustomer Flag</u> 

When this flag is set to a non-zero value, the system will filter the output by only returning records where this flag is set to TRUE in the system (i.e.: Customer records only). If this flag is omitted, OR set to 0 (false), the system will perform NO filtering by this flag. All customer and member records will be returned that match the other criteria that was used. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|Account|varchar|Internal Firestorm® account number|
|Active|smallint|Flag to indicate if the dealer record is flagged as active or not.<br>(NOTE: This is not the same as the BCQ flag!) 0 = not active, -1 =<br>Active. This field should only be used if your specific compensation<br>plan makes use of it. Ifyou are unsure,call support.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 33 | 317 

Firestorm® Web Services API | Version 2.2.33 

|AffiliateSponsoringDealerID|int|If this is a CUSTOMER who was sponsored by another customer, this<br>|
|---|---|---|
|||is the DealerID of the sponsoring customer. Will only be populated<br>for affiliate records.|
|AllowWebAccess|smallint|Flag to indicate if this dealer is to be allowed to log into the virtual<br>office|
|APDealershipNumber|int|When the default placement web tool is used to set up a default<br>placement for new enrollments, this is the dealership number to use<br>for thoseplacements(NOT the same as a dealerhsipID!)|
|APLineage|char|When the default placement web tool is used to set up a default<br>placement for new enrollments for BINARY systems, this will be the<br>lineage to use. Valid values are “L” or  “R”(left or right)|
|APPlacementDealerID|int|When the default placement web tool is used to set up a default<br>placement for new enrollments, This is the Dealer ID of the<br>placement position. This field in combination witl<br>APDealershipNumber is used to derive the DealershipID.|
|BirthDate|datetime||
|CellPhone|nvarchar||
|CompanyName|nvarchar||
|CurrencyTypeID|int|Default currency type for this Dealer. Values are stored in<br>tblCurrencyType.CurrencyTypeID|
|CustomerStatusID|int|Status code for the customer. Values are stored in<br>tblCustomerStatusCustomerStatusID|
|CustomerTypeID|int|.<br>FK for tblCustomerType|
|DateEmailPrimaryLastValidated|datetime|When email validation is in use, this is the date this email address<br>was last validated|
|DateExported|datetime|DO NOT USE|
|DealerID|int|Unique identifier for this dealer. Generated byFirestorm®|
|DealerStatusCodeID|int|Status code for the DEALER (non-customer aka Member). FK to<br>tblDealerStatusCode|
|DealerURL|varchar|Replicated website name.(This is NOT a fully qualified URL)|
|DEFSponsorDealerID|int|When the default sponsor web tool is being used, this field will<br>contain the default sponsoringdealer ID specified bythat tool.|
|DEFSponsorDealershipNumber|int|When the default sponsor web tool is being used, this field will<br>contain the default dealership number (not DealershipID!) of the<br>sponsoringdealer specified bythat tool.|
|DeleteBy|varchar|DO NOT USE|
|Deleted|smallint|<br>DO NOT USE|
|DeleteDate|datetime|DO NOT USE|
|EMailFormatTextOnly|smallint|Flag to indicate that the Dealer has requested email to be sent as<br>text only (no HTML) (0 = false,non-zero = true)|
|EmailOptOutGlobal|smallint|Flag to indicate this use has requested that no email be sent (0 =<br>false,non-zero = true)|
|EmailOptOutUpline|smallint|Flag to indicate this use has requested that no email from their<br>upline be sent(0 = false,non-zero = true)|
|EmailPrimary|nvarchar|Main email address|
|EmailPrimaryValidated|smallint|Flag to indicate that this email has been validated. Only used if<br>email validation engine is turned on)|
|EmailPrimaryValidationResult|varchar|The result of the email validation expressed as a  message|
|EmailSecondary|nvarchar|Second email address|
|EnrollDate|datetime|Date that thisperson enrolled into the system|
|FaxPhone<br>Firstname|nvarchar<br>nvarchar||
|HomePhone|nvarchar||
|IsCustomer|smallint|Flag to indicate that this dealer record is a CUSTOMER (non-<br>b)|
|IsSentinal|smallint|memer<br>DO NOT USE|
|LastName|nvarchar||
|MailAddress1|nvarchar|Mailingaddress is also used as the default billingaddress|
|MailAddress2|nvarchar|“|
|MailCity|nvarchar|“|
|MailCountry|nvarchar|“|
|MailState|nvarchar|“|
|MailZip|nvarchar|“|
|MiddleInitial|nvarchar||



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 34 | 317 

Firestorm® Web Services API | Version 2.2.33 

|NPO|smallint|Flagto indicate that this is a Nonprofit organization|
|---|---|---|
|OldID|varchar|If this record was imported from another system, this field will<br>contain the unique identifier for this record in the old system.|
|Password|nvarchar|Dealer’spassword used when logginginto the system|
|PayCurrencyTypeID|int|Type of currency this dealer wishes to be paid in. FK to<br>tblCurrencyType)|
|ShipAddress1|nvarchar||
|ShipAddress2|nvarchar||
|ShipCity|nvarchar||
|ShipCountry|nvarchar||
|ShipState|nvarchar||
|ShipZip|nvarchar||
|SMSTextInfoAlerts|smallint|Flagto enable/disable SMS Alerts|
|SMSTextOnEnroll|smallint|Flag to enable/disable SMS notification when someone enrolls in<br>their downline|
|SMSTextOnOrder|smallint|Flag to enable/disable SMS notification when an order is placed in<br>their downline|
|SMSTextOptOut|smallint|Flagto opt out of all SMS texts|
|SponsoringDealerID|int|If this is a customer, this is the sponsoring member’s dealer ID. If<br>this is NOT a customer, use the field “StructureSponsoringDealerID”<br>below to determine the sponsor of the member.|
|SubAccount|varchar|Sub account number used internallybyFirestorm®|
|TaxExempt|smallint|Flagindicatingthat this dealer is tax exempt or not|
|TaxPayerNumber|nvarchar|SSN/EIN or some othergovernment ID|
|UseEWalletOnly|int|Flag to indicate that this person does not want any paper checks.<br>Theywill retrieve their commissions from the e-wallet system.|
|WebCatalogueID|int|DO NOT USE|
|WebGreeting|ntext|Greetingto be used on the dealer’s replicated website|
|WebPhoto|image|DO NOT USE. If you want to see this dealer’s photo, use the web<br>tool GetDealerImage.aspx|
|WebProductID|int|DO NOT USE|
|CustomerType|Nvarchar|Code representing type of customer (RETAIL, PREFERRED, etc) These<br>values are configured through the administrative interface for<br>Firestorm®|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 35 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.GetDealerDetailExtended2 

Searches for a dealer record based on the passed in search criteria. The system will pull all matching records and will return a datatable that will have an entry for each matching record. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|C|The unique DealerID you are searching for|Numeric|Any non-negative<br>DealerID|
|TaxPayerNumber|C|Generally in the USA, this is a SSN or an EIN.<br>International clients mayuse different values.|String||
|FirstName|C|First name of the Dealer|String||
|LastName|C|Last name of the Dealer|String||
|CompanyName|C|Companyname of the Dealer|String||
|PrimaryEmail|C|Primaryemail address of the Dealer or Customer|String||
|SecondaryEmail|C|Secondaryemail address of the Dealer or Customer|String||
|IsCustomer|C|Flag indicating whether or not this dealer is flagged<br>as a customer|String|0 = false, -1 = true<br>* see note below|
|OldID|C|If the data in the system was imported  from another<br>software vendor, then this field it the unique ID that<br>was assigned to this dealer on the OLD system|String|Dependant on the<br>format used by the<br>old system|
|HomePhone|C|Homephone number(format must match exactly)|String||
|WorkPhone|C|Workphone number(format must match exactly)|String||
|FaxPhone|C|Faxphone number(format must match exactly)|String||
|CellPhone|C|Cellphone number(format must match exactly)|String||
|IsDealer|C|Non Customer records only|Numeric|0 = false,-1 = true|
|IsActive|C|Active Records only|Numeric|0 = false,-1 = true|



* At least one of the conditional arguments must have a value to search on 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes(Returned data is filtered byauthorized countries)|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

If no records are returned as a result of the search, the system will return an empty datatable. 

##### <u>IsCustomer Flag</u> 

When this flag is set to a non-zero value, the system will filter the output by only returning records where this flag is set to TRUE in the system (i.e.: Customer records only). If this flag is omitted, OR set to 0 (false), the system will perform NO filtering by this flag. All customer and member records will be returned that match the other criteria that was used. 

##### <u>IsDealer Flag</u> 

When this flag is set to a non-zero value, the system will filter the output by only returning records where the Dealer record is NOT flagged as a customer (i.e.: this will filter out ALL customer records). If this flag is omitted, OR set to 0 (false), the system will perform NO filtering by this flag. All customer and member records will be returned that match the other criteria that was used. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 36 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### <u>IsActive Flag</u> 

When this flag is set to a non-zero value, the system will filter the output by only returning records where the Dealer record is flagged as being Active. If this flag is omitted, OR set to 0 (false), the system will perform NO filtering by this flag. All records will be returned that match the other criteria that was used. 

##### **<u>Return Values</u>** 

|Returned Data|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|Account|varchar|Internal Firestorm® account number|
|Active|smallint|Flag to indicate if the dealer record is flagged as active or not.<br>(NOTE: This is not the same as the BCQ flag!) 0 = not active, -1 =<br>Active. This field should only be used if your specific compensation<br>plan makes use of it. Ifyou are unsure,call support.|
|AffiliateSponsoringDealerID|int|If this is a CUSTOMER who was sponsored by another customer, this<br>is the DealerID of the sponsoring customer. Will only be populated<br>for affiliate records.|
|AllowWebAccess|smallint|Flag to indicate if this dealer is to be allowed to log into the virtual<br>office|
|APDealershipNumber|int|When the default placement web tool is used to set up a default<br>placement for new enrollments, this is the dealership number to use<br>for thoseplacements(NOT the same as a dealerhsipID!)|
|APLineage|char|When the default placement web tool is used to set up a default<br>placement for new enrollments for BINARY systems, this will be the<br>lineage to use. Valid values are “L” or  “R”(left or right)|
|APPlacementDealerID|int|When the default placement web tool is used to set up a default<br>placement for new enrollments, This is the Dealer ID of the<br>placement position. This field in combination witl<br>APDealershipNumber is used to derive the DealershipID.|
|BirthDate|datetime||
|CellPhone|nvarchar||
|CompanyName|nvarchar||
|CurrencyTypeID|int|Default currency type for this Dealer. Values are stored in<br>tblCurrencyType.CurrencyTypeID|
|CustomerStatusID|int|Status code for the customer. Values are stored in<br>tblCustomerStatus.CustomerStatusID|
|CustomerTypeID|int|FK for tblCustomerType|
|DateEmailPrimaryLastValidated|datetime|When email validation is in use, this is the date this email address<br>was last validated|
|DateExported|datetime|DO NOT USE|
|DealerID|int|Unique identifier for this dealer. Generated byFirestorm®|
|DealerStatusCodeID|int|Status code for the DEALER (non-customer aka Member). FK to<br>tblDealerStatusCode|
|DealerURL|varchar|Replicated website name.(This is NOT a fully qualified URL)|
|DEFSponsorDealerID|int|When the default sponsor web tool is being used, this field will<br>contain the default sponsoringdealer ID specified bythat tool.|
|DEFSponsorDealershipNumber|int|When the default sponsor web tool is being used, this field will<br>contain the default dealership number (not DealershipID!) of the<br>sponsoringdealer specified bythat tool.|
|DeleteBy|varchar|DO NOT USE|
|Deleted|smallint|DO NOT USE|
|DeleteDate|datetime|DO NOT USE|
|EMailFormatTextOnly|smallint|<br>Flag to indicate that the Dealer has requested email to be sent as<br>text only (no HTML) (0 = false,non-zero = true)|
|EmailOptOutGlobal|smallint|Flag to indicate this use has requested that no email be sent (0 =<br>false,non-zero = true)|
|EmailOptOutUpline|smallint|Flag to indicate this use has requested that no email from their<br>upline be sent(0 = false,non-zero = true)|
|EmailPrimary|nvarchar|Main email address|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 37 | 317 

Firestorm® Web Services API | Version 2.2.33 

|EmailPrimaryValidated|smallint|Flag to indicate that this email has been validated. Only used if<br>email validation enine is turned on)|
|---|---|---|
|EmailPrimaryValidationResult|varchar|g <br>The result of the email validation expressed as a  message|
|EmailSecondary<br>|nvarchar<br>|Second email address<br>|
|EnrollDate|datetime|Date that thisperson enrolled into the system|
|FaxPhone<br>Firstname|nvarchar<br>nvarchar||
|HomePhone|nvarchar||
|IsCustomer|smallint|Flag to indicate that this dealer record is a CUSTOMER (non-<br>member)|
|IsSentinal|smallint|DO NOT USE|
|LastName|nvarchar||
|MailAddress1|nvarchar|Mailingaddress is also used as the default billingaddress|
|MailAddress2|nvarchar|“|
|MailCity|nvarchar|“|
|MailCountry|nvarchar|“|
|MailState|nvarchar|“|
|MailZip|nvarchar|“|
|MiddleInitial|nvarchar||
|NPO|smallint|Flagto indicate that this is a Nonprofit organization|
|OldID|varchar|If this record was imported from another system, this field will<br>contain the unique identifier for this record in the old system.|
|Password|nvarchar|Dealer’spassword used when logginginto the system|
|PayCurrencyTypeID|int|Type of currency this dealer wishes to be paid in. FK to<br>tblCurrencyType)|
|ShipAddress1|nvarchar||
|ShipAddress2<br>ShipCity|nvarchar<br>nvarchar||
|ShipCountry|nvarchar||
|ShipState<br>|nvarchar<br>||
|ShipZip<br>SMSTextInfoAlerts|nvarchar<br>smallint|Flagto enable/disable SMS Alerts|
|SMSTextOnEnroll|smallint|Flag to enable/disable SMS notification when someone enrolls in<br>their downline|
|SMSTextOnOrder|smallint|Flag to enable/disable SMS notification when an order is placed in<br>their downline|
|SMSTextOptOut|smallint|Flagto opt out of all SMS texts|
|SponsoringDealerID|int|If this is a customer, this is the sponsoring member’s dealer ID. If<br>this is NOT a customer, use the field “StructureSponsoringDealerID”<br>below to determine the sponsor of the member.|
|SubAccount|varchar|Sub account number used internallybyFirestorm®|
|TaxExempt|smallint|Flagindicatingthat this dealer is tax exempt or not|
|TaxPayerNumber|nvarchar|SSN/EIN or some othergovernment ID|
|UseEWalletOnly|int|Flag to indicate that this person does not want any paper checks.<br>|
|||Theywill retrieve their commissions from the e-wallet system.|
|WebCatalogueID|int|DO NOT USE|
|WebGreeting|ntext|Greetingto be used on the dealer’s replicated website|
|WebPhoto|image|DO NOT USE. If you want to see this dealer’s photo, use the web<br>tool GetDealerImage.aspx|
|WebProductID|int|DO NOT USE|
|CustomerType|Nvarchar|Code representing type of customer (RETAIL, PREFERRED, etc) These<br>values are configured through the administrative interface for<br>Firestorm®|
|CustomerStatus|Nvarchar|<br>Code representing status of the customer (ACTIVE, TERMINATED,<br>etc) These values are configured through the administrative<br>interface for Firestorm®|
|StructureSponsoringDealerID|Int|The dealer id of the sponsor of this dealer.|
|UnilevelPlacementDealerID|Int|The dealer id of the unilevelplacement of this dealer.|
|UnilevelSponsorDealerID|Int|The dealer id of the unilevel sponsor of this dealer.|
|DealershipID|Int|The dealershipID of this dealer|
|PaidAsDealershipTypeID|Int|The paid-as DealershipTypeID of this dealers lowest numbered|
|||<br>dealership (typically position #1). If the dealer has multiple|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 38 | 317 

Firestorm® Web Services API | Version 2.2.33 

|||dealerships (structure positions) this value will only contain the<br>dealershipID of the lowest numbered dealership|
|---|---|---|
|PaidAsRankCode|Nvarchar|The code representingthe currentpaid as dealershipTypeID(rank)|



#### FirestormDealerWS.DealerSearch 

Searches for a dealer record based on the passed in search criteria. The system will pull all matching records and will return a datatable that will have an entry for each matching record. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|C|The unique DealerID you are searching for|Numeric|Any non-negative<br>DealerID|
|TaxPayerNumber|C|Generally in the USA, this is a SSN or an EIN.<br>International clients mayuse different values.|String||
|FirstName|C|First name of the Dealer|String||
|LastName|C|Last name of the Dealer|String||
|CompanyName|C|Companyname of the Dealer|String||
|PrimaryEmail|C|Primaryemail address of the Dealer or Customer|String||
|SecondaryEmail|C|Secondaryemail address of the Dealer or Customer|String||
|State|C|The ISO State code|String|Any valid state code<br>defined in the<br>Firestorm® system|
|DealerURL|C|The replicated website url for the dealer being<br>searched for|||



* At least one of the conditional arguments must have a value to search on 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes(Returned data is filtered byauthorized countries)|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

If no records are returned as a result of the search, the system will return an empty datatable. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|Account|varchar|Internal Firestorm® account number|
|Active|smallint|Flag to indicate if the dealer record is flagged as active or not.<br>(NOTE: This is not the same as the BCQ flag!) 0 = not active, -1 =<br>Active. This field should only be used if your specific compensation<br>plan makes use of it. Ifyou are unsure,call support.|
|AffiliateSponsoringDealerID|int|If this is a CUSTOMER who was sponsored by another customer, this<br>is the DealerID of the sponsoring customer. Will only be populated<br>for affiliate records.|
|AllowWebAccess|smallint|Flag to indicate if this dealer is to be allowed to log into the virtual<br>office|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 39 | 317 

Firestorm® Web Services API | Version 2.2.33 

|APDealershipNumber|int|When the default placement web tool is used to set up a default<br>|
|---|---|---|
|||placement for new enrollments, this is the dealership number to use<br>for thoseplacements(NOT the same as a dealerhsipID!)|
|APLineage|char|When the default placement web tool is used to set up a default<br>placement for new enrollments for BINARY systems, this will be the<br>lineage to use. Valid values are “L” or  “R”(left or right)|
|APPlacementDealerID|int|When the default placement web tool is used to set up a default<br>placement for new enrollments, This is the Dealer ID of the<br>placement position. This field in combination witl<br>APDealershipNumber is used to derive the DealershipID.|
|BirthDate|datetime||
|CellPhone|nvarchar||
|CompanyName|nvarchar||
|CurrencyTypeID|int|Default currency type for this Dealer. Values are stored in<br>tblCurrencyType.CurrencyTypeID|
|CustomerStatusID|int|Status code for the customer. Values are stored in<br>tblCustomerStatus.CustomerStatusID|
|CustomerTypeID|int|FK for tblCustomerType|
|DateEmailPrimaryLastValidated|datetime|When email validation is in use, this is the date this email address<br>was last validated|
|DateExported|datetime|DO NOT USE|
|DealerID|int|Unique identifier for this dealer. Generated byFirestorm®|
|DealerStatusCodeID|int|Status code for the DEALER (non-customer aka Member). FK to<br>tblDealerStatusCode|
|DealerURL|varchar|Replicated website name.(This is NOT a fully qualified URL)|
|DEFSponsorDealerID|int|When the default sponsor web tool is being used, this field will<br>contain the default sponsoringdealer ID specified bythat tool.|
|DEFSponsorDealershipNumber|int|When the default sponsor web tool is being used, this field will<br>contain the default dealership number (not DealershipID!) of the<br>sponsoringdealer specified bythat tool.|
|DeleteBy|varchar|DO NOT USE|
|Deleted|smallint|DO NOT USE|
|DeleteDate|datetime|DO NOT USE|
|EMailFormatTextOnly|smallint|Flag to indicate that the Dealer has requested email to be sent as<br>text only (no HTML) (0 = false,non-zero = true)|
|EmailOptOutGlobal|smallint|Flag to indicate this use has requested that no email be sent (0 =<br>false,non-zero = true)|
|EmailOptOutUpline|smallint|Flag to indicate this use has requested that no email from their<br>upline be sent(0 = false,non-zero = true)|
|EmailPrimary|nvarchar|Main email address|
|EmailPrimaryValidated|smallint|Flag to indicate that this email has been validated. Only used if<br>email validation engine is turned on)|
|EmailPrimaryValidationResult|varchar|The result of the email validation expressed as a  message|
|EmailSecondary|nvarchar|Second email address|
|EnrollDate|datetime|Date that thisperson enrolled into the system|
|FaxPhone|nvarchar||
|Firstname|nvarchar||
|HomePhone|nvarchar||
|IsCustomer|smallint|Flag to indicate that this dealer record is a CUSTOMER (non-|
|||member)|
|IsSentinal|smallint|DO NOT USE|
|LastName|nvarchar||
|MailAddress1|nvarchar|Mailingaddress is also used as the default billingaddress|
|MailAddress2|nvarchar|“|
|MailCity|nvarchar|“|
|MailCountry|nvarchar|“|
|MailState<br>|nvarchar<br>|“<br>|
|MailZip<br>MiddlIitil|nvarchar<br>h|“|
|ena<br>NPO|nvarcar<br>smallint|Flagto indicate that this is a Nonprofit organization|
|OldID|varchar|If this record was imported from another system, this field will<br>contain the uniue identifier for this record in the old sstem|
|Password|nvarchar|q y.<br>Dealer’spassword used when logginginto the system|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 40 | 317 

Firestorm® Web Services API | Version 2.2.33 

|PayCurrencyTypeID|int|Type of currency this dealer wishes to be paid in. FK to<br>tblCurrencyType)|
|---|---|---|
|ShipAddress1|nvarchar||
|ShipAddress2|nvarchar||
|ShipCity|nvarchar||
|ShipCountry|nvarchar||
|ShipState|nvarchar||
|ShipZip|nvarchar||
|SMSTextInfoAlerts|smallint|Flagto enable/disable SMS Alerts|
|SMSTextOnEnroll|smallint|Flag to enable/disable SMS notification when someone enrolls in<br>their downline|
|SMSTextOnOrder|smallint|Flag to enable/disable SMS notification when an order is placed in<br>their downline|
|SMSTextOptOut|smallint|Flagto opt out of all SMS texts|
|SponsoringDealerID|int|If this is a customer, this is the sponsoring member’s dealer ID. If<br>this is NOT a customer, use the field “StructureSponsoringDealerID”<br>below to determine the sponsor of the member.|
|SubAccount|varchar|Sub account number used internallybyFirestorm®|
|TaxExempt|smallint|Flagindicatingthat this dealer is tax exempt or not|
|TaxPayerNumber|nvarchar|SSN/EIN or some othergovernment ID|
|UseEWalletOnly|int|Flag to indicate that this person does not want any paper checks.<br>Theywill retrieve their commissions from the e-wallet system.|
|WebCatalogueID|int|DO NOT USE|
|WebGreeting|ntext|Greetingto be used on the dealer’s replicated website|
|WebPhoto|image|DO NOT USE. If you want to see this dealer’s photo, use the web<br>tool GetDealerImage.aspx|
|WebProductID|int|DO NOT USE|
|FullName|String|If the dealer has a company name defined then this value will be the<br>companyname. If not,it will contain both the First and Last name.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 41 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.SaveDealerDetail 

Updates a dealer record based on the passed in arguments. The system will validate passed in parameters and if everything is good, then the update will be applied. Any value not supplied will not be updated. 

|Method Definition<br>|<br>||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|DealerID of the member being updated|Numeric|Any valid existing<br>DealerID in the<br>system|
|LastName|N|Last name of the dealer|String||
|FirstName|N|First name of the dealer|String||
|MiddleInitial|N|Middle initial of the dealer|String||
|CompanyName|N|Company name for this dealer. Only use this value if<br>the member actually has a company! This value will<br>override the first/last name on commission checks.|String||
|ShipAddress1|N|ShippingAddress|String||
|ShipAddress2|N|“|String||
|ShipCity|N|“|String||
|ShipState|N|“|String||
|ShipZip|N|“|String||
|ShipCountry|N|“|String||
|MailAddress1|N|Mailing Address. Used as a default billing address in<br>the shoppingcart|String||
|MailAddress2|N|“|String||
|MailCity|N|“|String||
|MailState|N|“|String||
|MailZip|N|“|String||
|MailCountry|N|“|String||
|WorkPhone|N|Workphone number for the dealer|String||
|HomePhone|N|Homephone number for the dealer|String||
|FaxPhone|N|Faxphone number for the dealer|String||
|CellPhone|N|Cell phone number for the dealer. This value should<br>be required if the member wishes to receive SMS<br>texts from the system.|String||
|PrimaryEmail|N|Main email address to use for this dealer|String||
|SecondaryEmail|N|Secondaryemail address to use for this dealer|String||
|BirthDate|N|Date of birth for the dealer|String|Use format<br>MM/DD/YYYY|
|EmailOptOutUpline|N|Boolean flag to indicate the dealer does not wish to<br>receive emails from their upline. Used by the “Email<br>Your Downline” tool in the virtual office|String|0 = false<br>-1 = true|
|EmailOptOutGlobal|N|Boolean flag to indicate the dealer does not wish to<br>receive anyemails at all.|String|0 = false<br>-1 = true|
|EmailFormatTextOnly|N|Flag to indicate that this dealer wishes to receive all<br>emails in text format only|String|0 = false<br>-1 = true|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (The dealer record being edited must be in an authorized<br>country)|
|Fields|Yes(onlyauthorized fields maybe updated)|
|Max Records|No|



##### **<u>Additional Information</u>** 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 42 | 317 

Firestorm® Web Services API | Version 2.2.33 

This method will fail silently if any validations fail. This is by design and is for security purposes. If you experience a failure, please contact our support department for assistance, as all errors will be logged on our system. 

##### **<u>Return Values</u>** 

BOOLEAN – True = Success, False = Update Failed 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 43 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.GetDealerListByDealerIDRange 

Returns a list of Dealers that fall within the range specified by the arguments. The system will pull all matching records and will return a datatable that will have an entry for each matching record. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|StartDealerID|Y|The starting DealerID|String|Requires a numeric<br>DealerID|
|EndDealerID|Y|The ending DealerID|String|Requires a numeric<br>DealerID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes(Return data is filtered byauthorized countries)|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

The system will search for all dealer records whose ID number falls within the range specified. If matching records are found, a datatable will be returned with one record for each matching record. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|DealerID|integer|The DealerID of the member|
|CurrentRank|Nvarchar|The Current dealershiptype(payrank)of the dealer|
|LifetimeRank|Nvarchar|The highest dealership type (pay rank) ever achieved by the dealer.<br>Note that in some comp plans the lifetime rank could go down! Be<br>aware.|
|CurrentSequence|Nvarchar|Numeric representation of the currentpayrank|
|LifetimeSequence|Nvarchar|Numeric representation of the current lifetimepayrank|
|DealershipStatus|Nvarchar|Current status of the dealers position in the tree (ACTIVE, INACTIVE,<br>etc). These codes are set up in the administrative interface in<br>Firestorm®|
|IsCustomer|integer|Flagto indicate that this dealer record belongs to a customer|
|IsAffiliate|integer|Flag to indicate that this dealer record belongs to an affiliate (a<br>customer of a customer)|
|IsDistributor|integer|Flagto indicate that this dealer record belongs to a member|
|MailCountry|Nvarchar|ISO countrycode for the Dealer|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 44 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.UpdateTaxpayerNumber 

This call will update the unique taxpayer number for a dealer in the system. Please note that the new taxpayer number being assigned to the dealer must be unique in the system, or the update will be disallowed. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The DealerID of the record to be updated|Integer|Requires a numeric<br>DealerID that already<br>exists in the system|
|TaxPayerNumber|Y|The new taxpayer number for the specified dealer.<br>Please note that format is not enforced for this<br>value, as different countries use differing formats.<br>Please ensure that the passed in value is in the<br>appropriate format desired in your system (i.e:<br>dashes,spaces,etc)|String|Any non zero length<br>string value|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Web service user must be authorized to update data in the<br>countryon the dealer record)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The system will verify the existence of the requested DealerID, and if found, will perform the update of the TaxPayerNumber to the passed in value. 

##### **<u>Return Values</u>** 

BOOLEAN – True = Success, False = Update Failed 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 45 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.DealerLocator 

Provides access to the dealer locator engine used by the Firestorm® system. The system will take the provided zip code or other search parameters and will perform a search of the system to return a list of matching records. 

**Please note** : The dealer locator engine has an override capability that will allow a company to apply specific rules to filter the returned data set. The returned list of dealers from this web service will match the list returned by the regular system (i.e.: in the shopping cart). 

|Method Definitio|n<br>||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|SourceZipCode|C*|The zipcode of thepersonperformingthe search|String||
|LastName|C*|Last name of the distributor beingsearched for|String||
|MaxDistanceInMiles|C*|Maximum distance (in miles) from the<br>SourceZipCode|Numeric||
|MaxResults|C*|Maximum number of results to return|Numeric|Number of records<br>to return. This<br>number can be<br>overridden by the<br>configuration of the<br>web service itself.|
|FirstName|C*|First name of distributor beingsearched for|String||
|StateID|C*|The ISO state code to search for|String|Any value from<br>tblDealer.MailState|



* At least 1 search parameter must be provided. 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

Using the passed in criteria, the system will perform a search for dealer’s that meet the specified search parameters. If a zip code is present, it will be used to perform a geographic search for distributors that are within “MaxDistanceInMiles” from the source zip code. 

This web service uses the same dealer locator engine that the Firestorm® system uses, so the same rules apply. These rules include the maximum number of results, so whatever the system is configured for in regards to max results will also apply here (unless overridden by the web service configuration) 

##### <u>Sorting</u> 

The returned data set will be sorted as follows: 

```
IsDefaultDealer ASC, HasReplicatedSite DESC, MilesApart ASC, CurrMoRetail DESC,
Sequence DESC
```

##### **<u>Return Values</u>** 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 46 | 317 

Firestorm® Web Services API | Version 2.2.33 

|Returned Data|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ZipCode|String|Zipcode of distributor|
|MilesApart|Numeric|Number of miles from SourceZipCode|
|MailCity|String||
|State|String||
|DealerID|Numeric|Unique ID assigned byFirestorm® for this dealer|
|FirstName|String||
|LastName|String||
|HomePhone|String||
|WorkPhone|String||
|EmailPrimary|String||
|DealerURL|String|Actual replicated website name(not fully qualified) (i.e.: bob)|
|ReplicatedWebsiteURL|String|Fully qualified website URL constructed from the value stored<br>in tblControl.CompanyURL prepended to the value in<br>DealerURL.(i.e.: http://www.myco.com/bob)|
|StatusCode|String|Status of the members dealership position (stored in<br>tblDealershipStatus.Code) (ex: ACTIVE. INACTIVE,etc)|
|Sequence|Numeric|Numeric representation of the current pay rank of the<br>distributor. You may use this value to sort with to place the<br>result set into pay rank order. (higher ranks have higher<br>numbers).. This value is stored in tblDealershipType.Sequence|
|DealershipID|Numeric||
|HasReplicatedSite|Boolean|Flag to indicate that this dealer has a replicated website. (0 =<br>No website,non-zero = Has an active replicated site)|
|IsDefaultDealer|Boolean|Flag to indicate that this is the default dealer record. This<br>record can be included in the results when no results are<br>returned by the search. The system must be configured to<br>support this feature before this record will be returned.|
|IsQualified|Boolean|INTERNAL USE ONLY: If a custom qualification procedure has<br>been put in place to filter the results based on company<br>specific rules, this flag will indicate that this dealer has met<br>those requirements and should be included in the displayed<br>results from the search. The locator engine will remove any<br>records from the output that are flagged as not qualified IF a<br>qualification procedure is being used. Regardless, this flag will<br>always be set to -1 for all records returned.|
|CurrMoRetail|Double|Total retail sales for the current month for the dealer.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 47 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.GetUnpaidCommissions 

Returns the total amount of UNPAID (not on a check) commissions that are currently available in the Dealer’s account within the Firestorm® system. 

|Method Definition<br>Argument|Required|Description|Datatype|Valid Values|
|---|---|---|---|---|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The unique dealerID number toget results for|Numeric||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Web service caller must be authorized to retrieve data for the<br>countryspecified in the dealer’s record)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

Calculates the total available commissions currently in a dealer’s commission account. Only records that are available for payment will be included in the sum. 

##### **<u>Return Values</u>** 

Double - Sum of all available commissions 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 48 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.GetDealerCommissionsByDate 

Returns a data set of all commission records that have a date created that falls between the start and end date supplied in the call to this method. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The unique dealerID number to get results for|Numeric|Must be an existing<br>DealerID in the<br>system|
|StartDate|Y|Startingdate for the date range|Date||
|EndDate|Y|Ending date for the date range|Date|Must be greater than<br>start date|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

Time stamps for the start date will be set to 00:00:00 AM. 

Time stamp for the end date will be set to 11:59:59 PM. 

WARNING: This call will return ALL commission records for a dealer that fall within the requested date range, without regard to whether or not the commission was already paid (put on a check). DO NOT USE THIS DATA TO PAY COMMISSIONS! 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|CommissionID|Integer|Unique ID assigned by Frestorm®|
|TransactionLogID|Integer|FK to tblTransactionLog|
|CheckID|Integer|Check number this commission record was assigned to. FK to<br>tblCheck|
|DealershipID|Integer|DealershipID that this commission record was generated for|
|CommissionTypeID|Integer|FK to tblCommissionType. Look up the codes in this table to<br>determine the type of commission.(BINARY,UNILEVEL,etc)|
|DateCreated|Date|The date that this commission record was created for. In a<br>system that uses the concept of commission periods, this will<br>be the end date of the commission period. When a system<br>uses real time payouts, this wil be the actual date and time<br>the commission record was created. If you need to absolutely<br>know the time a given record was actually created, used the<br>field “ActualCreateDate”|
|Threshold|Integer|LEGACY – DO NOT USE|
|Amount|Double|Amount of the commission check. This amount is in the base<br>currencyof the system.|
|LeftVolume|Double|LEGACY – DO NOT USE|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 49 | 317 

Firestorm® Web Services API | Version 2.2.33 

|CenterVolume|Double|LEGACY – DO NOT USE|
|---|---|---|
|RightVolume|Double|LEGACY – DO NOT USE|
|PersonalVolume|Double|LEGACY – DO NOT USE|
|PayoutCapInEffect|Integer|LEGACY – DO NOT USE|
|PayoutCapPointValue|Double|LEGACY – DO NOT USE|
|EndOfCycle|Smallint|LEGACY – DO NOT USE|
|Comment|String|Descriptive comment relating to this commission. Custom<br>written commissions will use this field extensively.|
|OrderID|Integer|If this commission was generated from an order, this field will<br>contain the order ID.|
|ClawbackCommissionID|Integer|If this commission has been clawed back (voided), this field<br>will contain the offsettingcommission record’s CommissionID|
|DealershipTypeCode|String|The current pay rank of the dealership receiving this<br>commission.|
|OnQualificationHold|Smallint|Flag to indicate that this commission is not currently eligible<br>to be included on a check(on hold)|
|QualificationReleaseDate|Date|Contains the date that the commission record was release<br>from being on qualification hold. If the commission was never<br>on hold,this field will be empty.|
|ParentCommissionID|Integer|If this commission is a child of another commission record,<br>this field will contain the CommissionID of theparent record.|
|CompanyPayCapProcessed|Smallint|LEGACY – DO NOT USE|
|LevelNumber|Integer|IF this is a level payout, (i.e.: Multilevel orUnilevel), this is the<br>level of theperson’s downline that thepayment came from|
|PercentagePaid|Float|If this is a percentage based payout, this field will contain the<br>percentage of field “VolumePaidOn”that was used to<br>calculate the commission. Not all commission records will<br>have this value.|
|VolumePaidOn|Double|The amount of volume that was used as the basis for the<br>commission payment. Not all commission records will have<br>this value.|
|PaidFromDealerID|Integer|If this commission record was paid because of a purchase or<br>action of another dealer, this field will contain the DealerID of<br>that person. (i.e.: a sponsor commission. This field would then<br>contain the DealerID of thepersonallysponsored dealer)|
|IsCustomerCommission|Smallint|In the RARE event of a company paying a commission to a<br>customer, if this is a commission for a customer, then this<br>field is used as a flag to indicate that this is a customer<br>commission. (0 = not a customer commission, non-zero = Is a<br>customer commission)|
|CustomerDealerID|Integer|In the RARE event of a company paying a commission to a<br>customer, if this is a commission for a customer, then that<br>customer’s DealerID will be in this field.|
|FundsTransferTxn|Smallint|If this is a commission record created as part of a funds<br>trancfer from one dealer to another, this flag will indicate<br>that. MAKE SURE you understand funds transfers before you<br>use this field for any reason! 0 = not a funds transfer, non-<br>zero = ispart of a funds transfer|
|DateExported|Date|Date and time this record was exported to a third party<br>payment system. Maynot be used on all systems.|
|ActualCreateDate|Date|Date and timestamp that this commission record was created<br>in the system. This value is always set to the current date and<br>time when the record is created, unlike the “DateCreated”<br>field which is used to ensure the commission record falls into<br>the correct commissionperiod.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 50 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.SaveDealerOption 

Allows a remote system to add and update dealer custom fields (known as “Dealer Options”) in the Firestorm® system. These fields are used in many implementation to control company specific attributes of the compensation plan. However, they can be used to track almost any value not normally tracked by Firestorm®. Each field may store up to 10 different values. The meaning of each value will depend on the implementation of the system. Please consult your compensation plan to ensure you are using correct field names and values. 

|Method Defini<br>|tion<br>||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The dealer ID of the person who record will be<br>updated|Numeric|Any DealerID that<br>exists in the system|
|OptionName|Y|The name of the option to be edited / assigned|String|Any valid option that<br>exists in<br>tblOption.Code|
|User1|Y|Value to store in this field|String|1. Valid value<br>2. Zero length to<br>delete<br>3. “NOUPDATE” to<br>saveprevious value|
|User2|Y|Value to store in this field|String|“|
|User3|Y|Value to store in this field|String|“|
|User4|Y|Value to store in this field|String|“|
|User5|Y|Value to store in this field|String|“|
|User6|Y|Value to store in this field|String|“|
|User7|Y|Value to store in this field|String|“|
|User8|Y|Value to store in this field|String|“|
|User9|Y|Value to store in this field|String|“|
|User10|Y|Value to store in this field|String|“|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Record being edited must be in a country the web service caller<br>is authorized for)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

If the option code is not currently assigned to the Dealer’s record, then it will be assigned with the values specified in User1 thru User10. 

If the option code is already assigned to the Dealer, then the values will be updated with the values passed in User1 thru User10. 

**WARNING:** This update will update ALL user fields. If you wish to preserve prior values you must pass in the value of “NOUPDATE” in any UserX field you do not wish to update!! 

If a zero length string is passed in one of the UserX fields, the corresponding value on the dealer’s record will be removed. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 51 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **<u>Return Values</u>** 

BOOLEAN: True = Update / Assign was successful, False = Update / Assign Failed. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 52 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.GetDealerOptions 

Returns a list of option codes (custom fields) assigned to a given Dealer that fall within the range The system will pull all matching records and will return a datatable that will have an entry for each matching record. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The DealerID of the person to check|String|Requires a numeric<br>DealerID|
|OptionName|N|The option code to check for. If you wich to see ALL<br>option records assigned to this dealer, pass an<br>emptystringin this argument.|String|A valid option code<br>as defined in<br>Firestorm®|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes(The dealer must exist in an authorized country)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

An option can also be classified as a custom field that is created by the administrator of the system and use to store up to 10 different values for each option. These values are not used by the standard Firestorm® system in any way. The only time they would come into play would be as a company specific need to track some form of data not normally tracked by Firestorm®. 

There is no limit to the number of options that may be assigned to a given dealer. 

When this capability is being leveraged, the definition of what each user value will represent will be defined as part of the overall design of the integration. 

For the DealerID passed, the system will pull all option records and their values that have been assigned to the Dealer. 

If the OptionName argument is used, the system will only return the assigned records that match the requested option. 

To see all options assigned to a given dealer, simply pass in an empty string in the “OptionName” argument. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|OptionID|integer|The unique ID assigned byFirestorm® to this option code|
|Code|string|String representing the code. This is created by the administrator in<br>Firestorm®|
|Description|String|A general description of the code and what it is intended for.<br>Entered bythe administrator in Firestorm®|
|User1|String|User specific data|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 53 | 317 

Firestorm® Web Services API | Version 2.2.33 

|User2|String|User specific data|
|---|---|---|
|User3|String|User specific data|
|User4|String|User specific data|
|User5|String|User specific data|
|User6|String|User specific data|
|User7|String|User specific data|
|User8|String|User specific data|
|User9|String|User specific data|
|User10|string|User specific data|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 54 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.GetCustomerListByDealerID 

Returns a list of Dealers that fall within the range specified by the arguments. The system will pull all matching records and will return a datatable that will have an entry for each matching record. 

|Method Definition<br><br>||||
|---|---|---|---|
|Argument<br>Required|Description|Datatype|Valid Values|
|Token<br>Y|SecurityToken assigned toyou bysupport|String||
|Context<br>Y|Context value assigned toyou bysupport|String||
|DealerID<br>Y|The starting DealerID|String|Requires a numeric<br>DealerID|
|EnrolledAfter<br>Y|A date/time stamp. This is used to filter out any<br>customer records that enrolled after this date|String|Format:<br>MM/dd/yyyy<br>hh:mm:ss tt<br>Example:<br>01/23/2019 11:24:15<br>AM|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes(Return data is filtered byauthorized countries)|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

The system will search for all customer records that were sponsored by the provided member DealerID. If matching records are found, a datatable will be returned with one record for each matching record. 

If an “EnrolledAfter” date is provided, any customer who enrolled prior to the specified date will be excluded from the returned datatable. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|MemberID|Integer|DealerID of the customer|
|Affiliate|String|Yes or “”. If this person is an affiliate (a customer of a customer)<br>then this field will contain the word “yes”. If they are not an affiliate,<br>then they are a direct customer of a member and the field will be<br>blank.|
|LastName|String|Last name|
|Firstname|String|First name|
|CompanyName|String|Companyname ifpresent|
|Rank|String|The type of customer. These types are configured in the Firestorm®<br>admin application and could be anything. Typical example values are<br>RETAIL, PREFERRED or AFFILIATE. Remember that these values are<br>company specific and could be different (or may change if the<br>companydecides to change the customer type)|
|Status|String|Customer status code. Typically ACTIVE or N/A. Again this status<br>code is configurable within Firestorm® and is companyspecific.|
|Email|String|Primaryemail address|
|Phone|String|Primary phone number as entered bythe customer|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 55 | 317 

Firestorm® Web Services API | Version 2.2.33 

|Name|String|Full name of the customer, last name then first name (i.e.: “Smith,<br>Joe”)|
|---|---|---|
|MailCity|String|MailingAddress element|
|MailState|String|MailingAddress element|
|MailCountry|String|MailingAddress element|
|MailAddress1|String|MailingAddress element|
|MailAddress2|String|MailingAddress element|
|MailZip|String|MailingAddress element|
|EmailOptOutGlobal|Boolean|0 = The customer has NOT opted out of email communications from<br>the company<br>-1 = the customer HAS opted out of email communications from the<br>company|
|EmailOptOutUpline|Boolean|0 = The customer has NOT opted out of email communications from<br>their sponsor and their sponsor’s upline<br>-1 = The customer HAS opted out of email communications from<br>their sponsor and their sponsor’s upline|
|EnrollDate|Date|The date and time thisperson enrolled(set upan account)|
|DisplayEmail|String|If the customer has not opted out of any email communications<br>then this field will contain their email address (if they entered one)<br>that may be used to send emails.<br>WARNING: If the customer has opted out of EITHER form of emails,<br>then this field will contain the string “Opted Out” and you would<br>then need to check the individual opt out flags to see if you can<br>send an email. In this case you will need to get the email address<br>from the “Email” field.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 56 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.ActivateDealer 

This method will allow a remote caller to Activate a dealer record in Firestorm. This should be used when a dealer who has been previously DeActivated needs to be Re-Activated for any reason. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The dealer ID to activate|Integer|Anyvalid DealerID|
|Comment|Y|An explanation or reason for the activation. This<br>value will be stored in the Dealer History for the<br>specified dealer and will be visible to administrative<br>personnel.|String||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Dealer’s MailCountry must be in an authorized country for the<br>caller)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This method will Activate a Firestorm dealer and record an entry in the Dealer History for the specified dealer. No <u>additional actions will be taken. If your company has additionaly processes that must occur when a dealer is</u> Activated for any reason, it will be your responsibility to make sure the required additional actions are performed. 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

##### Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ID>integer</ID>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
```

```
</FIRESTORMRESULT>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 57 | 317 

Firestorm® Web Services API | Version 2.2.33 

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|Integer||The Dealer ID of the dealer that was activated in Firestorm|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 58 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.DeActivateDealer 

This method will allow a remote caller to deactivate a dealer record in Firestorm. Additionally, the caller will also be able to optionally deactivate all of the specified dealer’s dealership records, rollup any sponsorships that are attached to the dealer, cancel the dealer’s recurring orders, as well as disable login access to the backoffice and shopping cart. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The dealer ID to deactivate|Integer|Anyvalid DealerID|
|Comment|Y|An explanation or reason for the activation. This<br>value will be stored in the Dealer History for the<br>specified dealer and will be visible to administrative<br>personnel.|String||
|RollSponsorships|Y|A boolean value indicating whether or not to roll up<br>the sponsorships of the dealers’s dealership records<br>to the next upline dealership with a Firestorm Status<br>of ACTIVE. This will only take place if the parameter<br>NewDealershipStatusCode contains a valid value.|Boolean|True/False|
|NewDealershipStatusCode|Y|A string value representing the status code that the<br>dealer’s dealership records should be set to.<br>Specifying a value in this field will deactivate the<br>dealer’s dealership records and change their<br>statuses to the specified value.|String|Any Dealership<br>Status code that<br>exists in Firestorm|
|CancelRecurringOrders|Y|A boolean value indicating whether or not to disable<br>all of the specified dealer’s recurringorders.|Boolean|True/False|
|CancelWebAccess|Y|A boolean value indicating whether or not to disable<br>the dealer’s ability to log in to the Firestorm<br>Backoffice and Firestorm ShoppingCart.|Boolean|True/False|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Dealer’s MailCountry must be in an authorized country for the<br>caller)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

<u>Deactivating Attached Dealerships – If a value for the parameter NewDealershipStatusCode is specified, all of the</u> dealer’s attached dealership records will be deactivated and have their status codes set to the specified value. 

<u>Rollup Sponsorships – If you choose to deactivate the dealership recrods for a dealer, you may also optionally roll</u> up the sponsorships for those dealership records by passing a value of True for the parameter RollSponsorships. The system will take the sponsorships for each dealership record deactivated and roll them upline to the next dealership that has a status of ACTIVE. 

<u>Dealership Status Codes – For a complete list of available Dealership Status Code available in Firestorm, please</u> contact Firestorm Support 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 59 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

##### Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ID>integer</ID>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|Integer||The Dealer ID of the dealer that was activated in Firestorm|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 60 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.GetRankWidgetData 

This method will allow a remote caller to pull the rank requirements for a given member with all rules governing rank advancement for that particular rank. The rules (with requirements) are returned along with the member’s current status for each requirement. The system will also return a percentage complete for each rule. 

_NOTE: This function is used in conjunction with FirestormDealerWS.GetRankWidgetRankPath() to obtain DealershipTypeIDs to make multiple calls to this function._ 

|Method Definition|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|Security Token assigned to you by<br>support|String||
|Context|Y|Context value assigned to you by<br>support|String||
|RequestedDealerID|Y|The DealerID of the member to pull<br>information for|Integer|Any valid DealerID|
|RequestedDealershipTypeID|N|If information for a particular rank is<br>desired, the system will accept a<br>dealershiptypeID for a particular rank<br>for the given member. When this<br>value is used a payload will be<br>delivered containing the<br>RequestedDealerID’s eligibility for that<br>rank(DealershipTypeID)|Integer|Any valid DealershipID in the system.<br>Pass in a -1 if you only want information for<br>the Dealer’s current rank.<br>Obtain a listing of DealershipTypeIDs from<br>FirestormDealerWS.GetRankWidgetRankPath|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Dealer’s MailCountry must be in an authorized country for the<br>caller)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This function is intended to provide all the data needed to drive a rank advancement widget displayed on a members dashboard. Many third party applications require this data to be able to accurately represent a member’s current status as they advance towards a given sales rank (DealershipTypeID) in the Firestorm® system. 

Most system require a series of requirements (steps) to be met in order to advance to that rank. The system will return a complete list of requirements for the requested rank, along with the value the member has achieved towards that step. 

Upon a successful call, the system will return a complex XML document that contains all relevant data to be able to drive a report or dashboard widget in third party applications. 

##### **<u>Special Behaviors</u>** 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 61 | 317 

Firestorm® Web Services API | Version 2.2.33 

If a RequestedDealershipTypeID (Rank) is not passed in, the system will look up the DealershipType of the #1 position in the system, and will return results for that rank. This will in effect be the members current pay rank as defined by the last promotions run performed in the system. 

If a specific DealershipTypeID (Rank) is passed in, the system will pull the requirements for the requested rank and will return a payload describing the RequestedDealerID’s qualifications for that rank. This capability is useful for “looking ahead” to the next rank. Many rank widgets will show the current rank, but will also allow members to look at their qualifications for higher ranks to see where they are. 

##### **<u>Maintenance Requirements and Initial Requirements</u>** 

Many compensation plans will have multiple sets of requirements for the same rank based on whether or not that rank has ever been achieved by the member before. The returned document contains a node to indicate if the member is in “maintenance” mode. If they are, then you should display the maintenance set of requirements. If they are not in maintenance (i.e.: They are working towards achieving the rank for the first time), then you should display the initial requirements for the specified rank (DealershipTypeID). 

##### **<u>Motivational Messages</u>** 

The system will also return a motivational message for each rule being enforced in the rank requirements. The intent of this message is for you to make a determination as to which rule the member is closest to achieving and display the message to “push” them across the finish line. Note that the messages are completely configurable within Firestorm® and you should test them to ensure that there are no display issues with your application. 

##### **<u>Weighting</u>** 

Each requirement for a given rank can be assigned a weighting value in Firestorm® to indicate its difficulty level to achieve. This weighting value is used in the percentage complete calculations for each step and overall percentage completed towards a given rank. When this capability is used properly, it allows you to present an accurate “percentage complete” value for each requirement by weighting more difficult requirements appropriately. 

For example, a given rank may have 5 steps to achieve. By default, the system will assign a weighting factor of 20 to each step, so as all 5 steps are completed the percentage complete will go up in proportional increments, regardless of the difficulty of each step. If a person had completed steps 1-4 in this scenario, the percentage complete would be calculated as 80% 

However, lets say that step 5 is really the most difficult to achieve so weighting factors of 10 are applied to steps 1-4, and a weighting factor of 60 is applied to step 5. If the user has completed steps 1-4 in this scenario, the percentage complete towards rank would be listed as 40%. A more accurate display that takes difficulty of each requirement into account to give the member a more realistic number. 

##### **<u>Sample Return XML</u>** 

This web service will return a complex XML document that will be embedded in the <FIRESTORMRESULT> envelope on a successful call. That portion of the document is described here: 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 62 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **Example Base XML Document containing Requirements** 

<PROMOTIONREQUIREMENTS> 

<DEALERID>NUMERIC</DEALERID> <REQUIREMENTS NumSets='1'> <DEALERSHIPTYPEID>NUMERIC</DEALERSHIPTYPEID> <RANKCODE>STRING</RANKCODE> <INMAINT>BOOLEAN</INMAINT> <RANKPERCENTAGECOMPLETE>FLOAT</RANKPERCENTAGECOMPLETE> <REQUIREMENTSTEPGROUPS NumRequirementStepGroups="2"> <REQUIREMENTSTEPGROUP> <PROMOTIONGROUPCODE>STRING</PROMOTIONGROUPCODE> <PROMOTIONGROUPDISPLAYNAME>STRING</PROMOTIONGROUPDISPLAYNAME> <PROMOTIONGROUPDESCRIPTION>STRING</PROMOTIONGROUPDESCRIPTION> <PROMOTIONGROUPHEXCOLORCODE>STRING</PROMOTIONGROUPHEXCOLORCODE> <PROMOTIONGROUPISMAINTENANCE>BOOLEAN</PROMOTIONGROUPISMAINTENANCE> <PROMOTIONGROUPSTEPGROUPS NumPromotionGroupSteps='1'> <PROMOTIONGROUPSTEPGROUP> <PROMOTIONGROUPSTEPGROUPCODE>STRING</PROMOTIONGROUPSTEPGROUPCODE> <PROMOTIONGROUPPERCENTAGECOMPLETE>FLOAT</PROMOTIONGROUPPERCENTAGECOMPLETE> <PROMOTIONSTEPS NumPromotionSteps='1'> <PROMOTIONSTEP> <PROMOTIONSTEPNUMBER>NUMERIC</PROMOTIONSTEPNUMBER> <PROMOTIONSTEPDESCRIPTION>STRING</PROMOTIONSTEPDESCRIPTION> <PROMOTIONSTEPREQUIREDVALUE>STRING</PROMOTIONSTEPREQUIREDVALUE> <PROMOTIONSTEPACTUALVALUE>STRING</PROMOTIONSTEPACTUALVALUE> <PROMOTIONSTEPPERCENTCOMPLETE>FLOAT</PROMOTIONSTEPPERCENTCOMPLETE> <PROMOTIONSTEPWEIGHTINGFACTOR>NUMERIC</PROMOTIONSTEPWEIGHTINGFACTOR> <MOTIVATIONALMESSAGETITLE>STRING</MOTIVATIONALMESSAGETITLE> <MOTIVATIONALMESSAGETEXT>STRING</MOTIVATIONALMESSAGETEXT> </PROMOTIONSTEP> </PROMOTIONSTEPS> 

</PROMOTIONGROUPSTEPGROUP> 

</PROMOTIONGROUPSTEPGROUPS> 

</REQUIREMENTSTEPGROUP> 

</REQUIREMENTSTEPGROUPS> 

</REQUIREMENTS> 

</PROMOTIONREQUIREMENTS> 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|PROMOTIONREQUIREMENT|n/a||Containingenvelope for the document|
|DEALERID|Numeric||The actual dealer ID that these results are for|
|REQUIREMENTS||NumSets<br>Set to the total number of<br>REQUIREMENT nodes that must<br>be interated through|Containing envelope for all set s of requirements<br>* As of the date of the release of this document,<br>the system only supports a single set of<br>requirements, so until further notice, this value<br>should be set to “1”.|
|*  DEALERSHIPTYPEID|Numeric||The dealershipTypeID that cooresponds to the<br>sales rank these requirements are for.|
|*  RANKCODE|String||Text code representing the dealershipTypeID. This<br>is the same code that is displayed in the member’s<br>web backoffice(i.e.: “DIST”,“SILVER”,GOLD”,etc)|
|*  INMAINT|Boolean|||
|*  RANKPERCENTAGECOMPLETE||||
|*  REQUIREMENTSTEPGROUPS|||Containingenvelope for a set of requirements|
|**  REQUIREMENTSTEPGROUP||NumRequirementStepGroups<br>Total number of<br>REQUIREMENTSTEPGROUPS nodes<br>that must be interated through|Containing envelope for a set of requirements|
|*** REQUIREMENTSTEPGROUP|||Containing envelope for a single set of<br>requirements (Typically “Initial” or “Maintenance”<br>requirements)|
|**** PROMOTIONGROUPCODE|String||A code used by admin to group togeteher a a set<br>of requirements|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 63 | 317 

Firestorm® Web Services API | Version 2.2.33 

|**** PROMOTIONGROUPDISPLAYNAME|String||A more descriptive name for<br>PROMOTIONGROUPCODE to be used for display<br>purposes inyour widget|
|---|---|---|---|
|**** PROMOTIONGROUPDESCRIPTION|String||A detailed description of the set of requirements|
|**** PROMOTIONGROUPHEXCOLORCODE|String||HexCode to represent a web color to be used to<br>color code the display for this set of requirements.<br>If you are using a radial gauge or something<br>similar, the gauge should use this color to<br>represent this set of requirements.|
|**** PROMOTIONGROUPISMAINTENANCE|Boolean||When set to TRUE, this flag represents whether or<br>not this set of requirements if for maintaining this<br>rank. If the member is INMAINT (true), then this is<br>the set of requirements that should be displayed<br>inyour widget|
|**** PROMOTIONGROUPSTEPGROUPS||NumPromotionGroupSteps<br>Total number of<br>PROMOTIONGROUPSTEPGROUP<br>nodes that must be interated<br>through|Containing envelope for the all steps defined for<br>the set of requirements|
|***** PROMOTIONGROUPSTEPGROUP|||Envelope to contain all elements of a  single step|
|****** PROMOTIONGROUPSTEPGROUPCODE||||
|******||||
|<br>PROMOTIONGROUPPERCENTAGECOMPLETE||||
|****** PROMOTIONSTEPS||NumPromotionSteps<br>Total number of<br>PROMOTIONSTEP nodes that<br>must be interated through|Containing envelope of all steps required to schive<br>this set of requirements|
|******* PROMOTIONSTEP|||Containing envelope to contain data points for<br>requirements for a single step|
|******** PROMOTIONSTEPNUMBER|Numeric||The stepnumber for this requirement.(1-n)|
|********PROMOTIONSTEPDESCRIPTION|String||A verbose description of the requirement that<br>must be met|
|********PROMOTIONSTEPREQUIREDVALUE|String||The required value for the step (i.e.: 50 PSV<br>required would be 50)|
|********PROMOTIONSTEPACTUALVALUE|String||The actual value achieved by the member toward<br>this requirement|
|********PROMOTIONSTEPPERCENTCOMPLETE|Numeric||On a scale from 0 to 100, the percentage<br>complete the member is towards this<br>requirement. This number will always rounded up<br>to be a whole number.|
|********PROMOTIONSTEPWEIGHTINGFACTOR|Numeric||On a scale of 1 to 100, the level of difficulty this<br>step represents towards meeting all requirements<br>in this PROMOTIONGROUPSTEPGROUP|
|********MOTIVATIONALMESSAGETITLE|String||Title of motivation message to display for this<br>requirement|
|********MOTIVATIONALMESSAGETEXT|String||Text of the motivational message to display for<br>this requirement|



* = Indentation Level 

Please see the following page for an example return from an actual call to make sure you understand what to expect from this web service: 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 64 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **Example of returned XML document from an actual call to this web service** 

```
<?xml version='1.0' encoding='utf-8'?>
```

```
<FIRESTORMRESULT>
```

```
    <STATUS>SUCCESS</STATUS>
    <ID>43096</ID>
    <ERRORS errorcount="0"></ERRORS>
    <PROMOTIONREQUIREMENTS>
```

```
        <DEALERID>43096</DEALERID>
```

```
        <REQUIREMENTS NumSets="1">
```

```
            <DEALERSHIPTYPEID>56</DEALERSHIPTYPEID>
```

```
            <RANKCODE>DISTRIBUTOR</RANKCODE>
            <INMAINT>True</INMAINT>
```

```
            <RANKPERCENTAGECOMPLETE>40</RANKPERCENTAGECOMPLETE>
```

```
            <REQUIREMENTSTEPGROUPS NumRequirementStepGroups="2">
```

```
                <REQUIREMENTSTEPGROUP>
```

```
                    <PROMOTIONGROUPCODE>DISTRIBUTOR_INITIAL</PROMOTIONGROUPCODE>
```

```
                    <PROMOTIONGROUPDISPLAYNAME>Initial</PROMOTIONGROUPDISPLAYNAME>
```

```
                    <PROMOTIONGROUPDESCRIPTION>Initial Requirements for DISTRIBUTOR</PROMOTIONGROUPDESCRIPTION>
                    <PROMOTIONGROUPHEXCOLORCODE>891ac9</PROMOTIONGROUPHEXCOLORCODE>
```

```
                    <PROMOTIONGROUPISMAINTENANCE>False</PROMOTIONGROUPISMAINTENANCE>
```

```
                    <PROMOTIONGROUPSTEPGROUPS NumPromotionGroupSteps="1">
```

```
                        <PROMOTIONGROUPSTEPGROUP>
```

|`<PROMOTIONGROUPSTEPGROUPCODE>Primary</PROMOTIONGROUPSTEPGROUPCODE>`|
|---|
|`<PROMOTIONGROUPPERCENTAGECOMPLETE>40</PROMOTIONGROUPPERCENTAGECOMPLETE>`|
|`<PROMOTIONSTEPS NumPromotionSteps="3">`|
|`<PROMOTIONSTEP>`|
|`<PROMOTIONSTEPNUMBER>1</PROMOTIONSTEPNUMBER>`<br>|
|`<PROMOTIONSTEPDESCRIPTION>Must be base qualified with $50 Personal Volume (PV) in`|
|`current period</PROMOTIONSTEPDESCRIPTION>`<br>|
|`<PROMOTIONSTEPREQUIREDVALUE>50.00</PROMOTIONSTEPREQUIREDVALUE>`<br>`<PROMOTIONSTEPACTUALVALUE>1</PROMOTIONSTEPACTUALVALUE>`|
|`<PROMOTIONSTEPPERCENTCOMPLETE>2</PROMOTIONSTEPPERCENTCOMPLETE>`<br>`<PROMOTIONSTEPWEIGHTINGFACTOR>20</PROMOTIONSTEPWEIGHTINGFACTOR>`|
|`<MOTIVATIONALMESSAGETITLE>Almost There!</MOTIVATIONALMESSAGETITLE>`|
|`<MOTIVATIONALMESSAGETEXT>“Believe in yourself! Have faith in your abilities! Without`|
|`a humble but reasonable confidence in your own powers you cannot be successful or happy.” —Norman Vincent`|
|`Peale</MOTIVATIONALMESSAGETEXT>`|
|`</PROMOTIONSTEP>`|
|`<PROMOTIONSTEP>`|
|`<PROMOTIONSTEPNUMBER>2</PROMOTIONSTEPNUMBER>`|
|`<PROMOTIONSTEPDESCRIPTION>Must have 2 or more QUALIFIED`|
|`legs</PROMOTIONSTEPDESCRIPTION>`|
|`<PROMOTIONSTEPREQUIREDVALUE>2</PROMOTIONSTEPREQUIREDVALUE>`<br>`<PROMOTIONSTEPACTUALVALUE>4</PROMOTIONSTEPACTUALVALUE>`|
|`<PROMOTIONSTEPPERCENTCOMPLETE>100</PROMOTIONSTEPPERCENTCOMPLETE>`<br>`<PROMOTIONSTEPWEIGHTINGFACTOR>20</PROMOTIONSTEPWEIGHTINGFACTOR>`|
|`<MOTIVATIONALMESSAGETITLE>You can do it!</MOTIVATIONALMESSAGETITLE>`|
|`<MOTIVATIONALMESSAGETEXT>“If you can dream it, you can do it.” —Walt`|
|`Disney</MOTIVATIONALMESSAGETEXT>`|
|`</PROMOTIONSTEP>`|
|`<PROMOTIONSTEP>`|
|`<PROMOTIONSTEPNUMBER>3</PROMOTIONSTEPNUMBER>`|
|`<PROMOTIONSTEPDESCRIPTION>$2,000 or more Team Sales in the Current`|
|`Period</PROMOTIONSTEPDESCRIPTION>`|
|`<PROMOTIONSTEPREQUIREDVALUE>2000.00</PROMOTIONSTEPREQUIREDVALUE>`<br>`<PROMOTIONSTEPACTUALVALUE>2500.00</PROMOTIONSTEPACTUALVALUE>`<br>`<PROMOTIONSTEPPERCENTCOMPLETE>100</PROMOTIONSTEPPERCENTCOMPLETE>`|
|`<PROMOTIONSTEPWEIGHTINGFACTOR>20</PROMOTIONSTEPWEIGHTINGFACTOR>`<br>`<MOTIVATIONALMESSAGETITLE>The final push!</MOTIVATIONALMESSAGETITLE>`|
|`<MOTIVATIONALMESSAGETEXT>“Where there is a will, there is a way. If there is a chance`|
|`in a million that you can do something, anything, to keep what you want from ending, do it. Pry the door open or, if need`<br>`be, wedge your foot in that door and keep it open.” —Pauline Kael</MOTIVATIONALMESSAGETEXT>`<br>`</PROMOTIONSTEP>`<br>`</PROMOTIONSTEPS>`|



```
                        </PROMOTIONGROUPSTEPGROUP>
```

```
                    </PROMOTIONGROUPSTEPGROUPS>
```

```
                </REQUIREMENTSTEPGROUP>
```

```
                <REQUIREMENTSTEPGROUP>
```

```
                    <PROMOTIONGROUPCODE>DISTRIBUTOR_MAINT</PROMOTIONGROUPCODE>
```

```
                    <PROMOTIONGROUPDISPLAYNAME>Maintenance</PROMOTIONGROUPDISPLAYNAME>
```

```
                    <PROMOTIONGROUPDESCRIPTION>Maintenance Requirements for DISTRIBUTOR</PROMOTIONGROUPDESCRIPTION>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 65 | 317 

Firestorm® Web Services API | Version 2.2.33 

|`<PROMOTIONGROUPHEXCOLORCODE>07de59</PROMOTIONGROUPHEXCOLORCODE>`|
|---|
|`<PROMOTIONGROUPISMAINTENANCE>True</PROMOTIONGROUPISMAINTENANCE>`|
|`<PROMOTIONGROUPSTEPGROUPS NumPromotionGroupSteps="1">`|
|`<PROMOTIONGROUPSTEPGROUP>`|
|`<PROMOTIONGROUPSTEPGROUPCODE>Primary</PROMOTIONGROUPSTEPGROUPCODE>`|
|`<PROMOTIONGROUPPERCENTAGECOMPLETE>40</PROMOTIONGROUPPERCENTAGECOMPLETE>`|
|`<PROMOTIONSTEPS NumPromotionSteps="3">`|
|`<PROMOTIONSTEP>`|
|`<PROMOTIONSTEPNUMBER>1</PROMOTIONSTEPNUMBER>`|
|`<PROMOTIONSTEPDESCRIPTION>Must be base qualified with $50 Personal Volume (PV) in`|
|`current period</PROMOTIONSTEPDESCRIPTION>`|
|`<PROMOTIONSTEPREQUIREDVALUE>50.00</PROMOTIONSTEPREQUIREDVALUE>`|
|`<PROMOTIONSTEPACTUALVALUE>1</PROMOTIONSTEPACTUALVALUE>`|
|`<PROMOTIONSTEPPERCENTCOMPLETE>2</PROMOTIONSTEPPERCENTCOMPLETE>`|
|`<PROMOTIONSTEPWEIGHTINGFACTOR>20</PROMOTIONSTEPWEIGHTINGFACTOR>`|
|`<MOTIVATIONALMESSAGETITLE>Almost There!</MOTIVATIONALMESSAGETITLE>`|
|`<MOTIVATIONALMESSAGETEXT>“Believe in yourself! Have faith in your abilities! Without`|
|`a humble but reasonable confidence in your own powers you cannot be successful or happy.” —Norman Vincent`|
|`Peale</MOTIVATIONALMESSAGETEXT>`|
|`</PROMOTIONSTEP>`|
|`<PROMOTIONSTEP>`|
|`<PROMOTIONSTEPNUMBER>2</PROMOTIONSTEPNUMBER>`|
|`<PROMOTIONSTEPDESCRIPTION>Must have 2 or more QUALIFIED`|
|`legs</PROMOTIONSTEPDESCRIPTION>`|
|`<PROMOTIONSTEPREQUIREDVALUE>2</PROMOTIONSTEPREQUIREDVALUE>`<br>`<PROMOTIONSTEPACTUALVALUE>4</PROMOTIONSTEPACTUALVALUE>`|
|`<PROMOTIONSTEPPERCENTCOMPLETE>100</PROMOTIONSTEPPERCENTCOMPLETE>`<br>`<PROMOTIONSTEPWEIGHTINGFACTOR>20</PROMOTIONSTEPWEIGHTINGFACTOR>`|
|`<MOTIVATIONALMESSAGETITLE>You can do it!</MOTIVATIONALMESSAGETITLE>`|
|`<MOTIVATIONALMESSAGETEXT>“If you can dream it, you can do it.” —Walt`|
|`Disney</MOTIVATIONALMESSAGETEXT>`|
|`</PROMOTIONSTEP>`|
|`<PROMOTIONSTEP>`|
|`<PROMOTIONSTEPNUMBER>3</PROMOTIONSTEPNUMBER>`|
|`<PROMOTIONSTEPDESCRIPTION>$2,000 or more Team Sales in the Current`|
|`Period</PROMOTIONSTEPDESCRIPTION>`|
|`<PROMOTIONSTEPREQUIREDVALUE>2000.00</PROMOTIONSTEPREQUIREDVALUE>`<br>`<PROMOTIONSTEPACTUALVALUE>2500.00</PROMOTIONSTEPACTUALVALUE>`|
|`<PROMOTIONSTEPPERCENTCOMPLETE>100</PROMOTIONSTEPPERCENTCOMPLETE>`|
|`<PROMOTIONSTEPWEIGHTINGFACTOR>20</PROMOTIONSTEPWEIGHTINGFACTOR>`|
|`<MOTIVATIONALMESSAGETITLE>The final push!</MOTIVATIONALMESSAGETITLE>`|
|`<MOTIVATIONALMESSAGETEXT>“Where there is a will, there is a way. If there is a chance`|
|`in a million that you can do something, anything, to keep what you want from ending, do it. Pry the door open or, if need`|
|`be, wedge your foot in that door and keep it open.” —Pauline Kael</MOTIVATIONALMESSAGETEXT>`<br>`</PROMOTIONSTEP>`|



```
                            </PROMOTIONSTEPS>
```

```
                        </PROMOTIONGROUPSTEPGROUP>
```

```
                    </PROMOTIONGROUPSTEPGROUPS>
```

```
                </REQUIREMENTSTEPGROUP>
```

```
            </REQUIREMENTSTEPGROUPS>
```

```
        </REQUIREMENTS>
```

```
    </PROMOTIONREQUIREMENTS>
```

```
</FIRESTORMRESULT>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 66 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ID>integer</ID>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
<PROMOTIONREQUIREMENTS></PROMOTIONREQUIREMENTS>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|Integer||The Dealer ID of the dealer that was requested in the call|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the<br>number of errors that occurred during the call, which will correlate directly<br>to the number of <ERRORMSG> elements that will be present. All argument<br>validation errors will be returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|
|PROMOTIONREQUIREMENTS|n/a||Containing envelope for a successful call. See prior pages  for contents of<br>this XML document.(only present on a successful call)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 67 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.GetRankWidgetRankPath 

This method will allow a remote caller to pull all of thepossible ranks for a given member to achieve. This information is used to be able to pull the rank requirements using GetRankWidgetDate() as described below. 

_NOTE: This function is used in conjunction with FirestormDealerWS.GetRankWidgetData() to obtain complete requirements for each DealershipTypeID returned by this web service._ 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|RequestedDealerID|Y|The DealerID of the member to pull information<br>for|Integer|Any valid DealerID|
|ShowAllRanks|Y|A Boolean flag to indicate if you want ALL<br>possible ranks returned|Boolean|TRUE or FALSE<br>When TRUE, the<br>system will return<br>all ranks defined in<br>the system. A<br>special flag is<br>provided in the<br>output so you will<br>know what the<br>current pay rank is<br>for the requested<br>member.<br>When FALSE, the<br>system will only<br>return ranks that<br>are HIGHER than<br>the current pay rank<br>of the member. In<br>other words, the<br>first rank in the list<br>will be the NEXT<br>rank that the<br>member is trying to<br>achieve.|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Dealer’s MailCountry must be in an authorized country for the<br>caller)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The web service is intended to prpvide you with a list of DealershipTypeIDs (Ranks) that can then be used in calls to GetRankWidgetData() in order to obtain a list of requirements for display in a rank widget. By iterating through the list of ranks returned by this call, it is possible to create a widget that will display a single set of requirements or all possible requirements for a given member. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 68 | 317 

Firestorm® Web Services API | Version 2.2.33 

Upon a successful call, the system will return a complex XML document that contains all relevant data . 

##### **<u>Special Behaviors</u>** 

If a RequestedDealershipTypeID (Rank) is not passed in, the system will look up the DealershipType of the #1 position in the system, and will return results for that rank. This will in effect be the members current pay rank as defined by the last promotions run performed in the system. 

If a specific DealershipTypeID (Rank) is passed in, the system will pull the requirements for the requested rank and will return a payload describing the RequestedDealerID’s qualifications for that rank. This capability is useful for “looking ahead” to the next rank. Many rank widgets will show the current rank, but will also allow members to look at their qualifications for higher ranks to see where they are. 

##### **<u>Full Rank List or Only Higher Ranks</u>** 

In typical use, this function will be used to return a list of ranks (DealershipTypeID) that are HIGHER that the current pay rank for the member. This is used to help the member “look ahead” at future ranks to see where they need to be to achieve them. If tyhis is what you want, then you should pass in FALSE to the argument “ReturnAllRanks” 

Sometimes compensation plans require a member to reachieve all lower ranks before moving on. In this care you will want to pass in TRUE to “ReturnAllRanks”. When the system sees this, it will return a complete list of all defined ranks in the system. There is a special node in the output document called “ISCURRENTRANK” which will be set to either TRUE or FALSE depending on whether or not the current pay rank matches 

##### **<u>Sample Return XML</u>** 

This web service will return a complex XML document that will be embedded in the <FIRESTORMRESULT> envelope on a successful call. That portion of the document is described here: 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 69 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **Example Base XML Document containing Requirements** 

```
<RANKPATH>
<DEALERID></DEALERID>
<RANKS NumRanks='1'>
<RANK>
<DEALERSHIPTYPEID></DEALERSHIPTYPEID>
<RANKCODE></RANKCODE>
<RANKSEQUENCE></RANKSEQUENCE>
<ISCURRENTRANK></ISCURRENTRANK>
</RANK>
```

```
</RANKS>
```

```
</RANKPATH>
```

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|RANKPATH|||Continaingenvelope for response|
|DEALERID|Numeric||Actual DealerID of the member these results are<br>for|
|RANKS||NumRanks<br>Total number of RANK nodes<br>that must be interated through|Containineg envelope for all returned RANK<br>nodes. The system will return a RANK node for<br>each unique rank.|
|* RANK|||Containingenvelope for a single rank|
|** DEALERSHIPTYPEID|Numeric||The DealershipTypeID for this rank|
|** RANKCODE|String||The code used to represent the rank on reports.<br>This is the value that members see in their web<br>backoffice.|
|** RANKSEQUENCE|Numeric||Numeric value representing this rank. This<br>number is used to determine if a given rank is<br>higher or lower than another rank.|
|** ISCURRENTRANK|Boolean||If TRUE, this rank is the current pay rank of the<br>member.<br>Special Note: If “ShowAllRanks” is set to FALSE,<br>the system will only return ranks that are higher<br>than the current pay rank of the dealer. Therefore<br>you will not have any ranks flagged as<br>ISCURRENTRANK = TRUE|



* = Indentation Level 

Please see the following page for an example return from an actual call to make sure you understand what to expect from this web service: 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 70 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **Example of returned XML document from an actual call to this web service** 

```
<?xml version='1.0' encoding='utf-8'?>
<FIRESTORMRESULT>
    <STATUS>SUCCESS</STATUS>
    <ID>43096</ID>
    <ERRORS errorcount="0"></ERRORS>
    <RANKPATH>
        <DEALERID>43096</DEALERID>
        <RANKS NumRanks="6">
            <RANK>
                <DEALERSHIPTYPEID>56</DEALERSHIPTYPEID>
                <RANKCODE>DISTRIBUTOR</RANKCODE>
                <RANKSEQUENCE>2</RANKSEQUENCE>
                <ISCURRENTRANK>TRUE</ISCURRENTRANK>
            </RANK>
            <RANK>
                <DEALERSHIPTYPEID>55</DEALERSHIPTYPEID>
                <RANKCODE>BRONZE</RANKCODE>
                <RANKSEQUENCE>3</RANKSEQUENCE>
                <ISCURRENTRANK>FALSE</ISCURRENTRANK>
            </RANK>
            <RANK>
                <DEALERSHIPTYPEID>54</DEALERSHIPTYPEID>
                <RANKCODE>SILVER</RANKCODE>
                <RANKSEQUENCE>4</RANKSEQUENCE>
                <ISCURRENTRANK>FALSE</ISCURRENTRANK>
            </RANK>
            <RANK>
                <DEALERSHIPTYPEID>53</DEALERSHIPTYPEID>
                <RANKCODE>GOLD</RANKCODE>
                <RANKSEQUENCE>5</RANKSEQUENCE>
                <ISCURRENTRANK>FALSE</ISCURRENTRANK>
            </RANK>
            <RANK>
                <DEALERSHIPTYPEID>52</DEALERSHIPTYPEID>
                <RANKCODE>PLATINUM</RANKCODE>
                <RANKSEQUENCE>6</RANKSEQUENCE>
                <ISCURRENTRANK>FALSE</ISCURRENTRANK>
            </RANK>
            <RANK>
                <DEALERSHIPTYPEID>51</DEALERSHIPTYPEID>
                <RANKCODE>DIAMOND</RANKCODE>
                <RANKSEQUENCE>7</RANKSEQUENCE>
                <ISCURRENTRANK>FALSE</ISCURRENTRANK>
            </RANK>
        </RANKS>
    </RANKPATH>
</FIRESTORMRESULT>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 71 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ID>integer</ID>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
<RANKPATH></RANKPATH>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|Integer||The Dealer ID of the dealer that was requested in the call|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|
|RANKPATH|n/a||Containing envelope for a successful call. See prior pages for contents of this XML<br>document.(only present on a successful call)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 72 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.CreditProductPoints 

This call will credit a given Dealer’s Product Point account in Firestorm with the specified number of Product Points. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The DealerID of the record to be updated|Integer|Requires a numeric<br>DealerID that already<br>exists in the system|
|NumPoints|Y|A number of points, greater than 0, that should be<br>credited to the Dealer’sproductpoint account.|Double|Any non-zero<br>positive value.|
|Comment|Y|The comment that should be added to the point<br>record. Will be visible to the Dealer.|String|Any non-zero length<br>string.|
|OrderID|Y|If the points being credited are the result of an<br>order, the corresponding OrderID should be supplied<br>for this parameter to link the two records. If no<br>order should be linked, pass -1.|Integer|A Firestorm Order ID<br>that exists in the<br>target system or -1.|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

There is no additional information for this method. 

##### **<u>Return Values</u>** 

BOOLEAN – True = Success, False = Update Failed 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 73 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.DebitProductPoints 

This call will debit a given Dealer’s Product Point account in Firestorm with the specified number of Product Points. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The DealerID of the record to be updated|Integer|Requires a numeric<br>DealerID that already<br>exists in the system|
|NumPoints|Y|A number of points, greater than 0, that should be<br>debited from the Dealer’sproductpoint account.|Double|Any non-zero<br>positive value.|
|Comment|Y|The comment that should be added to the point<br>record. Will be visible to the Dealer.|String|Any non-zero length<br>string.|
|OrderID|Y|If the points being debited are the result of an order,<br>the corresponding OrderID should be supplied for<br>this parameter to link the two records. If no order<br>should be linked, pass -1.|Integer|A Firestorm Order ID<br>that exists in the<br>target system or -1.|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

There is no additional information for this method. 

##### **<u>Return Values</u>** 

BOOLEAN – True = Success, False = Update Failed 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 74 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.GetDealerProductPointBalance 

This call will return the current available balance of the given Dealer’s Product Point account. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The DealerID to get the Product Point Balance for|Integer|Requires a numeric<br>DealerID that already<br>exists in the system|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

There is no additional information for this method. 

##### **<u>Return Values</u>** 

DOUBLE – Available Product Point Balance 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 75 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealerWS.GetDealerKPIData 

This call will return a list of Client specific KPI data points that are stored in the Client’s Genealogy Complilation Data table. This data is precompiled and updated on a regular schedule, and is not reflective of real time conditions. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The DealerID of the record to be updated|Integer|Requires a numeric<br>DealerID that already<br>exists in the system|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|Yes – Your Token must be specifically granted access to specific<br>fields.|
|Max Records|No|



##### **<u>Additional Information</u>** 

The Token used when calling this method must specifically be granted access to each field you need access to. If you need access to additional data fields that are available, please contact Customer Service. 

Additionally, the data made available by this method is not calculated in real time. The data is precompiled and updated on a set schedule. If you need to know what the set schedule is, please contact Customer Service. 

##### **<u>Return Values</u>** 

NOTE: This method will return a Data Table of available KPI data for the given Dealer, but the fields within the Data Table vary from client to client. To obtain a list of available fields, please contact Customer Service. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 76 | 317 

Firestorm® Web Services API | Version 2.2.33 

### Firestorm Dealership Web Service 

|General Informa|tion|
|---|---|
|Name|FirestormDealershipWS.asmx|
|WSDL|https://www.firestormwebservices.com/FirestormWebServices/FirestormDealershipWS.asmx|
|Description|This web service will contain methods necessary to retrieve dealership (structure) records for<br>a given Dealer. Each method is described below, along with the definition of each argument<br>and valid values where appropriate.|



|Method Summary||
|---|---|
|Method Name|Return Type|
|GetDealershipTypes|DataTable|
|GetDealershipsByDealer|DataTable|
|ActivateDealership|Complex XML Document|
|DeActivateDealership|Complex XML Document|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 77 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealershipWS.GetDealershipTypes 

Returns a list of dealership types that are currently defined in the Firestorm® system you are connected to. 

Dealership types are the ranks as defined in your compensation plan and will correlate directly to “pay” ranks and “lifetime (recognized as)” ranks. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealershipTypeID|N|If provided, the system will look for this specific<br>DealershipType.|Numeric|-1 or a valid<br>DealershipTypeID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

This web service is provided as a method to interpret data returned by other dealership web service functions. Please note that these records can be edited at any time by administrative personnel and as such could change at any time. These records are not static and should not be treated as such. 

##### **<u>Return Values</u>** 

|Returned Data|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|DealershipTypeID|Integer|The unique ID assigned byFirestorm® to this dealershiptype|
|Code|String|Code representing the RANK that corresponds to this dealership<br>type. This code will displayin all areas of the system.|
|Description|String|A full description of the dealershiptype|
|PromotesTo|String|When this position promotes by meeting qualifications, this is the<br>rank it will advance to.|
|ExpandsTo|String|If the compensation plan allows for “expansion” of a dealership (i.e.:<br>the member can earn a new position in the structure) this is the<br>dealershiptype that will be used when creatingthe new dealership.|
|NonProfit|Boolean|Flagindicatingif this dealershiptype is a non-profit organization.|
|TaxExempt|Boolean|Flagindicatingif this dealershiptype is sales tax-exempt.|
|PayCommissions|Boolean|Deprecated. Do not use.|
|MembershipInterval|String|Deprecated. Do not use.|
|MembershipUnits|Integer|Deprecated. Do not use.|
|MembershipPSV|Currency|Deprecated. Do not use.|
|MembershipPSVReset|Boolean|Deprecated. Do not use.|
|MembershipCycleDealershipStatusID|Integer|Deprecated. Do not use.|
|MembershipCycleRollSponsorships|Boolean|Deprecated. Do not use.|
|IsDefault|Boolean|Deprecated. Do not use.|
|CreateDate|Date|Date this record was originallycreated in the system|
|CreateBy|String|Login ID of the user who created this record|
|MaintDate|Date|Date this record was last updated|
|MaintBy|String|Login ID of the user who updated this record|
|Display|Boolean|Flagto indicate if this dealershiptype will be displayed in the system|
|WebDisplay|Boolean|Flagto indicate if this dealershiptype will be displayed on the web|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 78 | 317 

Firestorm® Web Services API | Version 2.2.33 

|WholesalePrices|Boolean|Flag to indicate that this dealership type is eligible for wholesale<br>pricing on products.<br>WARNING: This flag will control what type of pricing is displayed in<br>the shopping cart and on administrative orders the person buying is<br>at this rank.|
|---|---|---|
|EnforceMinimumOrder|Boolean|Deprecated. Do not use.|
|IsSentinal|Boolean|Flag to indicate if this dealership type is a sentinel. A sentinel is used<br>to indicate a topmost position in the structure, as well as other<br>internal system positions in the structure.<br>WARNING: DO NOT MODIFY THIS RECORD FOR ANY REASON!|
|CommissionsMinimumPSV|Currency|Deprecated. Do not use.|
|CommissionsMinimumSponsorship|Integer|Deprecated. Do not use.|
|CommissionsMinimumSponsorshipLeft|Integer|Deprecated. Do not use.|
|CommissionsMinimumSponsorshipRight|Integer|Deprecated. Do not use.|
|CommissionMinimumDealershipTypeID|Integer|Deprecated. Do not use.|
|PSVCycleEnforce|Boolean|Deprecated. Do not use.|
|PSVCycleInterval|String|Deprecated. Do not use.|
|PSVCycleAmount|Currency|Deprecated. Do not use.|
|PSVCycleUnits|Integer|Deprecated. Do not use.|
|PSVCycleVolumeReset|Boolean|Deprecated. Do not use.|
|PSVCycleDealershipStatusID|Integer|Deprecated. Do not use.|
|PSVCycleRollSponsorships|Boolean|Deprecated. Do not use.|
|OverrideCommissionQualifications|Boolean|*Can* be used to waive all compensation plan requirements to earn<br>commissions. (Note: To use this flag will require custom<br>programming. Please contact our support department for details)|
|Sequence|Integer|A numerical representation of the hierarchical position of this rank<br>in the entire rank sequence for the compensationplan.|
|MembershipCycleDelayUnits|Integer|Deprecated. Do not use.|
|PSVCycleDelayUnits|Integer|Deprecated. Do not use.|
|CatalogueID|Integer|Deprecated. Do not use.|
|WebEnrollmentDisplayOrder|Integer|A sort order that is used when the dealership type (rank) is<br>displayed on the enrollment form on the web.|
|CanSponsorDealers|Boolean|A flag to indicate that this dealership type CAN sponsor (enroll) new<br>positions into the system|
|IsStartingRank|Boolean|Deprecated. Do not use.|
|InternalRankCode|String|An internal string representing this dealership type. This code is<br>used for abstraction of the “Code” above. This allows users to edit<br>the dealership type codes without affecting any programming that<br>may be in place.<br>NOTE: This code will be created by our staff, and must NOT be<br>changed. Ever.|
|ExcludeFromPromotions|Boolean|A flag to indicate that this dealership type should be excluded from<br>rank advancementprocessing.(e.g.: A non-promoting position)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 79 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealershipWS.GetDealershipsByDealer 

Returns a list of dealership types that are currently defined in the Firestorm® system you are connected to. 

Dealership types are the ranks as defined in your compensation plan and will correlate directly to “pay” ranks and “lifetime (recognized as)” ranks. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|N||Numeric||
|DealershipID|N|If provided, the system will look for this specific<br>DealershipType.|Numeric||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

This web service is provided as a method to interpret data returned by other dealership web service functions. Please note that these records can be edited at any time by administrative personnel and as such could change at any time. These records are not static and should not be treated as such. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|DealershipID|||
|Account|||
|SubAccount|||
|DealershipTypeID|||
|DealershipStatusID|||
|DealerID|||
|SponsoringDealerID|||
|SponsoringDealershipID|||
|LevelNumber|||
|PlacementDealershipID|||
|ParentDealershipID|||
|LeftDealershipID|||
|RightDealershipID|||
|CenterDealershipID|||
|LeftVolume|||
|RightVolume|||
|CenterVolume|||
|PSV|||
|AllTimeLeftVolume|||
|AllTimeRightVolume|||
|AllTimeCenterVolume|||
|AllTimePSV|||
|NewVolume|||
|Lineage|||
|ExpirationDate|||



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 80 | 317 

Firestorm® Web Services API | Version 2.2.33 

|ExpansionParentID<br>IsSentinal|
|---|
|DealershipNumber|
|OriginalSponsoringDealerID|
|OriginalSponsoringDealershipID|
|BaseCommissionQualified<br>|
|LastVolumeReset|
|MembershipCycleEnd|
|CreateDate|
|PromotionCalcPending|
|UnitsSold<br>|
|UnilevelDepth|
|PromotionDate|
|PSVCycleEnd<br>|
|RollSponsorships|
|LastAutoPlace|
|PaidTo|
|Active<br>|
|Qualified|
|LifetimeDealershipTypeID<br>|
|LifetimePromotionDate|
|MinimumDealershipTypeID|
|MatrixFilled|
|MatrixCommissionPaid|
|MatrixCount|
|UnilevelDealershipTypeID|
|User1|
|User2|
|User3|
|LeftSponsorships<br>RightSponsorships|
|LastVolumeCompression|
|BaseCommissionQualifiedDate<br>|
|UnilevelVolume|
|UnilevelQualified|
|UnilevelQBV|
|UnilevelSponsoringDealershipID|
|UnilevelPlacementDealershipID<br>|
|LastLineage|
|OldID|
|LifeTimeUnilevelDealershipTypeID<br>|
|MinimumUnilevelDealershipTypeID|
|UnilevelPSV|
|UnilevelCustVolume|
|UnilevelLifetimePromotionDate|
|UnilevelAllTimeVolume|
|UnilevelLevelNumber|
|UnilevelPlacementLegNumber|
|UnilevelPayRankExpireDate|
|BinaryPayRankExpireDate|
|SponsorLineage<br>|
|SponsorLegNumber<br>LeftVolume2|
|RightVolume2|
|LeftVolume3|
|RightVolume3<br>|
|MatrixHorizontalPosition<br>EnrollerDealershipID|
|LeftVolume4|
|RightVolume4<br>MatrixParent|
|MatrixLeg0|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 81 | 317 

Firestorm® Web Services API | Version 2.2.33 

|MatrixLeg1|
|---|
|MatrixLeg2|
|MatrixLeg3|
|MatrixLeg4|
|MatrixLeg5|
|MatrixLeg6|
|MatrixLeg7|
|MatrixLeg8|
|MatrixLeg9|
|LastMatrixPlacement|
|IndirectParentDealershipID|
|LifetimeCodeDealershipID|
|LifetimeCodeDealershipTypeID|
|Code1|
|Code2|
|Code3|
|LastStatusChange|
|LeftLegCount|
|RightLegCount|
|MatrixVolume|
|MatrixPSV|
|MatrixLeg0Open|
|MatrixLeg1Open|
|MatrixLeg2Open|
|MatrixLeg3Open|
|MatrixLeg4Open|
|MatrixLeg5Open|
|MatrixLeg6Open|
|MatrixLeg7Open|
|MatrixLeg8Open|
|MatrixLeg9Open|
|PermanantBCQ|
|MaxLegDealershipTypeID|
|HoldingTankParentDealershipID|
|InHoldingTank|
|MatrixType|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 82 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealershipWS.ActivateDealership 

This method will allow a remote caller to Activate a specific dealership record in Firestorm. This should be used when a dealership record that has been previously deactivated needs to be reactivated for any reason. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealershipID|Y|The dealership ID to activate|Integer|Any valid<br>DealershipID|
|ReclaimLostSponsorships|Y|A boolean value indicating whether or not to reclaim<br>any sponsorships that the specified dealership id was<br>the original sponsor for but have since been lost.|Boolean|True/False|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Dealer’s MailCountry must be in an authorized country for the<br>caller)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

In order to be able to activate a specific Firestorm Dealership record, the Dealer that owns the Dealership record must already have a status of ACTIVE. If the Dealer is not ACTIVE, the activation of the Dealership will fail, and you will be returned an error message. 

<u>Reclaiming Lost Sponsorships – If a value of True is passed for the parameter ReclaimLostSponsorships, the</u> system will reclaim ALL sponsorships that have been lost by the dealership specified, where the sponsored dealership was originally sponsored by the specified dealership. This option will reclaim ALL original sponsorships, regardless of how they were lost. Caution should be exercised when using this option, as even sponsorships that were given away by administrative personnel will be reclaimed along with sponsorships that were automatically lost thorugh other means. 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

##### Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
```

```
<ID>integer</ID>
<ERRORS errorcount='0'>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 83 | 317 

Firestorm® Web Services API | Version 2.2.33 

```
<ERRORMSG>String</ERRORMSG>
```

```
</ERRORS>
```

```
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|Integer||The DealershipID of the dealer that was activated in Firestorm|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 84 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormDealershipWS.DeActivateDealership 

This method will allow a remote caller to deactivate a dealership record in Firestorm. Additionally, the caller will also be able to optionally rollup any sponsorships that are attached to the dealership record. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealershipID|Y|The dealershipID to deactivate|Integer|Anyvalid DealerID|
|RollSponsorships|Y|A boolean value indicating whether or not to roll<br>up the sponsorships of the dealers’s dealership<br>records to the next upline dealership with a<br>Firestorm Status of ACTIVE.|Boolean|True/False|
|NewDealershipStatusCode|Y|A string value representing the status code that<br>the dealer’s dealership records should be set to.<br>Specifying a value in this field will deactivate the<br>dealer’s dealership records and change their<br>statuses to the specified value.|String|Any Dealership<br>Status code that<br>exists in Firestorm|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Dealer’s MailCountry must be in an authorized country for the<br>caller)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

If no value (empty string) is specified for the parameter NewDealershipStatusCode, the new status that will be applied to the deactivated dealership record will be INACTIVE. 

<u>Rollup Sponsorships – If you choose to roll up the sponsorships for the dealership record being deactivated by</u> passing a value of True for the parameter RollSponsorships, the system will take the sponsorships for the dealership record being deactivated and roll them upline to the next dealership that has a status of ACTIVE. 

<u>Dealership Status Codes – For a complete list of available Dealership Status Code available in Firestorm, please</u> contact Firestorm Support. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 85 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ID>integer</ID>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|Integer||The Dealer ID of the dealer that was activated in Firestorm|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 86 | 317 

Firestorm® Web Services API | Version 2.2.33 

### FirestormEnrollmentWS 

|General Informa<br>Name|tion<br>FirestormEnrollmentWS.asmx|
|---|---|
|WSDL|https://www.firestormwebservices.com/FirestormWebServices/FirestormEnrollmentWS.asmx|
|Description|This web service will contain all methods necessary to enroll Members and Customers. Each<br>method is described below, along with the definition of each argument and valid values<br>where appropriate.|



|Method Summary<br>||
|---|---|
|Method Name|Return Type|
|EnrollMember|Complex XML|
|EnrollMemberExtended|Complex XML|
|EnrollMemberAsOrphan|Complex XML|
|EnrollCustomer|Complex XML|
|EnrollMemberInHoldingTank|Complex XML|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 87 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormEnrollmentWS.EnrollMember 

Performs all of the tasks required to enroll a new member into the system. This method is used to enroll a person who will participate in the compensation plan as a distributor. (DO NOT use this method to enroll a customer) 

**NOTE:** This method is designed to enroll a member who purchases a SINGLE product to enroll. If your enrollment requires a more complex order, please use FirestormEnrollmentWS.EnrollMemberExtended instead of this method. 

**PCI/DSS WARNING:** This web service uses sensitive personal and payment information to process an enrollment. It is YOUR responsibility to ensure that you are following all proper PCI/DSS procedures in addition to accessing the web service over a secure (https) link in your production environment!! 

|Method Definition|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|Security Token assigned to you by<br>support|String|Issued by Firestorm® Support|
|Context|Y|Context value assigned to you by<br>support|String|Issued by Firestorm® Support|
|FirstName|Y|First name of new member|String||
|MiddleInitial|Y||String||
|LastName|Y||String||
|CompanyName|Y|If a company name is supplied, it will be<br>used on all commission checks and will<br>be displayed ongenealogyreports.|String||
|TaxPayerNumber|Y|Government issued ID number.<br>Typically SSN (for 1099 reporting<br>purposes in the USA)|String|Apply formatting as desired|
|MailingAddress1|Y|Stored in the shipping address fields in<br>Firestorm® (don’t ask why, just believe<br>it!)|String||
|MailingAddress2|Y|“|String||
|MailingCity|Y|“|String||
|MailingState|Y|“|String|As defined in Firestorm®.<br>tblState.StateID|
|MailingZip|Y|“|String||
|MailingCountry|Y|“|String|As defined in Firestorm®.<br>tblCountry.CountryID|
|BillingAddress1|Y|Stored in the Mailing address fields in<br>Firestorm®  (don’t ask why, just believe<br>it!)|String||
|BillingAddress2|Y|“|String||
|BillingCity|Y|“|String||
|BillingState|Y|“|String|As defined in Firestorm®.<br>tblState.StateID|
|BillingZip|Y|“|String||
|BillingCountry|Y|“|String|As defined in Firestorm®.<br>tblCountry.CountryID|
|DayPhone|Y|No formatting is applied. If you want a<br>specific format for phone numbers,<br>applyit before sending.|String||
|EveningPhone|Y|“|String||
|MobilePhone|Y|“|String||
|Email|Y|Full email address|String||
|CatalogueID|Y|The specific catalogue as defined in<br>Firestorm® to place the enrollment<br>order against.|Integer|Any active enrollment catalog<br>in Firestorm®|
|ProductNumber|Y|Theproduct number being purchased|String|Must exist in specified catalog|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 88 | 317 

Firestorm® Web Services API | Version 2.2.33 

|Price|Y|LEGACY – NOT USED. The actual price<br>of the enrollment will be calculated<br>using the specified product’s pricing in<br>the catalog. All tax, shipping and other<br>fees will be calculated based on system<br>configurations.|Double|Must be >= 0|
|---|---|---|---|---|
|DealershipTypeCode|Y|The rank that the person is enrolling as.||Must exist in<br>tblDealershipType.Code|
|MemberEnrollerID|Y|This will be the dealerID of the sponsor<br>for this member. (Enroller and Sponsor<br>are almost always the same. Do not<br>deviate from this unless your system is<br>configured differently)|Integer|DealerID must exist in the<br>system|
|MemberEnrollerPosition|Y|The dealership number (NOT<br>DealershipID) to credit this enrollment<br>to. Will be set to “1” in almost all cases.|Integer|Any existing dealership number<br>for the enroller|
|SponsorMemberiD|Y|This will be the dealerID of the sponsor<br>for this member. (Enroller and Sponsor<br>are almost always the same. Do not<br>deviate from this unless your system is<br>configured differently)|Integer|DealerID must exist in the<br>system|
|SponsorPosition|Y|The dealership number (NOT<br>DealershipID) to credit this enrollment<br>to. Will be set to “1” in almost all cases.|Integer|Any existing dealership number<br>for the sponsor|
|BinaryPlacementMemberID|Y|For BINARY systems, this will be the<br>DealerID of the owner of the dealership<br>that you want to place the new<br>enrollee directly under. FOR NON-<br>BINARY systems, this will be the same<br>as “SponsorMemberID”|Integer|DealerID must exist in the<br>system|
|BinaryPlacementPosition|Y|For BNARY systems, this is the<br>dealership number of the dealership<br>you want to place the new enrollee<br>directly under. FOR NON-BINARY<br>systems,default this value to “1”|Integer|Any existing dealership number<br>for the dealerID specified in<br>“BinaryPlacementMemberID”|
|BinaryPlacementLineage|Y|For BINARY systems, this field will<br>indicate which side (left or right) of the<br>“BinaryPLacementPosition” that you<br>wish toplace the new enrollee on|String|“L” or “R” or “W”<br>(L)eft<br>(R)ight<br>(W)eak Side|
|UniPlacementMemberID|Y|The DealerID of the existing dealer who<br>will have the new enrollee placed on<br>their frontline. For UNILEVEL systems,<br>this will almost always be the same<br>value as “SponsorMemberID”. For<br>BINARY systems, this will always be the<br>same value as “SponsorMemberID”|Integer|DealerID must exist in the<br>system|
|UniPlacementPosition|Y|The dealership number (not<br>dealershipID) of the existing dealership<br>where the new enrollee will be placed.<br>For BINARY systems, this should be the<br>same value as “SponsorPosition”|Integer|Any existing dealership number<br>for the dealerID specified in<br>“UniPlacementMemberID”|
|PaymentTypeCode|Y|The payment type to be used to<br>process this order.|String|Any valid payment type as<br>defined in Firestorm®|
|CardAccountNumber|C*|Unencrypted credit card number|String||
|CVV2Code|C*|Unencrypted CVV2 code from the<br>credit card|String||
|CardHolderName|C*|<br>Name as it appears on the card|String||
|CardExpirationMonth|C*|2 digit number (zero filled)<br>representing the month of the<br>expiration date|String|MM|
|CardExpirationYear|C*|<br>4 digit number representing the year of<br>the expiration date|String|YYYY|
|ShippingCode|Y|Shipper code|String|Any valid shipper as defined in<br>the Firestorm® system.<br>(tblShipper.Code)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 89 | 317 

Firestorm® Web Services API | Version 2.2.33 

|ReplicatedWebsiteURL|Y<br>The unique name for the new enrollees<br>replicated website. This value is NOT<br>fully qualified!<br>(“http:www.myco.com/bob” would be<br>entered as “bob”)|String||
|---|---|---|---|
|ReplicatedWebsitePassword|Y<br>Unencrypted password used by the<br>new member to access their web office|String||
|AddlPaymentInfo|Y<br>Any additional payment information<br>that you may need to capture. This<br>value is stored in the database but is<br>not used in anyway)|String|Stored in<br>tblWebServiceAddlPaymentInfo|



* If the “PaymentTypeCode” is a credit card (as defined in Firestorm®) these fields are required 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Record being created must be in a country the web service<br>caller is authorized for. MailingCountrycontrols this access.)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The information passed into this web service is extensively validated against the database before allowing the enrollment to continue. Any validations that fail will be passed back to the caller as a complex XML document that will contain a complete listing of all validation failures. 

**Payment Processing** : This web service WILL process the payment for this order if the calculated total of the enrollment order is greater than zero. If the selected payment type is a credit card, the card will be charged for the order. If you do not wish the web service to process payment, you must configure the system so that the calculated total of the enrollment order is $0. If the web service does process payment, it will calculate the total amount to charge based on pricing, tax, shipping and other fees configurations in the system. 

**Currency Conversion:** When an order is being processed by the system for this enrollment, the system will look up the country specified in “BillingCountry” to see if a default currency has been defined for that country. If it has, the currency type and the defined conversion ratio for that currency will be saved as part of the order. Normal Firestorm® currency processing will still occur based on system setup and configurations. 

The web service will create the Dealer, Dealership and Order records as required by the system. Once a successful call has been made to this web service, the new member will be enrolled and ready to go. 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

##### Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 90 | 317 

Firestorm® Web Services API | Version 2.2.33 

```
<ID>integer</ID>
<ORDERID>integer</ORDERID>
<DEALERSHIPID>integer</DEALERSHIPID>
<ERRORS errorcount='0'>
```

```
<ERRORMSG>String</ERRORMSG>
```

```
</ERRORS>
```

```
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS: The DealerID that was created for the new enrollee|
|ORDERID|Integer||On SUCCESS: The OrderID of the enrollment order.|
|DEALERSHIPID|Integer||On SUCCESS: The DealershipID of the newposition created for the new enrollee|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 91 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormEnrollmentWS.EnrollMemberExtended 

This extended version of EnrollMember() will also perform all tasks required to enroll a new member into the system. However, this method also includes support for complex orders that are comprised of multiple products. You can also specify all financial information (retail, wholesale, upline and PSV) of each product, overriding what is configured in the catalog. 

This method is used to enroll a person who will participate in the compensation plan as a distributor. (DO NOT use this method to enroll a customer) 

**PCI/DSS WARNING:** This web service uses sensitive personal and payment information to process an enrollment. It is YOUR responsibility to ensure that you are following all proper PCI/DSS procedures in addition to accessing the web service over a secure (https) link in your production environment!! 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String|Issued byFirestorm® Support|
|Context|Y|Context value assigned toyou bysupport|String|Issued byFirestorm® Support|
|FirstName|Y|First name of new member|String||
|MiddleInitial|Y||String||
|LastName|Y||String||
|CompanyName|Y|If a company name is supplied, it will be used<br>on all commission checks and will be displayed<br>ongenealogyreports.|String||
|TaxPayerNumber|Y|Government issued ID number. Typically SSN<br>(for 1099 reporting purposes in the USA)|String|Apply formatting as desired|
|MailingAddress1|Y|Stored in the shipping address fields in<br>Firestorm®(don’t ask why, just believe it!)|String||
|MailingAddress2|Y|“|String||
|MailingCity|Y|“|String||
|MailingState|Y|“|String|As defined in Firestorm®.<br>tblState.StateID|
|MailingZip|Y|“|String||
|MailingCountry|Y|“|String|As defined in Firestorm®.<br>tblCountry.CountryID|
|BillingAddress1|Y|Stored in the Mailing address fields in<br>Firestorm®(don’t ask why, just believe it!)|String||
|BillingAddress2|Y|“|String||
|BillingCity|Y|“|String||
|BillingState|Y|“|String|As defined in Firestorm®.<br>tblState.StateID|
|BillingZip|Y|“|String||
|BillingCountry|Y|“|String|As defined in Firestorm®.<br>tblCountry.CountryID|
|DayPhone|Y|No formatting is applied. If you want a specific<br>format for phone numbers, apply it before<br>sending.|String||
|EveningPhone|Y|“|String||
|MobilePhone|Y|“|String||
|Email|Y|Full email address|String||
|CatalogueID|Y|The specific catalogue as defined in<br>Firestorm® to place the enrollment order<br>against.|Integer|Any active enrollment catalog<br>in Firestorm®|
|OrderDetail|Y|Complex XML document describing the order<br>to beplaced|String|See detailed information below|
|OrderTotalAmt|Y||Double|Must be equal to the total<br>amount of theproducts|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 92 | 317 

Firestorm® Web Services API | Version 2.2.33 

|||||specified on the order (not<br>including tax and shipping and<br>other fees).<br>**OVERRIDE**: If a value of -99 is<br>passed in this field, the system<br>will not validate the total of the<br>products on the XML document<br>“OrderDetail” against this<br>number.|
|---|---|---|---|---|
|DealershipTypeCode|Y|The rank that the person is enrolling as.||Must exist in<br>tblDealershipType.Code|
|MemberEnrollerID|Y|This will be the dealerID of the sponsor for this<br>member. (Enroller and Sponsor are almost<br>always the same. Do not deviate from this<br>unlessyour system is configured differently)|Integer|DealerID must exist in the<br>system|
|MemberEnrollerPosition|Y|The dealership number (NOT DealershipID) to<br>credit this enrollment to. Will be set to “1” in<br>almost all cases.|Integer|Any existing dealership number<br>for the enroller|
|SponsorMemberiD|Y|This will be the dealerID of the sponsor for this<br>member. (Enroller and Sponsor are almost<br>always the same. Do not deviate from this<br>unlessyour system is configured differently)|Integer|DealerID must exist in the<br>system|
|SponsorPosition|Y|The dealership number (NOT DealershipID) to<br>credit this enrollment to. Will be set to “1” in<br>almost all cases.|Integer|Any existing dealership number<br>for the sponsor|
|BinaryPlacementMemberID|Y|<br>For BINARY systems, this will be the DealerID<br>of the owner of the dealership that you want<br>to place the new enrollee directly under. FOR<br>NON-BINARY systems, this will be the same as<br>“SponsorMemberID”|Integer|DealerID must exist in the<br>system|
|BinaryPlacementPosition|Y|For BNARY systems, this is the dealership<br>number of the dealership you want to place<br>the new enrollee directly under. FOR NON-<br>BINARY systems,default this value to “1”|Integer|Any existing dealership number<br>for the dealerID specified in<br>“BinaryPlacementMemberID”|
|BinaryPlacementLineage|Y|For BINARY systems, this field will indicate<br>which side (left or right) of the<br>“BinaryPLacementPosition” that you wish to<br>place the new enrollee on|String|“L” or “R” or “W”<br>(L)eft<br>(R)ight<br>(W)eak Side|
|UniPlacementMemberID|Y|The DealerID of the existing dealer who will<br>have the new enrollee placed on their<br>frontline. For UNILEVEL systems, this will<br>almost always be the same value as<br>“SponsorMemberID”. For BINARY systems,<br>this will always be the same value as<br>“SponsorMemberID”|Integer|DealerID must exist in the<br>system|
|UniPlacementPosition|Y|The dealership number (not dealershipID) of<br>the existing dealership where the new<br>enrollee will be placed. For BINARY systems,<br>this should be the same value as<br>“SponsorPosition”|Integer|Any existing dealership number<br>for the dealerID specified in<br>“UniPlacementMemberID”|
|PaymentTypeCode|Y|The payment type to be used to process this<br>order.|String|Any valid payment type as<br>defined in Firestorm®|
|CardAccountNumber|C*|Unencrypted credit card number|String||
|CVV2Code|C*|Unencrypted CVV2 code from the credit card|String||
|CardHolderName|C*|Name as it appears on the card|String||
|CardExpirationMonth|C*|<br>2 digit number (zero filled) representing the<br>month of the expiration date|String|MM|
|CardExpirationYear|C*|<br>4 digit number representing the year of the<br>expiration date|String|YYYY|
|ShippingCode|Y|Shipper code|String|Any valid shipper as defined in<br>the Firestorm® system.<br>(tblShipper.Code)|
|ReplicatedWebsiteURL|Y|The unique name for the new enrollees<br>replicated website. This value is NOT fully|String||



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 93 | 317 

Firestorm® Web Services API | Version 2.2.33 

||qualified! (“http:www.myco.com/bob” would<br>be entered as “bob”)|||
|---|---|---|---|
|ReplicatedWebsitePassword|Y<br>Unencrypted password used by the new<br>member to access their web office|String||
|AddlPaymentInfo|Y<br>Any additional payment information that you<br>may need to capture. This value is stored in<br>the database but is not used in anyway)|String|Stored in<br>tblWebServiceAddlPaymentInfo|



* If the “PaymentTypeCode” is a credit card (as defined in Firestorm®) these fields are required 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Record being created must be in a country the web service<br>caller is authorized for. MailingCountrycontrols this access.)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The information passed into this web service is extensively validated against the database before allowing the enrollment to continue. Any validations that fail will be passed back to the caller as a complex XML document that will contain a complete listing of all validation failures. 

**Payment Processing** : This web service WILL process the payment for this order if the calculated total of the enrollment order is greater than zero. If the selected payment type is a credit card, the card will be charged for the order. If you do not wish the web service to process payment, you must configure the system so that the calculated total of the enrollment order is $0. If the web service does process payment, it will calculate the total amount to charge based on pricing, tax, shipping and other fees configurations in the system. 

**Currency Conversion:** When an order is being processed by the system for this enrollment, the system will look up the country specified in “BillingCountry” to see if a default currency has been defined for that country. If it has, the currency type and the defined conversion ratio for that currency will be saved as part of the order. Normal Firestorm® currency processing will still occur based on system setup and configurations. 

The web service will create the Dealer, Dealership and Order records as required by the system. Once a successful call has been made to this web service, the new member will be enrolled and ready to go. 

##### <u>Order Detail XML</u> 

When calling this web service, this field allows you to build the order to be used for the enrollment order on your system, then pass it over to Firestorm® as an XML document as shown below.  You will build an <ORDERDETAIL> element for each line item in your order, then embed them all in a containing <ORDER> element. This payload is not limited to the number of items that may be specified for a single order, allowing you to specify the order contents and pricing in any way necessary to meet your need. 

When building this document, remember that even though you can override pricing for a given product, that product MUST exist in the catalog specified in your call. If a product is missing, the call will fail. 

The <ORDER> element must contain at least 1 <ORDERDETAIL> element. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 94 | 317 

Firestorm® Web Services API | Version 2.2.33 

**_Hint:_** _The passed XML document must be completely valid so that it may be parsed correctly by Firestorm®. Please test your XML document thoroughly to ensure that it can be loaded without error by an XML parser. This will avoid problems with your successful use of this web service._ 

The following listing is an example XML document: 

```
///////////////////////////
Sample order detail XML
///////////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<ORDER itemcount='1'>
```

```
   <ORDERDETAIL>
```

```
      <PRODUCTNUMBER>string</PRODUCTNUMBER>
```

```
      <PRODUCTQTY>integer</PRODUCTQTY>
```

```
      <PRICEEACH>double</PRICEEACH>
```

```
      <RETAILPRICEEACH>double</RETAILPRICEEACH>
```

```
      <WHOLESALEPRICEEACH>double</WHOLESALEPRICEEACH>
```

```
      <UPLINEVOLUMEEACH>double</UPLINEVOLUMEEACH>
```

```
      <PSVAMOUNTEACH>double</PSVAMOUNTEACH>
```

```
      <ISFREEPRODUCT>boolean</ISFREEPRODUCT>
```

```
      <FREESHIPPING>boolean</FREESHIPPING>
```

```
    </ORDERDETAIL>
```

```
</ORDER>
```

The following table breaks out and defines each element of this document. 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|<?xml ……|||Required XML document header(see example above|
|ORDER||“Itemcount” – total<br>number of ORDERDETAIL<br>elements|Containing envelope for order|
|ORDERDETAIL|||Containingenvelope for one line item on an order|
|PRODUCTNUMBER|String||Product number that exists in the catalog specified in the web service<br>call|
|PRODUCTQTY|Integer||Quantityof this item to order|
|PRICEEACH|Double||Actual price paid for EACH item (do not multiply this by<br>PRODUCTQTY. The system will do that for you).<br>**WARNING: Only set this value if you are NOT providing**<br>**Retail/Wholesale/Upline/PSV. If you set this value it will override**<br>**what is in the Retail/Wholesale price fields!**<br>**If you are providing explicit pricing using the fields below, set this**<br>**value to $0**|
|RETAILPRICEEACH|Double||Retail price for each product. Do not multiply by PRODUCTQTY.<br>Setting this value to -1 will cause the system to use the price<br>configured in the catalog.|
|WHOLESALEPRICEEACH|Double||Wholesale price for each product. Do not multiply by PRODUCTQTY.<br>Setting this value to -1 will cause the system to use the price<br>configured in the catalog.|
|UPLINEVOLUMEEACH|Double||Upline (commissionable) volume for each product. Do not multiply by<br>PRODUCTQTY. Setting this value to -1 will cause the system to use the<br>price configured in the catalog.|
|PSVAMOUNTEACH|Double||PSV Amount for each product. Do not multiply by PRODUCTQTY.<br>Setting this value to -1 will cause the system to use the price<br>configured in the catalog.|
|ISFREEPRODUCT|Boolean||Flag to indicate if this is a free product. “True” = is a free product,<br>“False” = not a freeproduct|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 95 | 317 

Firestorm® Web Services API | Version 2.2.33 

|FREESHIPPING|Boolean|Flag to indicate if shipping charges should be suppressed for this<br>product. “True” = no shipping will be calculated, “False” = shipping<br>charges will be calculated normally.|
|---|---|---|



##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

##### Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ID>integer</ID>
<ORDERID>integer</ORDERID>
<DEALERSHIPID>integer</DEALERSHIPID>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS: The DealerID that was created for the new enrollee|
|ORDERID|Integer||On SUCCESS: The OrderID of the enrollment order.|
|DEALERSHIPID|Integer||On SUCCESS: The DealershipID of the newposition created for the new enrollee|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 96 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormEnrollmentWS.EnrollMemberAsOrphan 

Performs all of the tasks required to enroll a new member into the system, but will NOT insert them into the main structure. They will be created as an orphan, not attached to the main structure. When a member is created as an orphan, the new enrollee will be able to do business normally, but because they are not attached to the main structure their volume (and their downline volume) WILL NOT MOVE UPLINE. When the orphan is resolved (attached back to the main structure) the volume will still not move upline. After resolution, any future volume will credit upline based on the compensation plan. 

This method is used to enroll a person who will participate in the compensation plan as a distributor. (DO NOT use this method to enroll a customer) 

**NOTE:** This method is designed to enroll a member who purchases a SINGLE product to enroll. 

**PCI/DSS WARNING:** This web service uses sensitive personal and payment information to process an enrollment. It is YOUR responsibility to ensure that you are following all proper PCI/DSS procedures in addition to accessing the web service over a secure (https) link in your production environment!! 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|Security Token assigned to you by<br>support|String|Issued by Firestorm® Support|
|Context|Y|Context value assigned to you by<br>support|String|Issued by Firestorm® Support|
|FirstName|Y|First name of new member|String||
|MiddleInitial|Y||String||
|LastName|Y||String||
|CompanyName|Y|If a company name is supplied, it will be<br>used on all commission checks and will<br>be displayed ongenealogyreports.|String||
|TaxPayerNumber|Y|Government issued ID number.<br>Typically SSN (for 1099 reporting<br>purposes in the USA)|String|Apply formatting as desired|
|MailingAddress1|Y|Stored in the shipping address fields in<br>Firestorm® (don’t ask why, just believe<br>it!)|String||
|MailingAddress2|Y|“|String||
|MailingCity|Y|“|String||
|MailingState|Y|“|String|As defined in Firestorm®.<br>tblState.StateID|
|MailingZip|Y|“|String||
|MailingCountry|Y|“|String|As defined in Firestorm®.<br>tblCountry.CountryID|
|BillingAddress1|Y|Stored in the Mailing address fields in<br>Firestorm®  (don’t ask why, just believe<br>it!)|String||
|BillingAddress2|Y|“|String||
|BillingCity|Y|“|String||
|BillingState|Y|“|String|As defined in Firestorm®.<br>tblState.StateID|
|BillingZip|Y|“|String||
|BillingCountry|Y|“|String|As defined in Firestorm®.<br>tblCountry.CountryID|
|DayPhone|Y|No formatting is applied. If you want a<br>specific format for phone numbers,<br>applyit before sending.|String||



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 97 | 317 

Firestorm® Web Services API | Version 2.2.33 

|EveningPhone<br>MobilePhone|Y<br>Y|“<br>“|String<br>String||
|---|---|---|---|---|
|Email|Y|Full email address|String||
|CatalogueID|Y|The specific catalogue as defined in<br>Firestorm® to place the enrollment<br>order against.|Integer|Any active enrollment catalog<br>in Firestorm®|
|ProductNumber|Y|Theproduct number being purchased|String|Must exist in specified catalog|
|Price|Y|LEGACY – NOT USED. The actual price<br>of the enrollment will be calculated<br>using the specified product’s pricing in<br>the catalog. All tax, shipping and other<br>fees will be calculated based on system<br>configurations.|Double|Must be >= 0|
|DealershipTypeCode|Y|The rank that the person is enrolling as.||Must exist in<br>tblDealershipType.Code|
|MemberEnrollerID|Y|This will be the dealerID of the sponsor<br>for this member. (Enroller and Sponsor<br>are almost always the same. Do not<br>deviate from this unless your system is<br>configured differently)|Integer|DealerID must exist in the<br>system|
|MemberEnrollerPosition|Y|The dealership number (NOT<br>DealershipID) to credit this enrollment<br>to. Will be set to “1” in almost all cases.|Integer|Any existing dealership number<br>for the enroller|
|SponsorMemberiD|Y|<br>This will be the dealerID of the sponsor<br>for this member. (Enroller and Sponsor<br>are almost always the same. Do not<br>deviate from this unless your system is<br>configured differently)|Integer|DealerID must exist in the<br>system|
|SponsorPosition|Y|The dealership number (NOT<br>DealershipID) to credit this enrollment<br>to. Will be set to “1” in almost all cases.|Integer|Any existing dealership number<br>for the sponsor|
|BinaryPlacementMemberID|Y|Not used – You mustpass -1 in this field||-1|
|BinaryPlacementPosition|Y|Not used – You mustpass -1 in this field||-1|
|BinaryPlacementLineage|Y|Not used – You must pass “A” in this<br>field||“A”|
|UniPlacementMemberID|Y|<br>Not used – You mustpass -1 in this field||-1|
|UniPlacementPosition|Y|Not used – You mustpass -1 in this field||-1|
|PaymentTypeCode|Y|The payment type to be used to<br>process this order.|String|Any valid payment type as<br>defined in Firestorm®|
|CardAccountNumber|C*|Unencrypted credit card number|String||
|CVV2Code|C*|Unencrypted CVV2 code from the<br>credit card|String||
|CardHolderName|C*|Name as it appears on the card|String||
|CardExpirationMonth|C*|2 digit number (zero filled)<br>representing the month of the<br>expiration date|String|MM|
|CardExpirationYear|C*|4 digit number representing the year of<br>the expiration date|String|YYYY|
|ShippingCode|Y|Shipper code|String|Any valid shipper as defined in<br>the Firestorm® system.<br>(tblShipper.Code)|
|ReplicatedWebsiteURL|Y|The unique name for the new enrollees<br>replicated website. This value is NOT<br>fully qualified!<br>(“http:www.myco.com/bob” would be<br>entered as “bob”)|String||
|ReplicatedWebsitePassword|Y|<br>Unencrypted password used by the<br>new member to access their web office|String||
|AddlPaymentInfo|Y|Any additional payment information<br>that you may need to capture. This<br>value is stored in the database but is<br>not used in anyway)|String|Stored in<br>tblWebServiceAddlPaymentInfo|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 98 | 317 

Firestorm® Web Services API | Version 2.2.33 

* If the “PaymentTypeCode” is a credit card (as defined in Firestorm®) these fields are required 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Record being created must be in a country the web service<br>caller is authorized for. MailingCountrycontrols this access.)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The information passed into this web service is extensively validated against the database before allowing the enrollment to continue. Any validations that fail will be passed back to the caller as a complex XML document that will contain a complete listing of all validation failures. 

**Payment Processing** : This web service WILL process the payment for this order if the calculated total of the enrollment order is greater than zero. If the selected payment type is a credit card, the card will be charged for the order. If you do not wish the web service to process payment, you must configure the system so that the calculated total of the enrollment order is $0. If the web service does process payment, it will calculate the total amount to charge based on pricing, tax, shipping and other fees configurations in the system. 

**Currency Conversion:** When an order is being processed by the system for this enrollment, the system will look up the country specified in “BillingCountry” to see if a default currency has been defined for that country. If it has, the currency type and the defined conversion ratio for that currency will be saved as part of the order. Normal Firestorm® currency processing will still occur based on system setup and configurations. 

The web service will create the Dealer, Dealership and Order records as required by the system. Once a successful call has been made to this web service, the new member will be enrolled and ready to go. 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

##### Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ID>integer</ID>
<ORDERID>integer</ORDERID>
<DEALERSHIPID>integer</DEALERSHIPID>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 99 | 317 

Firestorm® Web Services API | Version 2.2.33 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS: The DealerID that was created for the new enrollee|
|ORDERID|Integer||On SUCCESS: The OrderID of the enrollment order.|
|DEALERSHIPID|Integer||On SUCCESS: The DealershipID of the newposition created for the new enrollee|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 100 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormEnrollmentWS.EnrollCustomer 

Enrolls a customer into the Firestorm® system. This web service will NOT create a member. The records created will only be in support of a Customer. Any customer type may be created through this call. Please note that structure position (dealership) will NOT be created when this call is made. 

Ensure that you understand the difference between a customer and a dealer in the Firestorm® system to ensure that you are making the correct call. If you need help understanding the differences, please contact our support department. 

|Method Definitio|n||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|FirstName|C|First name of new customer (Required if no<br>companyname supplied)|String||
|MiddleInitial|C||String||
|LastName|C|(Required if no companyname supplied)|String||
|CompanyName|C|If a company name is supplied, it will be used on all<br>commission checks and will be displayed on<br>genealogy reports. (not required if first and last<br>name are supplied)|String||
|MailingAddress1|N|Stored in the shipping address fields in Firestorm®<br>(don’t ask why, just believe it!)|String||
|MailingAddress2|N|“|String||
|MailingCity|N|“|String||
|MailingState|N|If this value is provided it will be used. If no value is<br>provided (i.e.: “”) , then the system will attempt to<br>look up the default state ID as defined in the<br>system. If it exists,then that will be used instead.|String|As defined in<br>Firestorm®.<br>tblState.StateID|
|MailingZip|N|“|String||
|MailingCountry|C|If this value is provided it will be used. If no value is<br>provided (i.e.: “”) , then the system will attempt to<br>look up the default country ID as defined in the<br>system. If it exists,then that will be used instead.|String|As defined in<br>Firestorm®.<br>tblCountry.CountryID|
|BillingAddress1|N|Stored in the Mailing address fields in Firestorm®<br>(don’t ask why, just believe it!)|String||
|BillingAddress2|N|“|String||
|BillingCity|N|“|String||
|BillingState|C|If this value is provided it will be used. If no value is<br>provided (i.e.: “”) , then the system will attempt to<br>look up the default state ID as defined in the<br>system. If it exists,then that will be used instead.|String|As defined in<br>Firestorm®.<br>tblState.StateID|
|BillingZip|N|“|String||
|BillingCountry|N|If this value is provided it will be used. If no value is<br>provided (i.e.: “”) , then the system will attempt to<br>look up the default country ID as defined in the<br>system. If it exists,then that will be used instead.|String|As defined in<br>Firestorm®.<br>tblCountry.CountryID|
|DayPhone|N|No formatting is applied. If you want a specific<br>format forphone numbers,applyit before sending.|String||
|EveningPhone|N|“|String||
|MobilePhone|N|“|String||
|Email|Y|Full email address|String||
|SponsorMemberID|Y|This is the DealerID of the member or customer<br>who is sponsoring the new customer. If this<br>DealerID belongs to another customer, the new<br>customer will be linked to the original member who<br>sponsored the sponsoringcustomer.|Integer|Any valid DealerID<br>that exists in the<br>Firestorm® system.|
|Username|N|The unique personal portion of a replicated website<br>URL. This is not a fully qualified URL.|String||



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 101 | 317 

Firestorm® Web Services API | Version 2.2.33 

|WebsitePassword|N|Unencrypted password to use when the customer<br>logs in to the shopping cart or the virtual office (if<br>your systemprovides customer back offices)|String||
|---|---|---|---|---|
|CustomerType|N|Customer type code. If this value is not provided,<br>the system will use the default customer type<br>(usuallyRETAIL)as defined in the Firestorm system.|String|Any valid customer<br>type defined in<br>tblCustomerType.Code|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Record being edited must be in a country the web service caller<br>is authorized for)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

##### <u>No Payment Information Required</u> 

This web service does not support the collection of payment information, as becoming a customer does not require a purchase. 

##### <u>Address Information Not Required</u> 

If you desire to create a customer record without providing an address, simply pass in an empty string (“”) in all address fields. Please note, however, that if you do not provide a MailCountry the system will assign the country code for the default country as defined in the system. If you do not provide a MailState code, then the system will assign the default state code as defined in Firestorm. These same rules apply to BillCountry and BillState. 

##### <u>Preferred Customer</u> 

If you are attempting to create a preferred customer, you will need to call this web service in combination with other web services if your system requires a preferred customer to set up auto ships or make some other kind of purchase. You must use the web services correctly in compliance with your compensation plan requirements. 

##### <u>Customer Sponsor and Affiliate Enrollment</u> 

When enrolling a new customer, to ensure that commissions and volume credit correctly, a “SponsorDealerID” must be included. This dealerID may be either a member or another customer. 

When the sponsoring dealerID is another customer, the system will automatically perform an AFFILIATE enrollment (a customer of a customer). When this happens, the system will look up the MEMBER who sponsored the sponsoring customer and will assign the new customer to that member. So, the new customer is linked to the sponsoring customer, but is also linked to the member who sponsored the sponsoring customer. Both of the linkages are tracked by the system and can both be used depending on your compensation plan. 

##### <u>Customer Type Code Will Default</u> 

If the customer type code is not provided on this call, the system will look up the default customer type as defined in Firestorm® and will assign that code by default. 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 102 | 317 

Firestorm® Web Services API | Version 2.2.33 

Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ID>integer</ID>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS: The DealerID that was created for the new customer|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 103 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormEnrollmentWS.EnrollMemberInHoldingTank 

Performs all of the tasks required to enroll a new member into the system, but will NOT insert them into the main structure. Instead, the new member will be placed into their sponsor’s holding tank. When a member is into their sponsors holding tank, the new enrollee will be able to do business normally, but because they are not attached to the main structure their volume (and their downline volume) WILL NOT MOVE UPLINE. When the new member is moved out of the holding tank (attached back to the main structure) ALL previously accumulated volume will be injected into the main structure based on the compensation plan. This includes any accumulated volume that may have already been paid on. As an example, a member in the holding tank accumulates 100 points of volume, then has that volume flushed to 0. The member then accumulates another 100 points of volume, bringing that member’s total accumulated volume to 200. The member is then removed from the holding tank. At that time, 200 points of volume would be injected into the structure. 

This method is used to enroll a person who will participate in the compensation plan as a distributor. (DO NOT use this method to enroll a customer) 

**PCI/DSS WARNING:** This web service uses sensitive personal and payment information to process an enrollment. It is YOUR responsibility to ensure that you are following all proper PCI/DSS procedures in addition to accessing the web service over a secure (https) link in your production environment!! 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String|Issued byFirestorm® Support|
|Context|Y|Context value assigned toyou bysupport|String|Issued byFirestorm® Support|
|FirstName|Y|First name of new member|String||
|MiddleInitial|Y||String||
|LastName|Y||String||
|CompanyName|Y|If a company name is supplied, it will be used<br>on all commission checks and will be displayed<br>ongenealogyreports.|String||
|TaxPayerNumber|Y|Government issued ID number. Typically SSN<br>(for 1099 reporting purposes in the USA)|String|Apply formatting as desired|
|MailingAddress1|Y|Stored in the shipping address fields in<br>Firestorm®(don’t ask why, just believe it!)|String||
|MailingAddress2|Y|“|String||
|MailingCity|Y|“|String||
|MailingState|Y|“|String|As defined in Firestorm®.<br>tblState.StateID|
|MailingZip|Y|“|String||
|MailingCountry|Y|“|String|As defined in Firestorm®.<br>tblCountry.CountryID|
|BillingAddress1|Y|Stored in the Mailing address fields in<br>Firestorm®(don’t ask why, just believe it!)|String||
|BillingAddress2|Y|“|String||
|BillingCity|Y|“|String||
|BillingState|Y|“|String|As defined in Firestorm®.<br>tblState.StateID|
|BillingZip|Y|“|String||
|BillingCountry|Y|“|String|As defined in Firestorm®.<br>tblCountry.CountryID|
|DayPhone|Y|No formatting is applied. If you want a specific<br>format for phone numbers, apply it before<br>sending.|String||
|EveningPhone|Y|“|String||
|MobilePhone|Y|“|String||



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 104 | 317 

Firestorm® Web Services API | Version 2.2.33 

|Email<br>CatalogueID|Y<br>Y|Full email address<br>The specific catalogue as defined in<br>Firestorm® to place the enrollment order<br>against|String<br>Integer|Any active enrollment catalog<br>in Firestorm®|
|---|---|---|---|---|
|OrderDetail|Y|.<br>Complex XML document describing the order<br>to beplaced|String|See detailed information below|
|OrderTotalAmt|Y||Double|Must be equal to the total<br>amount of the products<br>specified on the order (not<br>including tax and shipping and<br>other fees).<br>**OVERRIDE**: If a value of -99 is<br>passed in this field, the system<br>will not validate the total of the<br>products on the XML document<br>“OrderDetail” against this<br>number.|
|DealershipTypeCode|Y|The rank that the person is enrolling as.||Must exist in<br>tblDealershipType.Code|
|MemberEnrollerID|Y|This will be the dealerID of the sponsor for this<br>member. (Enroller and Sponsor are almost<br>always the same. Do not deviate from this<br>unlessyour system is configured differently)|Integer|DealerID must exist in the<br>system|
|MemberEnrollerPosition|Y|The dealership number (NOT DealershipID) to<br>credit this enrollment to. Will be set to “1” in<br>almost all cases.|Integer|Any existing dealership number<br>for the enroller|
|SponsorMemberiD|Y|<br>This will be the dealerID of the sponsor for this<br>member. (Enroller and Sponsor are almost<br>always the same. Do not deviate from this<br>unlessyour system is configured differently)|Integer|DealerID must exist in the<br>system|
|SponsorPosition|Y|The dealership number (NOT DealershipID) to<br>credit this enrollment to. Will be set to “1” in<br>almost all cases.|Integer|Any existing dealership number<br>for the sponsor|
|BinaryPlacementMemberID|Y|For BINARY systems, this will be the DealerID<br>of the owner of the dealership that you want<br>to place the new enrollee directly under. FOR<br>NON-BINARY systems, this will be the same as<br>“SponsorMemberID”|Integer|DealerID must exist in the<br>system|
|BinaryPlacementPosition|Y|For BNARY systems, this is the dealership<br>number of the dealership you want to place<br>the new enrollee directly under. FOR NON-<br>BINARY systems,default this value to “1”|Integer|Any existing dealership number<br>for the dealerID specified in<br>“BinaryPlacementMemberID”|
|BinaryPlacementLineage|Y|For BINARY systems, this field will indicate<br>which side (left or right) of the<br>“BinaryPLacementPosition” that you wish to<br>place the new enrollee on|String|“L” or “R” or “W”<br>(L)eft<br>(R)ight<br>(W)eak Side|
|UniPlacementMemberID|Y|The DealerID of the existing dealer who will<br>have the new enrollee placed on their<br>frontline. For UNILEVEL systems, this will<br>almost always be the same value as<br>“SponsorMemberID”. For BINARY systems,<br>this will always be the same value as<br>“SponsorMemberID”|Integer|DealerID must exist in the<br>system|
|UniPlacementPosition|Y|<br>The dealership number (not dealershipID) of<br>the existing dealership where the new<br>enrollee will be placed. For BINARY systems,<br>this should be the same value as<br>“SponsorPosition”|Integer|Any existing dealership number<br>for the dealerID specified in<br>“UniPlacementMemberID”|
|PaymentTypeCode|Y|<br>The payment type to be used to process this<br>order.|String|Any valid payment type as<br>defined in Firestorm®|
|CardAccountNumber|C*|Unencrypted credit card number|String||
|CVV2Code|C*|Unencrypted CVV2 code from the credit card|String||
|CardHolderName|C*|<br>Name as it appears on the card|String||



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 105 | 317 

Firestorm® Web Services API | Version 2.2.33 

|CardExpirationMonth|C*|2 digit number (zero filled) representing the<br>month of the expiration date|String|MM|
|---|---|---|---|---|
|CardExpirationYear|C*|4 digit number representing the year of the<br>expiration date|String|YYYY|
|ShippingCode|Y|Shipper code|String|Any valid shipper as defined in<br>the Firestorm® system.<br>(tblShipper.Code)|
|ReplicatedWebsiteURL|Y|The unique name for the new enrollees<br>replicated website. This value is NOT fully<br>qualified! (“http:www.myco.com/bob” would<br>be entered as “bob”)|String||
|ReplicatedWebsitePassword|Y|Unencrypted password used by the new<br>member to access their web office|String||
|AddlPaymentInfo|Y|Any additional payment information that you<br>may need to capture. This value is stored in<br>the database but is not used in anyway)|String|Stored in<br>tblWebServiceAddlPaymentInfo|



* If the “PaymentTypeCode” is a credit card (as defined in Firestorm®) these fields are required 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Record being created must be in a country the web service<br>caller is authorized for. MailingCountrycontrols this access.)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The information passed into this web service is extensively validated against the database before allowing the enrollment to continue. Any validations that fail will be passed back to the caller as a complex XML document that will contain a complete listing of all validation failures. 

**Payment Processing** : This web service WILL process the payment for this order if the calculated total of the enrollment order is greater than zero. If the selected payment type is a credit card, the card will be charged for the order. If you do not wish the web service to process payment, you must configure the system so that the calculated total of the enrollment order is $0. If the web service does process payment, it will calculate the total amount to charge based on pricing, tax, shipping and other fees configurations in the system. 

**Currency Conversion:** When an order is being processed by the system for this enrollment, the system will look up the country specified in “BillingCountry” to see if a default currency has been defined for that country. If it has, the currency type and the defined conversion ratio for that currency will be saved as part of the order. Normal Firestorm® currency processing will still occur based on system setup and configurations. 

The web service will create the Dealer, Dealership and Order records as required by the system. Once a successful call has been made to this web service, the new member will be enrolled and ready to go. 

##### <u>Order Detail XML</u> 

When calling this web service, this field allows you to build the order to be used for the enrollment order on your system, then pass it over to Firestorm® as an XML document as shown below.  You will build an <ORDERDETAIL> element for each line item in your order, then embed them all in a containing <ORDER> element. This payload is 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 106 | 317 

Firestorm® Web Services API | Version 2.2.33 

not limited to the number of items that may be specified for a single order, allowing you to specify the order contents and pricing in any way necessary to meet your need. 

When building this document, remember that even though you can override pricing for a given product, that product MUST exist in the catalog specified in your call. If a product is missing, the call will fail. 

The <ORDER> element must contain at least 1 <ORDERDETAIL> element. 

**_Hint:_** _The passed XML document must be completely valid so that it may be parsed correctly by Firestorm®. Please test your XML document thoroughly to ensure that it can be loaded without error by an XML parser. This will avoid problems with your successful use of this web service. When passing your order detail XML, make sure you encapsulate the order detail XML document with a CDATA tag to avoid parser errors._ 

The following listing is an example XML document: 

```
///////////////////////////
Sample order detail XML
///////////////////////////
```

```
<?xml version='1.0' encoding='utf-8' ?>
<ORDER itemcount='1'>
```

```
   <ORDERDETAIL>
```

```
      <PRODUCTNUMBER>string</PRODUCTNUMBER>
```

```
      <PRODUCTQTY>integer</PRODUCTQTY>
```

```
      <PRICEEACH>double</PRICEEACH>
```

```
      <RETAILPRICEEACH>double</RETAILPRICEEACH>
```

```
      <WHOLESALEPRICEEACH>double</WHOLESALEPRICEEACH>
```

```
      <UPLINEVOLUMEEACH>double</UPLINEVOLUMEEACH>
```

```
      <PSVAMOUNTEACH>double</PSVAMOUNTEACH>
```

```
      <ISFREEPRODUCT>boolean</ISFREEPRODUCT>
```

```
      <FREESHIPPING>boolean</FREESHIPPING>
```

```
    </ORDERDETAIL>
```

```
</ORDER>
```

The following table breaks out and defines each element of this document. 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|<?xml ……|||Required XML document header(see example above|
|ORDER||“Itemcount” – total<br>number of ORDERDETAIL<br>elements|Containing envelope for order|
|ORDERDETAIL|||Containingenvelope for one line item on an order|
|PRODUCTNUMBER|String||Product number that exists in the catalog specified in the web service<br>call|
|PRODUCTQTY|Integer||Quantityof this item to order|
|PRICEEACH|Double||Actual price paid for EACH item (do not multiply this by<br>PRODUCTQTY. The system will do that for you).<br>**WARNING: Only set this value if you are NOT providing**<br>**Retail/Wholesale/Upline/PSV. If you set this value it will override**<br>**what is in the Retail/Wholesale price fields!**<br>**If you are providing explicit pricing using the fields below, set this**<br>**value to $0**|
|RETAILPRICEEACH|Double||Retail price for each product. Do not multiply by PRODUCTQTY.<br>Setting this value to -1 will cause the system to use the price<br>configured in the catalog.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 107 | 317 

Firestorm® Web Services API | Version 2.2.33 

|WHOLESALEPRICEEACH|Double|Wholesale price for each product. Do not multiply by PRODUCTQTY.<br>Setting this value to -1 will cause the system to use the price<br>configured in the catalog.|
|---|---|---|
|UPLINEVOLUMEEACH|Double|Upline (commissionable) volume for each product. Do not multiply by<br>PRODUCTQTY. Setting this value to -1 will cause the system to use the<br>price configured in the catalog.|
|PSVAMOUNTEACH|Double|PSV Amount for each product. Do not multiply by PRODUCTQTY.<br>Setting this value to -1 will cause the system to use the price<br>configured in the catalog.|
|ISFREEPRODUCT|Boolean|Flag to indicate if this is a free product. “True” = is a free product,<br>“False” = not a freeproduct|
|FREESHIPPING|Boolean|Flag to indicate if shipping charges should be suppressed for this<br>product. “True” = no shipping will be calculated, “False” = shipping<br>charges will be calculated normally.|



##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ID>integer</ID>
<ORDERID>integer</ORDERID>
<DEALERSHIPID>integer</DEALERSHIPID>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS: The DealerID that was created for the new enrollee|
|ORDERID|Integer||On SUCCESS: The OrderID of the enrollment order.|
|DEALERSHIPID|Integer||On SUCCESS: The DealershipID of the newposition created for the new enrollee|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 108 | 317 

Firestorm® Web Services API | Version 2.2.33 

### FirestormGenealogyWS 

|General Informa<br>Name|tion<br>FirestormGenealogyWS.asmx|
|---|---|
|WSDL|https://www.firestormwebservices.com/FirestormWebServices/FirestormGenealogyWS.asmx|
|Description|This web service will contain all methods necessary to retrieve a members genealogy. Each<br>method is described below, along with the definition of each argument and valid values<br>where appropriate.|



|Method Summary||
|---|---|
|Method Name|Return Type|
|GetDownlineByDealerID|Datatable|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 109 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormGenealogyWS.GetDownlineByDealerID 

Retuns a data table containing a list of the downline for the specified dealer/dealership number. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The unique dealerID number to get results for|Numeric|Must be an existing<br>DealerID in the<br>system|
|DealershipNumber|Y|The dealership number (NOT dealershipID) that will<br>be the starting point to pull the downline for|Integer|Must be a dealership<br>number currently in<br>the system for the<br>requested dealer.<br>Typically passing in<br>“1” will pull<br>everything for a<br>given dealer.|
|ReportCode|Y|The actual report code that represents the data set<br>that you wish to have returned.<br>If you wish to use this capability, please contact our<br>support department forguidance.|String|See notes below.<br>Pass in and empty<br>string (“”) to use<br>standard output as<br>described below.|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes. If the requested Dealer is in a country that the web service<br>caller is authorized for, the system will pull the downline.<br>WARNING: If the downline contains records that the web service<br>caller is not authorized for, the records WILL be returned anyway.<br>This is required to maintain the integrity of the downline. NO<br>FILTERING OF UNAUTHORIZED COUNTRIES WILL OCCUR.|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The output of this web service is controlled by the WebGenealogy control engine in Firestorm®. This means that the ouput returned by this web service is configurable by using the web genealogy control screens in the admin interface in Firestorm and assigning the fields you wish to output to the genealogy report set up specifically for this web service. 

When adding fields to the output, use the report name of “WebServiceGenealogy”. This form is located in the administrative interface using the menu path of File->Configuration->Web->Web Genealogy Configuration. Once this form is displayed, select the report titled “WebServiceGenealogy” from the drop down list. Any field assigned to the report will be output as a data table by this web service. 

Be aware that depending on the type of system you are retrieving data from (BINARY or UNILEVEL) this web service will return slightly different results. Pay attention to the tables below to determine the exact result set for your call. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 110 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### <u>Custom Report Codes</u> 

This web service includes the ability to specify the exact pre-defined dataset that you wish to have returned by this call. This will allow you to specify as many different datasets as necessary for your application simply by using different report codes that represent each dataset. 

Coordinate your requests with our support department to implement this functionality. 

##### <u>Binary / Unilevel Hybrid Systems</u> 

This web service will always return the genealogy based on the base system type of your system. This affects you if your system is a BINARY hybrid, and are attempting to pull the Unilevel structure. This web service will not directly return that structure to you. However, if you need this information you can derive it if you add the field “UnilevelPlacementDealershipID” as one of the user configured fields for output. Once you have this information, you can perform the processing necessary on your end to derive the unilevel structure. All positions on a particular dealership’s front line will all point to the same DealershipID. 

##### **<u>Return Values</u>** 

When the web service returns data from a call, depending on the type of system the result set is slightly different. The two tables below specify the standard fields that will always be returned for each system type (BINARY or UNILEVEL), in addition to all user assigned fields. 

|Returned Data for BINARY systems<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|InsertOrder|Integer|INTERNAL USE. DO NOT USE.|
|SortField|Integer|Sorting the dataset by this value will render the list in<br>structure order.|
|InternalLevelNumber|Integer|The level of the user’s structure that this record is on. Please<br>note that these level numbers are relative to the person at<br>the top of the downline. The person at the top of the tree will<br>appear as level 1.|
|DealershipID|Integer|The DealershipID of thispersons structureposition|
|WorkDealerID|Integer|The DealerID of thisperson|
|AccumulateVolume|Boolean|Flag to indicate it this position is currently accumulating<br>volume in the binary. -1 = Accumulating volume normally, 0 =<br>Not accumulating.|
|BaseCommissionQualified|Boolean|Flag to indicate the status of the BCQ flag for this dealership. -<br>1 = ISqualified for commissions,|
|UnilevelQualified|Boolean|LEGACY. DO NOT USE.|
|PersonallySponsored|Boolean|Flag to indicate is this person was personally sponsored by the<br>dealer that this downline waspulled for.|
|PLUS ANY USER CONFIGURED FIELDS|||



|Returned Data for UNILEVEL systems<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|SortField|Integer|Sorting the dataset by this value will render the list in<br>structure order.|
|DealershipID|Integer|The DealershipID of thispersons structureposition|
|ParentDealershipID|Integer|The DealershipID of the position that this dealership is directly<br>UNDER. Generally speaking, this is the sponsor’s position, BUT<br>this is not always true due to the fact that a dealership can be<br>moved or placed differently in Firestorm® if the compensation<br>plan allows this behavior.|
|WorkDealerID|Integer|The DealerID of thisperson|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 111 | 317 

Firestorm® Web Services API | Version 2.2.33 

|InternalLevelNumber|Integer|The level of the user’s structure that this record is on. Please<br>note that these level numbers are relative to the person at<br>the top of the downline. The person at the top of the tree will<br>appear as level 1.|
|---|---|---|
|AccumulateVolume|Boolean|Flag to indicate it this position is currently active. This field<br>correlates with tblDealershipStatus.AccumulateVolume so<br>before using it make sure you understand how it is being<br>implemented in your specific compensation plan. -1 =<br>Accumulatingvolume normally,0 = Not accumulating.|
|UnilevelQualified|Boolean|LEGACY. DO NOT USE.|
|PersonallySponsored|Boolean|Flag to indicate is this person was personally sponsored by the<br>dealer that this downline waspulled for.|
|PLUS ANY USER CONFIGURED FIELDS|||



### FirestormInventoryWS 

|General Inform|ation|
|---|---|
|Name|FirestormInventoryWS.asmx|
|WSDL|https://www.firestormwebservices.com/FirestormWebServices/FirestormInventoryWS.asmx|
|Description|Provides access into specific areas of the Firestorm® inventorysubsystem.|



|Method Summary||
|---|---|
|Method Name|Return Type|
|`GetCurrentInventoryCounts`|DataTable|
|AdjustInventory|Boolean|
|GetCatalogueList|DataTable|
|GetCatalogueContents|DataTable|
|GetCatalogueContentsV4Cart|DataTable|
|GetEntrollmentSpecialsByDealershipType|DataTable|
|GetProductItemDetail|DataTable|
|GetShoppingCartGroupCodeDetail|DataTable|
|GetVariationPathsForParentProduct|DataTable|
|GetInventoryCountsByProductID|DataTable|
|SaveProduct|Complex XML Document|
|SaveCatalogueProductDetail|Complex XML Document|
|GetProductList|DataTable|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 112 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.AdjustInventory 

Allows a remote system to modify inventory stock levels by submitting adjustment records for individual items in Firestorm. Both positive and negative adjustments are allowed to both on hand and staged inventor counts. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|ItemNumber|Y|The ItemNumber of the Item to update, as defined in<br>Firestorm|String|Any valid<br>ItemNumber defined<br>in Firestorm|
|Qty|Y|Thequantityto adjust inventorystock levels by|Integer|Anyvalid integer|
|AdjustmentTypeCode|Y|The code for the type of inventory update to<br>execute, as defined in Firestorm|String|Must be a valid code<br>as defined in<br>Firestorm|
|Comments|Y|A comment to be recorded on the inventory update<br>history.|String||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

##### <u>Valid Adjustment Type Codes</u> 

- POSITIVE – For positive adjustments to Quantity On Hand. 

- NEGATIVE – For negative Adjustments to Quantity On Hand 

- STAGED_NEG – For negative Adjustments to Staged Quantity. This code should not be used without guidance. Please contact our support department if you think you may need to use this field. 

- STAGED_POS – For positive Adjustments to Staged Quantity. This code should not be used without guidance. Please contact our support department if you think you may need to use this field. 

##### <u>Backordered Quantity</u> 

If you apply an inventory adjustment to an Item that currently has backordered quantity, the system will automatically manage the backordered status of the Item. No additional action will be required to remove items from backorder. 

##### **<u>Return Values</u>** 

The web service will return a Boolean value indicating whether or not the adjustment was successful. If a value of False is returned, you will need to review the web service transaction logs for details on the failure. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 113 | 317 

Firestorm® Web Services API | Version 2.2.33 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 114 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.GetCatalogueList 

Returns a list of catalogs, along with specific configuration details about those catalogs, based on search criteria supplied in the call. This list can be used to derive the CatalogueID required by other web services. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|CatalogueID|Y|The catalogueID for the catalog you wish to retrieve<br>from the system. Passing -1 will return a complete<br>list of all catalogues (subject to any additional<br>filtering provided byother arguments)|Integer|Any valid catalog as<br>defined in the<br>Firestorm® system.|
|CountryID|Y|The country code you wish to filter the returned list<br>by. Pass an empty string for no country filtering.|String|Any valid country<br>code defined in<br>Firestorm®|
|DealershipTypeID|C|The dealership type ID (rank) that you wish to filter<br>the list by. Pass -1 for no dealership type filtering.|Integer|Any valid dealership<br>type ID from<br>Firestorm®. This is a<br>numeric<br>representation of a<br>single rank. Pass in<br>“-1” if you want all<br>ranks or you are<br>using the<br>“RankCode”<br>parameter|
|RankCode|C|A string representing the single rank code that you<br>wish to filter the list by. Pass an empty string for no<br>rank code filtering.|String|Use this field to pass<br>in the actual code<br>(i.e.: “BRONZE”) if<br>you do not know the<br>DealershipTypeID.|
|ActiveOnly|Y|Flag to indicate to the system to only return catalogs<br>that are marked as active.|Boolean|0 = Return complete<br>list<br>Non-Zero = Return<br>only catalogs that are<br>marked as active.|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

Be aware that all search criteria is cumulative in nature. If you pass in multiple parameters to filter the returned list by, they will all be used together to filter the returned results. 

If you do not have access to the system to obtain the DealershipTypeID for the given rank you want, you may pass in the parameter “RankCode” to specify the rank you want by the actual code. This allows you to use codes such as “BRONZE”, “GOLD”, etc. The code you pass in must be defined in the Firestorm® System. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 115 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **<u>Return Values</u>** 

|Returned Data|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|CatalogueID|Integer|Unique ID assigned to the catalogbyFirestorm®|
|Name|String|Name of the catalog|
|Active|Boolean|Flag to indicate if this catalog is marked as active or not.<br>0 = Not Active<br>Non-Zero = Active|
|MinimumOrder|Double|The minimum amount of product (in monetary terms) that<br>must be ordered on a single order. This value is presented in<br>the base currencyof the system.|
|IsPublic|Boolean|Flag to indicate if this catalog is used for public orders (i.e.:<br>Retail purchases).<br>0 = Public catalog<br>Non-Zero = Non-Public catalog|
|IsEnrollment|Boolean|Flag to indicate if this catalog is used for enrollment orders.<br>0 = Not an enrollment catalog<br>Non-Zero = Enrollment catalog|
|IsAutoship|Boolean|Flag to indicate if this catalog is used for recurring orders.<br>Only catalogs with this flag set will appear in the recurring<br>order portal web tool.|
|||0= Not an autoship catalog<br>Non-Zero = Autoshipcatalog|
|IsParty|Boolean|Flag to indicate if this catalog is used for party orders. Only<br>catalogs with this flag set will appear in the party portal web<br>tool.|
|||0 = Not a party catalog<br>Non-Zero = Partycatalog|
|IsHostAward|Boolean|Flag to indicate if this catalog is used for party host award<br>orders. Only catalogs with this flag set will appear in the party<br>portal host award order web tool.|
|||0 = Not a party host award catalog<br>Non-Zero = Partyhost award catalog|
|UseDateFiltering|Boolean|Flag to indicate if this catalog is using date filtering. If it is, this<br>catalog should only be used during the time period specified<br>by the “StartDate” and “EndDate” fields|
|||0 = Do not use date filter. This catalog may be used any time.<br>Non-Zero = Use the date filter. This catalog may only be used<br>for orders during the date range specified by “StartDate” and<br>“EndDate”|
|StartDate|Date|The startingdate/time of the date filter window|
|EndDate|Date|The endingdate/time of the date filter window|
|CustomerTypeID|Integer|The ID of the type of customer that may order from this<br>catalog. Customer types are defined in Firestorm®|
|InHouseUseOnly|Boolean|Flag to indicate if this catalog is used for in-house orders only.<br>When this flag is set, this catalog should never be displayed<br>on the website. Typically this indicates that this is a special<br>use catalog (i.e.: Replacement orders, etc)|
|||0 = This catalog may be used on the web<br>Non-Zero = This catalogmayonlybe used for in-house orders.|
|IsStreaming|Boolean|Flag to indicate that this catalog can be used for live<br>streaming events. 0 = cannot be used, non-zero = CAN be<br>used for streamingevents.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 116 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.GetCatalogueContents 

Returns the contents of the specified catalog. This web service will provide all of the data necessary for you to build your own shopping cart display, as it contains all product information, including current pricing, image URLs and other items required for a shopping cart. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|CatalogueID|Y|The catalogueID for the catalog you wish to retrieve<br>from the system.<br>You may retrieve this number from the<br>administrative interface by opening the form<br>Inventory->Catalogs. The “ID” field on this form is<br>the number you are looking for.|Integer|Any valid catalog as<br>defined in the<br>Firestorm® system.|
|SuppressChildProducts|Y|Flag to either include or exclude child products from<br>the returned data.|Boolean|0 = Include child<br>products in the<br>returned data, -1 =<br>Do not return child<br>products in the<br>returned data.|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The returned data from this web service can be used to provide input for you to build your own shopping cart display. The returned information will contain everything you need to build a cart display. The engine behind this web service will provide current up to the date pricing, taking into account any sales that may be in progress, availability rules and all other configurable operational parameters that can be used in Firestorm®. 

##### <u>Child Products</u> 

The Firestorm® system uses to concept of parent and child products to control the display of variations of a given product. As an example, if widget A comes in 10 different colors, there will be 10 child products, each with their own product number and pricing. A parent product can be identified by the flag “IsParentProduct”. If this flag is a non-zero value, you must either build a variation display or suppress it from being displayed. 

You will need this information to build a variation display of your choosing. As a general rule, a parent product should never be offered for sale directly as it has no pricing associated with it. Only the related child products will have pricing and therefore are the only items eligible to be sold. You will need to build your display accordingly to maintain compliance with this rule. 

##### **<u>Return Values</u>** 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 117 | 317 

Firestorm® Web Services API | Version 2.2.33 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ProductID|Integer|The unique number assigned to thisproduct(for internal use)|
|GroupString|String|A string representing the groups that this product belongs to.<br>This is a concatenation of group numbers separated by a “.”<br>Character. For example: “60.72”. This would represent<br>GROUP1.GROUP2|
|Group1|string|Thegroup1 ID that thisproduct is assigned to.|
|Group2|string|Thegroup2 ID that thisproduct is assigned to|
|ProductNumber|String|Product number assigned in the “Product” form in the<br>Firestorm® admin interface.|
|WebName|String|The name of the product for display on the web. WARNING:<br>This field may contain HTML code and my contain UNICODE<br>characters.|
|WebDescription|String|The description of the product for display on the web.<br>WARNING: This field may contain HTML code and my contain<br>UNICODE characters.|
|PictureURL|String|The URL for the small picture of this product. This URL may or<br>may not be fully qualified. The system will allow relative URLs<br>to be entered. Check with the system administrator to<br>determine how they have been entered to determine if you<br>mayneed to make adjustments in the URL before use.|
|PageURL|String|If a product has a “more information” page associated with it,<br>this field will contain the URL to that page. May or may not be<br>fully qualified.|
|LargePictureURL|string|The URL for the large picture of this product. This URL may or<br>may not be fully qualified. The system will allow relative URLs<br>to be entered. Check with the system administrator to<br>determine how they have been entered to determine if you<br>mayneed to make adjustments in the URL before use.|
|RetailPrice|Double|Retail price AFTER any discounts, sales or adjustments have<br>been applied bythe system|
|WholesalePrice|Double|Wholesale price AFTER any discounts, sales or adjustments<br>have been applied bythe system|
|UplineAmount|Double|Commissionable value AFTER any discounts, sales or<br>adjustments have been applied bythe system.|
|PSVAmount|Double|Personal Sales Volume AFTER any discounts, sales or<br>adjustments have been applied by the system. Typically used<br>forqualificationpurposes in the compensationplan.|
|OriginalRetailPrice|Double|Retail price BEFORE any discounts, sales or adjustments have<br>been applied bythe system|
|OriginalWholesalePrice|Double|Wholesale price BEFORE any discounts, sales or adjustments<br>have been applied bythe system|
|OriginalUplineAmount|Double|Commissionable value BEFORE any discounts, sales or<br>adjustments have been applied bythe system.|
|OriginalPSVAmount|Double|Personal Sales Volume BEFORE any discounts, sales or<br>adjustments have been applied by the system. Typically used<br>forqualificationpurposes in the compensationplan.|
|PointValue|Double|If product points can be earned by purchasing this product,<br>this is the number of product points that will be awarded by<br>the system.|
|AllowPurchaseWithPoints|Boolean|<br>Flag to indicate that this product is eligible to be purchased<br>withproductpoints.(-1 = Eligible0 = not eligible)|
|PriceInPoints|Double|, <br>The cost of thisproduct inpoints.|
|AllowAsFreeProduct|Boolean|Flag to indicate if this product is eligible to be given as a free<br>product(0 = not eligible-1 = eligible)|
|MaxWebQty|Integer|, <br>Maximum quantity of this item that can be purchased at one<br>time(-1 = no limit)|
|OutOfStock|Boolean|. <br>Flag to indicate that this item is currently out of stock. (Should<br>be used with “AllowBackorder” to determine if you can allow<br>this item to be ordered)|
|IsParentProduct|Boolean|Flag to indicate that this product is a parent product (see<br>description in “**Additional Information**” section above. (0 =<br>Not aparentproduct,-1 = Is aparentproduct)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 118 | 317 

Firestorm® Web Services API | Version 2.2.33 

|InventoryGroupID|Integer|If this product is assigned to an inventory group, this ID value<br>is the actual group to which it is assigned. See the Firestorm®<br>Use and Operations Manual for more information on<br>InventoryGroups.|
|---|---|---|
|AllowBackorder|Boolean|Flag to indicate if this product is allowed to be backordered. If<br>this flag is set to -1, no order should be taken for this product<br>(suppress the “add to cart” button and display a message<br>accordingly)|
|SaleComment|String|When an item is on sale, this field will contain the name of the<br>sale as entered in Firestorm®.(i.e.: “All items 10% off”)|
|RetailSaleComment|String|When an item is on sale, this field will contain a comment<br>indicating how much was saved off of the retail price. i.e:<br>“(You save 24.97)”|
|WholesaleSaleComment|String|When an item is on sale, this field will contain a comment<br>indicating how much was saved off of the wholesale price. i.e:<br>“(You save 24.97)”|
|CatalogueID|Integer|The catalogueID that this data is for.|
|ParentStartingRetailPrice|Double|When this product is a parent product, this field contains a<br>comment that will indicate the retail price of the lowest<br>priced child product. (i.e: “From 9.95”). Since actual price may<br>vary based on the selection made by the user, this comment is<br>intended to be displayed at a higher level in the cart, before<br>the user clicks into the product detail page to make an actual<br>selection.|
|ParentStartingWholesalePrice|Double|When this product is a parent product, this field contains a<br>comment that will indicate the wholesale price of the lowest<br>priced child product. (i.e: “From 6.95”). Since actual price may<br>vary based on the selection made by the user, this comment is<br>intended to be displayed at a higher level in the cart, before<br>the user clicks into the product detail page to make an actual<br>selection.|
|DropShippingCharges|Boolean|Flag to indicate that this product should not increase the<br>shippingcost.(Free shipping)|
|SearchText|String|A concatenation of Product Number, Web Name and Web<br>Description. Use this field to perform wildcard searches<br>against the dataset for a specific product. (i.e: %lotion%). This<br>field is intended for use by search functions included in your<br>cart.|
|IsChildProduct|Boolean|Flag to indicate that this product is a child product (a variation<br>of the relatedparentproduct)|
|Group1ID|Integer|ShoppingCartGroupCodeID for the group 1 code assigned to<br>thisproduct|
|Group1|String|tblShoppingCartGroupCode.Code for the Group1 ID.|
|SuppressInShoppingCart|Boolean|Flag to indicate that this product should not be displayed in<br>the shoppingcart(0 = Displaynormally,-1 = Do not display)|
|DealershipTypeID|Integer|Used in conjunction with the “IsEnrollmentSpecial” flag. If this<br>product is an enrollment special, then this is the type of<br>dealershipthat it should be offered for.|
|IsEnrollmentSpecial|Boolean|Flag to indicate that is product is intended to be used as an<br>enrollment special (i.e.: an upsell during the enrollment<br>process) (0 = Not an enrollment special, -1 = Is an enrollment<br>special)|
|IsDynamicProduct|Boolean|Flag to indicate if this is a dynamic kit product (0 = Not a<br>dynamic kit,-1 = is a dynamic kit)|
|DynamicProductMaxQty|Integer|If this is a dynamic kit, this is the maximum quantity of this<br>product that maybe added to the kit|
|DynamicProductRequiredValue|Double|If this is a dynamic kit which requires a specified value, this is<br>the total value of theproducts that must be added to the kit.|
|DynamicProductValueType|String|When a dynamic product is a required value type, this is the<br>type of value. Valid values are “RETAIL”, “WHOLESALE”,<br>“UPLINE” or “PSV”. These values correlate directly to the<br>value fields in this dataset.|
|ProductName|String|The product name used internally. This value should not<br>contain anyHTML markup.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 119 | 317 

Firestorm® Web Services API | Version 2.2.33 

|NumItems|Integer|When this is a dynamic kit based on a number of products,<br>this value indicates the total number of products that must be<br>added to the kit.|
|---|---|---|
|QtyOnHand|Integer|Total quantity of this product available for purchase at the<br>time this dataset waspulled.|
|EligibleForRecurringOrder|Boolean|Flag to indicate that this product is eligible to be put onto a<br>recurring order (Autoship). (0 = may not be placed on a<br>recurring order, -1 = may be placed on a recurring order).<br>WARNING: Use this value in conjunction with<br>“CatalogAllowsRecurringOrder”. If**BOTH**flags are not set<br>to “-1”, then you maynotset up a recurring order for this<br>item!|
|CatalogAllowsRecurringOrder|Boolean|Flag to indicate if the catalog can be used to set up a recurring<br>order. IF THIS FLAG IS SET TO 0, YOU MUST IGNORE THE<br>“EligibleForRecurringOrder” flag. ( 0 = Not eligible, -1 = Is<br>eligible.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 120 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.GetCatalogueContentsV4Cart 

Returns the contents of the specified catalog for use only in the V4 shopping cart. This web service will provide all of the data necessary for you to build your own shopping cart display, as it contains all product information, including current pricing, image URLs and other items required for a shopping cart. 

|Method Definition|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|CatalogueID|Y|The catalogueID for the catalog you wish to retrieve<br>from the system.<br>You may retrieve this number from the<br>administrative interface by opening the form<br>Inventory->Catalogs. The “ID” field on this form is<br>the number you are looking for.|Integer|Any valid catalog as<br>defined in the<br>Firestorm® system.|
|ShoppingCartMasterGroupID|Y|Top level (master) grouping in the v4 cart.|Integer|Any valid master<br>group ID defined in<br>Firestorm.<br>Pass -1 in this field to<br>get all master<br>groups. (be aware<br>that a listing for a<br>given product will be<br>returned for EACH<br>master group it is<br>assigned to)|
|Group1ID|Y|Second level of grouping in the v4 cart||Any valid group 1 ID<br>defined in Firestorm.<br>Pass -1 to to not<br>search by group 1|
|Group2ID|Y|Third level of grouping in the V4 cart||Any valid group 2 ID<br>defined in Firestorm.<br>Pass -1 to to not<br>search by group 2|
|SuppressChildProducts|Y|Flag to either include or exclude child products from<br>the returned data.|Boolean|0 = Include child<br>products in the<br>returned data, -1 =<br>Do not return child<br>products in the<br>returned data.|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 121 | 317 

Firestorm® Web Services API | Version 2.2.33 

The returned data from this web service can be used to provide input for you to build your own shopping cart display. The returned information will contain everything you need to build a cart display. The engine behind this web service will provide current up to the date pricing, taking into account any sales that may be in progress, availability rules and all other configurable operational parameters that can be used in Firestorm®. 

##### <u>Grouping IDs</u> 

You may optionally pass in ShoppingCartMasterGroupID, Group1ID and Group2IDs in this call. The grouping IDs coorelate to the grouping that is used by the V4 shopping cart. You would use these IDs in the event that you want to see only those products assigned to a specific group. 

In other words, if someone wants to see all product assigned to a specific master group (like MENS CLOTHING), you would pass in the ShoppingCartMasterGroupID that coorelates to MENS CLOTHING (in this example, use the value 223). The web service would then use this to filter the output to only show those products currently assigned to the master group 223. 

Group 1 and Group 2 are simply two more levels of grouping. You may use ShoppingCartMasterGroupID in conjunction with Group1ID or optionally add in Group2ID as well. It is not a valid search to provide a group2ID but not a group1ID. You may use a master group by itself, optionally with a group 1, and if you use a group 1, then you can use a group 2. 

**WARNING:** _If you search with NO master group ID, a record for each ProductID/ ShoppingCartMasterGroupID combination will be returned. In other words, if a given product is assigned to 4 different master groups in the catalog, the output would contain 4 rows for that product (one for each master group). Of course the ShoppingCartMasterGroupID would be different for each one._ 

##### <u>Child Products</u> 

The Firestorm® system uses to concept of parent and child products to control the display of variations of a given product. As an example, if widget A comes in 10 different colors, there will be 10 child products, each with their own product number and pricing.  If a product is a child product, the system will set the field “IsChildProduct” to be a non-zero value. When this flag is set, you should refer to the field “ParentProductID” to determine which parent product the child product is tied to. In addition, the field “VariationPath” will return a pipe delimited (“|”) string containing the path used to select the product in the cart (i.e.: RED|SIZE 10|BUTTON DOWN COLLAR). Note that the total number of variations used in selecting the child product is determined by configurations in the system. The path is presented in the order of selection by the user. 

If you need to know all possible paths from a parent product to a given child product, use the web service FirestormInventoryWS.GetVariationPathsForParentProduct(). 

A parent product can be identified by the flag “IsParentProduct”. If this flag is a non-zero value, you must either build a variation display or suppress it from being displayed. 

You will need this information to build a variation display of your choosing. As a general rule, a parent product should never be offered for sale directly as it has no pricing associated with it. Only the related child products will have pricing and therefore are the only items eligible to be sold. You will need to build your display accordingly to maintain compliance with this rule. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 122 | 317 

Firestorm® Web Services API | Version 2.2.33 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 123 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **<u>Return Values</u>** 

|Returned Data|||
|---|---|---|
|Fild N|SQL Dtt|Ct|
|e ame|aaype|ommens|
|ProductID|Integer|The unique number assigned to thisproduct(for internal use)|
|GroupString|String|A string representing the groups that this product belongs to.<br>This is a concatenation of group numbers separated by a “.”<br>Character. For example: “60.72”. This would represent<br>GROUP1.GROUP2|
|Group1|string|Thegroup1 ID that thisproduct is assigned to.|
|Group2|string|Thegroup2 ID that thisproduct is assigned to|
|ProductNumber|String|Product number assigned in the “Product” form in the<br>Firestorm® admin interface.|
|WebName|String|The name of the product for display on the web. WARNING:<br>This field may contain HTML code and my contain UNICODE<br>characters.|
|WebDescription|String|The description of the product for display on the web.<br>WARNING: This field may contain HTML code and my contain<br>UNICODE characters.|
|PictureURL|String|The URL for the small picture of this product. This URL may or<br>may not be fully qualified. The system will allow relative URLs<br>to be entered. Check with the system administrator to<br>determine how they have been entered to determine if you<br>mayneed to make adjustments in the URL before use.|
|PageURL|String|If a product has a “more information” page associated with it,<br>this field will contain the URL to that page. May or may not be<br>fully qualified.|
|LargePictureURL|string|The URL for the large picture of this product. This URL may or<br>may not be fully qualified. The system will allow relative URLs<br>to be entered. Check with the system administrator to<br>determine how they have been entered to determine if you<br>mayneed to make adjustments in the URL before use.|
|RetailPrice|Double|Retail price AFTER any discounts, sales or adjustments have<br>been applied bythe system|
|WholesalePrice|Double|Wholesale price AFTER any discounts, sales or adjustments<br>have been applied bythe system|
|UplineAmount|Double|Commissionable value AFTER any discounts, sales or<br>adjustments have been applied bythe system.|
|PSVAmount|Double|Personal Sales Volume AFTER any discounts, sales or<br>adjustments have been applied by the system. Typically used<br>forqualificationpurposes in the compensationplan.|
|OriginalRetailPrice|Double|Retail price BEFORE any discounts, sales or adjustments have<br>been applied bythe system|
|OriginalWholesalePrice|Double|Wholesale price BEFORE any discounts, sales or adjustments<br>have been applied bythe system|
|OriginalUplineAmount|Double|Commissionable value BEFORE any discounts, sales or<br>adjustments have been applied bythe system.|
|OriginalPSVAmount|Double|Personal Sales Volume BEFORE any discounts, sales or<br>adjustments have been applied by the system. Typically used<br>forqualificationpurposes in the compensationplan.|
|PointValue|Double|If product points can be earned by purchasing this product,<br>this is the number of product points that will be awarded by<br>the system.|
|AllowPurchaseWithPoints|Boolean|Flag to indicate that this product is eligible to be purchased<br>withproductpoints.(-1 = Eligible,0 = not eligible)|
|PriceInPoints|Double|The cost of thisproduct inpoints.|
|AllowAsFreeProduct|Boolean|Flag to indicate if this product is eligible to be given as a free<br>product(0 = not eligible,-1 = eligible)|
|MaxWebQty|Integer|Maximum quantity of this item that can be purchased at one<br>time.(-1 = no limit)|
|OutOfStock|Boolean|Flag to indicate that this item is currently out of stock. (Should<br>be used with “AllowBackorder” to determine if you can allow<br>this item to be ordered)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 124 | 317 

Firestorm® Web Services API | Version 2.2.33 

|IsParentProduct|Boolean|Flag to indicate that this product is a parent product (see<br>description in “**Additional Information**” section above. (0 =<br>Not aparentproduct,-1 = Is aparentproduct)|
|---|---|---|
|ParentProductID|Integer|For child products only, this value is the productid of the<br>parent product that the child product is tied to. When this<br>value is present, the IsChildProduct field will be set to a non-<br>zero value, and the field VariationPath will contain the<br>product variations that were seleted in the cart to get to this<br>product forpurchase.|
|InventoryGroupID|Integer|If this product is assigned to an inventory group, this ID value<br>is the actual group to which it is assigned. See the Firestorm®<br>Use and Operations Manual for more information on<br>InventoryGroups.|
|AllowBackorder|Boolean|Flag to indicate if this product is allowed to be backordered. If<br>this flag is set to -1, no order should be taken for this product<br>(suppress the “add to cart” button and display a message<br>accordingly)|
|SaleComment|String|When an item is on sale, this field will contain the name of the<br>sale as entered in Firestorm®.(i.e.: “All items 10% off”)|
|RetailSaleComment|String|When an item is on sale, this field will contain a comment<br>indicating how much was saved off of the retail price. i.e:<br>“(You save 24.97)”|
|WholesaleSaleComment|String|When an item is on sale, this field will contain a comment<br>indicating how much was saved off of the wholesale price. i.e:<br>“(You save 24.97)”|
|CatalogueID|Integer|The catalogueID that this data is for.|
|ParentStartingRetailPrice|Double|When this product is a parent product, this field contains a<br>comment that will indicate the retail price of the lowest<br>priced child product. (i.e: “From 9.95”). Since actual price may<br>vary based on the selection made by the user, this comment is<br>intended to be displayed at a higher level in the cart, before<br>the user clicks into the product detail page to make an actual<br>selection.|
|ParentStartingWholesalePrice|Double|When this product is a parent product, this field contains a<br>comment that will indicate the wholesale price of the lowest<br>priced child product. (i.e: “From 6.95”). Since actual price may<br>vary based on the selection made by the user, this comment is<br>intended to be displayed at a higher level in the cart, before<br>the user clicks into the product detail page to make an actual<br>selection.|
|DropShippingCharges|Boolean|Flag to indicate that this product should not increase the<br>shippingcost.(Free shipping)|
|SearchText|String|A concatenation of Product Number, Web Name and Web<br>Description. Use this field to perform wildcard searches<br>against the dataset for a specific product. (i.e: %lotion%). This<br>field is intended for use by search functions included in your<br>cart.|
|IsChildProduct|Boolean|Flag to indicate that this product is a child product (a variation<br>of the relatedparentproduct)|
|VariationPath|String|a pipe delimited (“|”) string containing the path used to select<br>the product in the cart (i.e.: RED|SIZE 10|BUTTON DOWN<br>COLLAR). The path is presented in the order of selection by<br>the user.|
|Group1ID<br>G1|Integer<br>Sti|ShoppingCartGroupCodeID for the group 1 code assigned to<br>thisproduct<br>tblShiCtGCdCd f th G1 ID|
|roup<br>SuppressInShoppingCart|rng<br>Boolean|oppngarroupoe.oe or e roup.<br>Flag to indicate that this product should not be displayed in<br>the shoppingcart(0 = Displaynormally-1 = Do not display)|
|DealershipTypeID|Integer|, <br>Used in conjunction with the “IsEnrollmentSpecial” flag. If this<br>product is an enrollment special, then this is the type of<br>dealershipthat it should be offered for.|
|IsEnrollmentSpecial|Boolean|Flag to indicate that is product is intended to be used as an<br>enrollment special (i.e.: an upsell during the enrollment<br>process) (0 = Not an enrollment special, -1 = Is an enrollment<br>special)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 125 | 317 

Firestorm® Web Services API | Version 2.2.33 

|IsDynamicProduct|Boolean|Flag to indicate if this is a dynamic kit product (0 = Not a<br>dynamic kit,-1 = is a dynamic kit)|
|---|---|---|
|DynamicProductMaxQty|Integer|If this is a dynamic kit, this is the maximum quantity of this<br>product that maybe added to the kit|
|DynamicProductRequiredValue|Double|If this is a dynamic kit which requires a specified value, this is<br>the total value of theproducts that must be added to the kit.|
|DynamicProductValueType|String|When a dynamic product is a required value type, this is the<br>type of value. Valid values are “RETAIL”, “WHOLESALE”,<br>“UPLINE” or “PSV”. These values correlate directly to the<br>value fields in this dataset.|
|ProductName|String|The product name used internally. This value should not<br>contain anyHTML markup.|
|NumItems|Integer|When this is a dynamic kit based on a number of products,<br>this value indicates the total number of products that must be<br>added to the kit.|
|QtyOnHand|Integer|Total quantity of this product available for purchase at the<br>time this dataset waspulled.|
|EligibleForRecurringOrder|Boolean|Flag to indicate that this product is eligible to be put onto a<br>recurring order (Autoship). (0 = may not be placed on a<br>recurring order, -1 = may be placed on a recurring order).<br>WARNING: Use this value in conjunction with<br>“CatalogAllowsRecurringOrder”. If**BOTH**flags are not set<br>to “-1”, then you maynotset up a recurring order for this<br>item!|
|CatalogAllowsRecurringOrder|Boolean|Flag to indicate if the catalog can be used to set up a recurring<br>order. IF THIS FLAG IS SET TO 0, YOU MUST IGNORE THE<br>“EligibleForRecurringOrder” flag. ( 0 = Not eligible, -1 = Is<br>eligible.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 126 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS. GetVariationPathsForParentProduct 

Returns a recordset from Firestorm® describing all possible variations for a given parent product. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|ParentProductID|Y|The product ID of the PARENT product that you need<br>to see all configured variations for.|Integer|Any valid ProductID<br>defined in Firestorm<br>that is flagged as a<br>parentproduct|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

This method will pull all possible paths to specific child products that are defined in the system by the company. The results are hierarchical in nature and must be traversed properly in order to successfully build out a variation display in your shopping experience. 

To understand the output of this web service, it is important for you to understand the relationship beterrn parent and child products! See below for an explanation: 

Our example will be a shirt, available in 3 colors and in 3 different sizes. 

|**Parent Product**<br>**(ParentProductID**<br>**17853)**|**First Level Variation**<br>**(COLOR)**|**Second Level Variation**<br>**(SIZE)**|**Actual Product ID**|
|---|---|---|---|
|Shirt|Red|Small|17854|
|||Medium|17855|
|||Large|17856|
||Blue|Small|17857|
|||Medium|17858|
|||Large|17859|
||Green|Small|17860|
|||Medium|17861|
|||Large|17862|



As you can see in the chart above, the variations provide a “path” to get from a parent product to an actual product that can be be put into the shopping cart. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 127 | 317 

Firestorm® Web Services API | Version 2.2.33 

You will pass in the parent product ID you are looking at variation paths for, and the web service will return a result set that contains all possible paths to child product that are tied to the requested parent product. 

You can use this data to build out your own variation display. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|VariationID|Integer|The unique number assigned to this Variation|
|ParentVariationID|Integer|The VariationID of the parent variation that this variation is<br>assigned to.|
|VariationTypeCode|String|The text Code of this variation type(eg: COLOR,SIZE)|
|VariationTypeDescription|String|The text Description of this variation type (eg: Material Color,<br>Shirt Size)|
|VariationDescription|String|The text description of this variation (eg: Red, Green, Small<br>Large)|
|ActualProductID|Integer|The actual ProductID that represents the combined selected<br>variations. NOTE: The ProductID will only be present on the<br>last level of a variationpath.|
|VariationLevel|Integer|The level of the variationpath,beginningat 0.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 128 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.GetProductItemDetail 

Returns a record from Firestorm® describing the passed in Item Number. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|ItemNumber|Y|The Item Number of the Firestorm Product Item to<br>retrieve detail for|Integer|Any valid<br>ItemNumber defined<br>in Firestorm|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

This method will pull all active items defined in the system along with their current inventory counts and return them in a single dataset sorted by “ItemNumber”. 

This web service should be used _<u>sparingly</u>_ if your company has a large number of active items defined in the system. The call to this web service has the potential to return a very large result set, which could result in a load on the system in order to pull it and return it as an XML document. 

This web service is intended to only be called no more than 4 times per 24 hour period to update inventory counts on a remote system. While the system _<u>will</u>_ respond to more frequent calls, you could negatively impact the performance of your Firestorm® system by calling it too frequently. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|Timestamp|String|The timestamp that this set of results was returned to the<br>caller. All inventory counts are up to date with this<br>timestamp.|
|ProductItemID|Integer|The unique ID number assigned to the product item in<br>Firestorm®|
|ItemNumber|String|The assigned ItemNumber|
|Name|String|The Name of the Product Item|
|Description|String|The description of the Product Item|
|WeightLBS|Double|Thepoundsportion of the weight of 1 unit of the item|
|WeightOzs|Double|The ouncesportion of the weight of 1 unit of the item|
|QtyOnHand|Integer|Thequantityof the item that is on hand and available to sell.|
|QtyStaged|Integer|The quantity of the item that is on hand but has been marked<br>as sold.|
|QtyOnOrder|Integer|The quantity of the item that is currently on order from an<br>outside vendor.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 129 | 317 

Firestorm® Web Services API | Version 2.2.33 

|QtyOnBackOrder|Integer|The quantity of the item that has been sold, but placed on<br>backorder due to lack of available stock.|
|---|---|---|
|ReOrderLevel|Integer|The minimum quantity of non-sold on hand stock remaining<br>that will trigger a reorder,if this feature has been set up.|
|ReorderQty|Integer|The quantity of the item that will be re-ordered when<br>triggered,if this feature has been set up.|
|AllowBackorder|Integer|A flag indicating whether or not this item can be purchased if<br>it would cause the item to beplaced on backorder.|
|StorageBinNumber|String|The Storage Bin Number that this item is stored in, within the<br>warehouse.|
|HarmonizingCode|String|Displayed as General Code on the Items screen in Firestorm.|
|Active|Integer|A flag indicating whether or not this item is marked as Active<br>in Firestorm.|
|IsHazMat|Integer|A flag indicating whether or not this item is considered or<br>contains Hazardous Materials, and would cause the system to<br>applyanyconfigured Haz Mat charges.|
|UPCA|String|The UPC Code(numeric)of the item.|
|User1|String|Special field for use with thirdpartyfulfillment center exports.|
|User2|String|Special field for use with thirdpartyfulfillment center exports.|
|User3|String|Special field for use with thirdpartyfulfillment center exports.|
|User4|String|Special field for use with thirdpartyfulfillment center exports.|
|User5|String|Special field for use with thirdpartyfulfillment center exports.|
|FullfillmentCenterID|Integer|The ID of the fulfillment center assigned to this item.|
|HSCode|String|Displayed as Harmonized System Code on the Items screen in<br>Firestorm,in the Customs Specific Data section.|
|CountryOfOrigin|String|The Country of Origin on the Items screen in Firestorm, in the<br>Customs Specific Data section.|
|CustomsDescription|String|The Goods Description on the Items screen in Firestorm, in<br>the Customs Specific Data section.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 130 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.GetProductItems 

Returns a record from Firestorm® listing the Items that are assigned to a specific Product. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|ProductID|Y|The ID of the Product to retrieve an Item listing for|Integer|Any valid ProductID<br>defined in Firestorm|
|WithDetail|Y|A boolean flag indicating whether or not to return<br>the full detail on file for each item.|Boolean|True/False|
|SuppressInactive|Y|A boolean flag indicating whether or not to include<br>Items that have been flagged as Inactive in the<br>system. If this is set to True, all Items that are<br>assigned to a Product will be returned to the caller,<br>regardless of their current Active status.|Boolean|True/False|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

This method will pull all items that are current assigned to a specified Product in Firestorm. You must pass in a valid Firestorm Product ID in order to get back an Item listing. If you wish to see the full detail of the Item record, set WithDetail to True. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ProductItemID|Integer|The unique ID number assigned to the product item in<br>Firestorm®|
|ItemNumber|String|The assigned ItemNumber|
|Name|String|The Name of the Product Item|
|Description|String|The description of the Product Item|
|WeightLBS*|Double|Thepoundsportion of the weight of 1 unit of the item|
|WeightOzs*|Double|The ouncesportion of the weight of 1 unit of the item|
|QtyAssigned**|Integer|The quantity of this item assigned to a single instance of this<br>product.<br>NOTE: This value is only returned when a ProductID is<br>specified.<br>NOTE: This number must be multiplied by the quantity<br>ordered to determine the actual number required to fulfill a<br>given request.|
|QtyOnHand*|Integer|Thequantityof the item that is on hand and available to sell.|
|QtyStaged*|Integer|The quantity of the item that is on hand but has been marked<br>as sold.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 131 | 317 

Firestorm® Web Services API | Version 2.2.33 

|QtyOnOrder*|Integer|The quantity of the item that is currently on order from an<br>outside vendor.|
|---|---|---|
|QtyOnBackOrder*|Integer|The quantity of the item that has been sold, but placed on<br>backorder due to lack of available stock.|
|ReOrderLevel*|Integer|The minimum quantity of non-sold on hand stock remaining<br>that will trigger a reorder,if this feature has been set up.|
|ReorderQty*|Integer|The quantity of the item that will be re-ordered when<br>triggered,if this feature has been set up.|
|AllowBackorder*|Integer|A flag indicating whether or not this item can be purchased if<br>it would cause the item to beplaced on backorder.|
|StorageBinNumber*|String|The Storage Bin Number that this item is stored in, within the<br>warehouse.|
|HarmonizingCode*|String|Displayed as General Code on the Items screen in Firestorm.|
|Active*|Integer|A flag indicating whether or not this item is marked as Active<br>in Firestorm.|
|IsHazMat*|Integer|A flag indicating whether or not this item is considered or<br>contains Hazardous Materials, and would cause the system to<br>applyanyconfigured Haz Mat charges.|
|UPCA*|String|The UPC Code(numeric)of the item.|
|User1*|String|Special field for use with thirdpartyfulfillment center exports.|
|User2*|String|Special field for use with thirdpartyfulfillment center exports.|
|User3*|String|Special field for use with thirdpartyfulfillment center exports.|
|User4*|String|Special field for use with thirdpartyfulfillment center exports.|
|User5*|String|Special field for use with thirdpartyfulfillment center exports.|
|FullfillmentCenterID*|Integer|The ID of the fulfillment center assigned to this item.|



* - Only returned when WithDetail is set to True 

** - Only returned when ProductID is set to a valid product number 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 132 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.GetCurrentInventoryCounts 

Returns a dataset from Firestorm® containing all inventory counts for all ACTIVE items defined in database. 

|Method Definition<br>Argument|Required|Description|Datatype|Valid Values|
|---|---|---|---|---|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ProductItemID|Integer|The unique ID number assigned to theproduct item|
|ItemNumber|String|The assigned ItemNumber|
|Name|String|The Name of the Product Item|
|Description|String|The description of the Product Item|
|QtyOnHand|Integer|Thequantityof the item that is on hand and available to sell.|
|QtyStaged|Integer|The quantity of the item that is on hand but has been marked<br>as sold.|
|QtyOnOrder|Integer|The quantity of the item that is currently on order from an<br>outside vendor.|
|QtyOnBackOrder|Integer|The quantity of the item that has been sold, but placed on<br>backorder due to lack of available stock.|
|FullfillmentCenterID|Integer|The ID of the fulfillment center assigned to this item.<br>NOTE: A returned value of “-1” indicates that no fulfillment<br>center has been assigned to this item.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 133 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.GetInventoryCountsByProductID 

Returns a dataset from Firestorm® containing all inventory counts for all specified items defined in database. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|ProductIDListXML|Y|XML document containing a list of all productIDs<br>thatyou want current inventorylevels for|String|See xml document<br>specification below|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This web service can be used to obtain inventory levels for specific products in the system. In order to pass in the list of product IDs, you will need to construct an xml document to pass in using the following specifications. 

There is no limit to the number of product envelopes that may be passed in. 

##### <u>WARNING</u> 

If you pass in a ProductID or ProductNumber that is not valid, there will be no returned record for that product in the output of this web service. Only products that are located in the database, that have product items actually assigned to them will be returned in the output. If you do not get a record back for a given product, then it was invalid, or it has no product items assigned to it (this is a configuration error that must be corrected by the administrator) 

##### <u>XML Document Specification</u> 

##### NOTE: 

When passing in product information, you may provide ProductID OR ProductNumber.  You are not required to pass in both values. However, if you do pass in both, the system will attempt to use ProductID to retrieve the information requested and ignore ProductNumber. 

|Element|Required|Attribute Value|Datatype|Description|
|---|---|---|---|---|
|PRODUCTIDLIST|Y|itemcount<br>Number of<br>“PRODUCT”<br>envelopes to<br>follow||Containing envelope for list|
|<br>PRODUCT|Y|||Containingenvelope for a singleproduct|
|<br>PRODUCTID|C||Numeric|The numeric product ID as assigned by Firestorm. Product IDs<br>in a given catalog can be obtained by a call to<br>FirestormInventoryWS.GetCatalogueContents()|
|<br>PRODUCTNUMBER|C||String|Theproduct number as defined in Firestorm.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 134 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### <u>Example</u> 

<![CDATA[ <?xml version='1.0' encoding='utf-8'?> <PRODUCTIDLIST itemcount=’2’> <PRODUCT> 

<PRODUCTID>326874</PRODUCTID> <PRODUCTNUMBER></PRODUCTNUMBER> </PRODUCT> 

<PRODUCT> <PRODUCTID></PRODUCTID> <PRODUCTNUMBER>P-001</PRODUCTNUMBER> </PRODUCT> </PRODUCTIDLIST> ]]> 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ProductItemID|Integer|The unique ID number assigned to theproduct item|
|ItemNumber|String|The assigned ItemNumber|
|Name|String|The Name of the Product Item|
|Description|String|The description of the Product Item|
|QtyOnHand|Integer|Thequantityof the item that is on hand and available to sell.|
|QtyStaged|Integer|The quantity of the item that is on hand but has been marked<br>as sold.|
|QtyOnOrder|Integer|The quantity of the item that is currently on order from an<br>outside vendor.|
|QtyOnBackOrder|Integer|The quantity of the item that has been sold, but placed on<br>backorder due to lack of available stock.|
|FullfillmentCenterID|Integer|The ID of the fulfillment center assigned to this item.<br>NOTE: A returned value of “-1” indicates that no fulfillment<br>center has been assigned to this item.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 135 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.GetShoppingCartGroupCodeDetail 

Returns a record from Firestorm® describing the passed in shopping cart group code. Also capable of returning a complete list of all available group codes. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|ShoppingCartGroupCodeID|Y|The ID of the record beingretrieved|Integer|Anyvalid ID value|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

If you desire to utilize the product grouping mechanisms within the Firestorm® system, you will use this web service to retrieve the details for a specific group code from the database. Firestorm® utilizes a level based grouping mechanism that the system administrator can use to group products in the shopping cart into logical groupings to help a consumer find a product quickly and easily. 

Each product is assigned at least 2 group codes. A level 1 code and a level 2 code. Level 1 correlates to the “Category” button on the top of the shopping cart (i.e.: “Clothing”, “Shoes”, etc). The level 2 code correlates with the side menu navigation that is presented to the user when a group 1 button is clicked. These codes will further break down the main category into sub-categories. For example, if a group 1 of “Clothes” is selected, the corresponding group 2 codes might be: “Shirts”, “Pants”, “Socks” etc. 

In order to return a complete list of all defined group codes, simply pass in a value of -1 in the “ShoppingCartGroupCodeID” field. The system will return a complete list sorted by level and DisplayOrder. Each group should be displayed in the order defined by “DisplayOrder” as this is the display order dictated by the system administrator. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ShoppingCartGroupCodeID|Integer|The uniqu ID number assigned to the code|
|Code|String|Short code representing this group. This code is for internal<br>use onlyand should not be displayed.|
|Description|String|A description of the group. This is the value that should be<br>used to displayto the user.(i.e.: Button labels)|
|Level|Integer|The level ofgrouping. Levels start with level 1|
|ImageURL_On|String|The URL to the image to use as a button in the cart for this<br>group1 code when selected(ON).(Warning: This URL mayor|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 136 | 317 

Firestorm® Web Services API | Version 2.2.33 

|||may not be fully qualified! Check with the system<br>administrator to determine how the system is configured)|
|---|---|---|
|ImageURL_Off|String|The URL to the image to use as a button in the cart for this<br>group 1 code when not selected (OFF). (Warning: This URL<br>may or may not be fully qualified! Check with the system<br>administrator to determine how the system is configured)|
|DisplayOrder|Integer|The display order for this code within the same level. (i.e.: All<br>level 1 codes will have a display order that only applies to<br>other level 1 codes)|
|Level2BannerURL|String|When a level 2 code is selected, this is the URL to the image to<br>display as a banner in the shopping cart above the product<br>display.|
|SubLevel|Integer|NOT CURRENTLY USED|
|Level1LandingURL|String|When a user selects a group 1 code, the system will see if a<br>default group 2 code has been defined in the system. If it has<br>NOT, the system will display this URL within an I-FRAME inside<br>the shoppingcart.|
|Level2GeneralURL|String|NOT CURRENTLY USED|
|BackgroundColor|String|LEGACY – NO LONGER USED|
|ForegroundColor|String|LEGACY – NO LONGER USED|
|IsDefault|Boolean|Flag to indicate if this group code is the default for the level it<br>is on. Most commonly used to select a group 2 code to use<br>when a group 1 is selected by the user. If one is defined, the<br>system will pre-select it for the user and display the assigned<br>products.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 137 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.GetEnrollmentSpecialsByDealershipType 

Returns a dataset containing all defined enrollment specials for the designated dealership type. Typically enrollment specials are used as upsell products during an enrollment process. 

|Method Definition<br>|<br>||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|CatalogueID|Y|The ID of the enrollment catalog to use|Integer|Any valid catalog ID as defined in<br>Firestorm|
|DealershipTypeID|Y|The ID that corresponds to the rank that the<br>member is enrollingas.|Integer|tblDealershipType.DealershipTypeID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

During the enrollment process, the system allows a specific set of products to be defined as enrollment specials. The products can be offered during enrollment to upsell the enrollee to make additional purchases. Typically these products are offered at a reduced price that is only good at the time of enrollment. 

This web service will allow these productIDs  to be pulled from the catalog without having to pull the entire catalog. This product ID list can then be used to filter the catalog contents to retrieve any other information needed. 

This web service is used in conjunction with tblInventoryWS.GetCatalogueContents(). 

##### **<u>Return Values</u>** 

|Returned Data|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ProductID|Integer|The productID for the product. You may use this value to filter<br>the catalog contents to obtain other information about the<br>product.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 138 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.SaveProduct 

This method will allow a remote caller to create a new product in Firestorm, or update a product that already exists in Firestorm. When creating a new product, the system will also create a corresponding Product Item record and link it to the new Product record with a required quantity of 1. Additionally, you may also specify the starting QtyOnHand inventory value for the new Product Item. This method only supports basic product setup and configuration. Configuration options for Parent/Child Products (variations), Cart Pop Images, OG Tags, Shopping Cart Code Injection, Attributes, Product Add Ons, Categories, Questions, and Sequential Product settings are not supported at this time. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|ProductID|Y|The ID value of the Product to update. To create a<br>newproduct in Firestorm,use the ID value -1|Integer|Any valid ProductID<br>or -1|
|OptionsXML||Complex XML document describing the product|String|See description<br>below<br>_Hint: Don’t forget_<br>_CDATA tags!_|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### <u>Options XML</u> 

When calling this web service, you must pass in an extended set of options using this field. The options included in the XML document will be used to configure the Product in Firestorm 

NOTE: As new product configuration options are added to the system, this XML document will expand to include those new options. Please refer to the most current version of this document to obtain the most current sample xml for this field. 

The following is an example of the options XML document: 

```
‘//////////////////////////////////////////
‘ SAMPLE OPTIONS XML
‘//////////////////////////////////////////
<![CDATA[
<?xml version='1.0' encoding='utf-8' ?>
<OPTIONS>
<ProductNumber>P-APPLE</ProductNumber>
<InventoryGroupCode>Group 1</InventoryGroupCode>
<Name>Red Delicious Apple </Name>
<Description>A very red, very delicious apple.</Description>
<ShortDescription>Red Apple</ShortDescription>
<WebName>Red Apple</WebName>
<WebDescription> A very red, very delicious apple.</WebDescription>
<IsActive>TRUE</IsActive>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 139 | 317 

Firestorm® Web Services API | Version 2.2.33 

```
<IsBinaryProduct>TRUE</IsBinaryProduct>
<IsSequentialProduct>FALSE</IsSequentialProduct>
<IsParentProduct>FALSE</IsParentProduct>
<CartSortValue1>1</CartSortValue1>
<CartSortValue2>2</CartSortValue2>
<CartSortValue3>3</CartSortValue3>
<CartSortValue4>4</CartSortValue4>
<CartSortValue5>5</CartSortValue5>
<SmallImageURL>https://www.mycompany.com/small.jpg</SmallImageURL>
<LargeImageURL>https://www.mycompany.com/large.jpg</LargeImageURL>
<AdditionalInfoURL>https://www.mycompany.com/addlinfo.htm</AdditionalInfoURL>
<UseImageMagnification>TRUE</UseImageMagnification>
<MaginificationImageURL>https://www.mycompany.com/magnify.jpg</MaginificationImageURL>
<MagnifierWindowHeight>200</MagnifierWindowHeight>
<MagnifierWindowWidth>150</MagnifierWindowWidth>
<AccountingCode1>ACCT1</AccountingCode1>
<AccountingCode2>ACCT2</AccountingCode2>
<UseAddToShoppingCartHook>TRUE</UseAddToShoppingCartHook>
<AddToShoppingCartHookName>https://www.mycompany.com/MyHook.aspx</AddToShoppingCartHookName>
<AddToShoppingCartHookIsStoredProcedure>FALSE</AddToShoppingCartHookIsStoredProcedure>
<AddToShoppingCartHookIsWebPage>TRUE</AddToShoppingCartHookIsWebPage>
<AddToShoppingCartHookViewportHeight>200</AddToShoppingCartHookViewportHeight>
<AddToShoppingCartHookViewportWidth>150</AddToShoppingCartHookViewportWidth>
<IsTaxable>TRUE</IsTaxable>
<TaxableProductType>FOOD</TaxableProductType>
<TaxableGroupCode>TaxGroupCode</TaxableGroupCode>
<TaxableItemCode>TaxItemCode</TaxableItemCode>
<CountsTowardsFreeProductSchedule>TRUE</CountsTowardsFreeProductSchedule>
<CountsTowardsDiscountSchedule>TRUE</CountsTowardsDiscountSchedule>
<ReorderLevel>10</ReorderLevel>
<ReorderQty>100</ReorderQty>
<AllowBackorder>TRUE</AllowBackorder>
<HarmonizingCode>HMC</HarmonizingCode>
<StorageBinNumber>SBN</StorageBinNumber>
<WeightLBS>1</WeightLBS>
<WeightOZS>3</WeightOZS>
<QtyOnHand>500</QtyOnHand>
</OPTIONS>
]]>
```

This XML document is constructed by your system and is passed over to Firestorm® in the “OptionsXML” argument. The layout of the XML document and each possible option can vary based on whether you are creating a new product, or updating an existing product. The following table describes in detail the various elements of this document along with definitions and requirements for each section. Additionally, the record that the option will be applied to is indicated (either Product or Product Item) and whether or not the option is required to be passed. 

|**Element**|**DataType**|**Target Record**|**Required**|**Definition**|
|---|---|---|---|---|
|<![CDATA[|||Y|Required openingCDATA tag|
|<?xml ……|||Y|Required XML document header (see<br>example above)|
|OPTIONS|||Y|Containing envelope for the option<br>containers beingused.|
|<br>ProductNumber|String|Product|Y|The SKU of the Product|
|<br>InventoryGroupCode|String|Product|Y|The Code of the Inentory Group to assign<br>the product to. This will also control which<br>Binary Accumulators are credited with<br>volume for BinaryProducts.|
|<br>Name|String|Product|Y|The Name of the Product|
|<br>Description|String|Product|Y|The full description of theproduct.|
|<br>ShortDescription|String|Product|Y|A brief description of theproduct.|
|<br>WebName|String|Product|Y|The name of the product as it will be<br>displayed on the web.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 140 | 317 

Firestorm® Web Services API | Version 2.2.33 

|<br>WebDescription|String|Product|Y|The description of the product as it will be<br>dislaed on the web|
|---|---|---|---|---|
|<br>IsActive|Boolean|Product|Y|py.<br>A flag to indicate whether the product is<br>active or not. Allowed values: TRUE or<br>FALSE.|
|<br>IsBinaryProduct|Boolean|Product|Y|A flag to indicate whether the product is a<br>binary product or not. Products flagged as<br>binary will inject volume into the binary<br>structure. Allowed values: TRUE or FALSE.|
|<br>IsSequentialProduct|Boolean|Product|Y|A flag to indicate whether the product is a<br>sequential product or not. NOTE: While<br>you may flag a product as a sequential<br>product using this API, no other sequential<br>product configurations are supported.<br>These options may only be set in the admin<br>application. Allowed values: TRUE or FALSE.|
|<br>IsParentProduct|Boolean|Product|Y|A flag to indicate whether the product is a<br>parent product or not for product<br>variations. NOTE: While you may flag a<br>product as a parent product using this API,<br>no other product variation configurations<br>are supported. These options may only be<br>set in the admin application. Allowed<br>values: TRUE or FALSE.|
|<br>CartSortValue1|String|Product|N|<br>Custom Sorting Value 1 for use with the<br>custom sort feature in the cart.|
|<br>CartSortValue2|String|Product|N|Custom Sorting Value 2 for use with the<br>custom sort feature in the cart.|
|<br>CartSortValue3|String|Product|N|Custom Sorting Value 3 for use with the<br>custom sort feature in the cart.|
|<br>CartSortValue4|String|Product|N|Custom Sorting Value 4 for use with the<br>custom sort feature in the cart.|
|<br>CartSortValue5|String|Product|N|Custom Sorting Value 5 for use with the<br>custom sort feature in the cart.|
|<br>SmallImageURL|String|Product|N|The fully qualified URL for the image to be<br>used as the “Small Image” in the shopping<br>cart.|
|<br>LargeImageURL|String|Product|N|The fully qualified URL for the image to be<br>used as the “Large Image” in the shopping<br>cart.|
|<br>AdditionalInfoURL|String|Product|N|The fully qualified URL to a page or<br>resource for additional information for the<br>product. This will be made available as a<br>link on theproduct detailpage.|
|<br>UseImageMagnification|Boolean|Product|N|A flag to indicate whether product image<br>magnification should be used. Allowed<br>values: TRUE or FALSE.|
|<br>MaginificationImageURL|String|Product|N*|The fully qualified URL for the image to be<br>used as the “Magnification Image” in the<br>shopping cart.<br>*Field is required if UseImageMagnification<br>is TRUE|
|<br>MagnifierWindowHeight|Integer|Product|N*|The height in pixels of the image magnifier.<br>*Field is required if UseImageMagnification<br>is TRUE|
|<br>MagnifierWindowWidth|Integer|Product|N*|<br>The width in pixels of the image magnifier.<br>*Field is required if UseImageMagnification<br>is TRUE|
|<br>AccountingCode1|String|Product|N|A user provided accounting code for the<br>product. Maybe left blank.|
|<br>AccountingCode2|String|Product|N|A second user provided accounting code<br>for theproduct. Maybe left blank.|
|<br>UseAddToShoppingCartHook|Boolean|Product|N|A flag to indicate whether a hook should be<br>called when aproduct is added to a|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 141 | 317 

Firestorm® Web Services API | Version 2.2.33 

|||||shopper’s cart. Allowed values: TRUE or<br>FALSE|
|---|---|---|---|---|
|<br>AddToShoppingCartHookName|String|Product|N*|.<br>The name of the add to shopping cart<br>hook. Can either be a stored procedure<br>name, or a path to a special web page. If<br>using the web page option, the path to the<br>page must be relative to the Firestorm<br>Shopping cart (eg:<br>“../../hooks/myhook.aspx”)<br>*Field is required if<br>UseAddToShoppingCartHook is TRUE|
|<br>AddToShoppingCartHookIsStoredProcedure|Boolean|Product|N*|A flag to indicate whether the add to cart<br>hook is a SQL stored procedure or not.<br>Allowed values: TRUE or FALSE.<br>*Field is required if<br>UseAddToShoppingCartHook is TRUE|
|<br>AddToShoppingCartHookIsWebPage|Boolean|Product|N*|A flag to indicate whether the add to cart<br>hook is a web page or not. Allowed values:<br>TRUE or FALSE.<br>*Field is required if<br>UseAddToShoppingCartHook is TRUE|
|<br>AddToShoppingCartHookViewportHeight|Integer|Product|N*|The height in pixels of the add to shopping<br>cart hook web page viewport height.<br>*Field is required if<br>UseAddToShoppingCartHook is TRUE and<br>AddToShoppingCartHookIsWebPage is<br>TRUE.|
|<br>AddToShoppingCartHookViewportWidth|Integer|Product|N*|<br>The width in pixels of the add to shopping<br>cart hook web page viewport height.<br>*Field is required if<br>UseAddToShoppingCartHook is TRUE and<br>AddToShoppingCartHookIsWebPage is<br>TRUE.|
|<br>IsTaxable|Boolean|Product|Y|<br>A flag to indicate whether the product is<br>taxable or not. Allowed values: TRUE or<br>FALSE.|
|<br>TaxableProductType|String|Product|Y|Value indicating what type of product this<br>product is for taxation purposes. Allowed<br>Values: FOOD and NON-FOOD.|
|<br>TaxableGroupCode|String|Product|Y|A group code that is used for taxation<br>services such as AVALARA.|
|<br>TaxableItemCode|String|Product|Y|An item code that is used for taxation<br>services such as AVALARA.|
|<br>CountsTowardsFreeProductSchedule|Boolean|Product|N|A flag to indicate whether the value of the<br>product counts towards any defined free<br>product schedules. Allowed values: TRUE<br>or FALSE.|
|<br>CountsTowardsDiscountSchedule|Boolean|Product|N|A flag to indicate whether the value of the<br>product counts towards any defined<br>discount schedules. Allowed values: TRUE<br>or FALSE.|
|<br>ReorderLevel|Integer|Product Item|N*|The QtyOnHand value at which point a<br>reorder of this product should be placed to<br>replenish inventory.<br>*Field is required if creatinga newproduct.|
|<br>ReorderQty|Integer|Product Item|N*|The qty of this product to reorder when<br>ReorderLevel is reached.<br>*Field is required if creatinga newproduct.|
|<br>AllowBackorder|Boolean|Product Item|N*|<br>A flag to indicate whether or not<br>backorders of this product are allowed.<br>Allowed values: TRUE or FALSE.<br>*Field is required if creatinga newproduct.|
|<br>HarmonizingCode|String|Product Item|N*|The Harmonizing Code of the product.<br>*Field is required if creatinga newproduct|
|<br>StorageBinNumber|String|Product Item|N*|.<br>The Storage Bin Number of theproduct.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 142 | 317 

Firestorm® Web Services API | Version 2.2.33 

|||||*Field is required if creatinga newproduct.|
|---|---|---|---|---|
|<br>WeightLBS|Integer|Product Item|N*|The whole pounds portion of the weight of<br>the product.<br>*Field is required if creatinga newproduct.|
|<br>WeightOZS|Integer|Product Item|N*|The remaining ounces portion of the<br>weight of the product.<br>*Field is required if creatinga newproduct.|
|<br>QtyOnHand|Integer|Product Item|N*|The initial qty available for ordering of the<br>new product.<br>*Field is required if creatinga newproduct.|
|]]>|||Y|Required closingof CDATA tag|



##### **<u>Additional Information</u>** 

When updating an existing product in Firestorm, the linked Product Item record **cannot** be updated using the fields in the OptionsXML. Any field passed in the OptionsXML that is tagged as record type “Product Item” will be ignored if a Product ID is also passed into this method. If you are attempting to update the inventory levels of a product, please use the FirestormInventoryWS.AdjustInventory() method instead. 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

##### Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ID>integer</ID>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|Integer||The Product ID of the Product that was created or updated in Firestorm|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 143 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.SaveCatalogueProductDetail 

This method will allow a remote caller to add or update a catalogue specifc product configuration, including pricing and basic shoping cart options. Confiiguration options for commissions, dynamic product options, shopping cart grouping, related products, restricted shippers and payment methods, and VAT are not supported by this method at this time. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|CatalogueID|Y|The ID of the catalogue to apply the configuration to|Integer|Any valid<br>CatalogueID|
|ProductID|Y|The ID value of the Product to update. To create a<br>newproduct in Firestorm,use the ID value -1|Integer|Any valid ProductID|
|OptionsXML||Complex XML document describing the catalogue<br>product configuration|String|See description<br>below<br>_Hint: Don’t forget_<br>_CDATA tags!_|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### <u>Options XML</u> 

When calling this web service, you must pass in an extended set of options using this field. The options included in the XML document will be used to configure the Catalogue Product record in Firestorm 

NOTE: As new product configuration options are added to the system, this XML document will expand to include those new options. Please refer to the most current version of this document to obtain the most current sample xml for this field. 

The following is an example of the options XML document: 

```
‘//////////////////////////////////////////
‘ SAMPLE OPTIONS XML
‘//////////////////////////////////////////
<![CDATA[
```

```
<?xml version='1.0' encoding='utf-8' ?>
<OPTIONS>
<PSVAmount>10.00</PSVAmount>
<RetailPrice>9.99</RetailPrice>
<WholesalePrice>6.99</WholesalePrice>
<UplineAmount>7.00</UplineAmount>
<CountsAsXUnits>0</CountsAsXUnits>
<CustomAction>spCustomAction</CustomAction>
<PointValue>100</PointValue>
<DealershipTypeCode></DealershipTypeCode>
<CustomerTypeCode></CustomerTypeCode>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 144 | 317 

Firestorm® Web Services API | Version 2.2.33 

```
<EligibleForRecurringOrder>TRUE</EligibleForRecurringOrder>
```

```
<AllowPurchaseWithPoints>TRUE</AllowPurchaseWithPoints>
<PriceInPoints>5000</PriceInPoints>
<AllowAsFreeProduct>TRUE</AllowAsFreeProduct>
<MaxWebQty>-1</MaxWebQty>
<FreeShipping>FALSE</FreeShipping>
<DropCountryFee>FALSE</DropCountryFee>
<StartDate>10/12/2022</StartDate>
<EndDate>10/31/2022</EndDate>
<CustomActionArgument> </CustomActionArgument>
<IsEnrollmentSpecial>FALSE</IsEnrollmentSpecial>
<SuppressInShoppingCart>FALSE</SuppressInShoppingCart>
<Use4Digits>FALSE</Use4Digits>
<FlatShippingRate>9.99</FlatShippingRate>
<WebTag>myWT</WebTag>
<MaximumPointsRedeemable>-1</MaximumPointsRedeemable>
</OPTIONS>
]]>
```

This XML document is constructed by your system and is passed over to Firestorm® in the “OptionsXML” argument. The following table describes in detail the various elements of this document along with definitions and requirements for each section. Additionally, whether or not the option is required to be passed in the document is indicated in the Required column. 

|**Element**||**DataType**|**Required**|**Definition**|
|---|---|---|---|---|
|<![CDATA|[||Y|Required openingCDATA tag|
|<?xml ……|||Y|Required XML document header(see example above)|
|OPTIONS|||Y|Containingenvelope for the option containers beingused.|
||PSVAmount|Double|Y|The amount PSV the product will award when purchased<br>or sold. This value should be passed in the base system<br>currency.|
||RetailPrice|Double|Y|The Retail Price of the product. This value should be<br>passed in the base system currency.|
||WholesalePrice|Double|Y|The Wholesale Price of the product. This value should be<br>passed in the base system currency.|
||UplineAmount|Double|Y|The amount Upline (Commissionable) Volume the product<br>will award when purchased or sold. This value should be<br>passed in the base system currency.|
||CountsAsXUnits|Double|Y|The number of “units” the sale or purchase of this product<br>will count for. If you are not using this feature, you must<br>pass zero(0)for this value.|
||CustomAction|String|Y|The name of a SQL stored procedure to execute when the<br>product is purchased. If this feature is not used for this<br>product, you must pass an empty string for this value.<br>NOTE: Before use of this feature, please contact Firestorm<br>support to discuss allpre-requisites that must be inplace.|
||PointValue|Double|Y|The amont of Product Points to award to the purchaser for<br>thepurchasingtheproduct.|
||DealershipTypeCode|String|N|The Dealership Rank Code to restrict the purchase of this<br>product to.<br>NOTE: This field is only supported in enrollment<br>catalogues.|
||CustomerTypeCode|String|N|The Customer Type Code to restrict the purchase of this<br>product to.<br>NOTE: This field is only supported in enrollment<br>catalogues.|
||EligibleForRecurringOrder|Boolean|N|A flag indicating whether or not this product can be<br>purchased via a recurring oder. Allowed values: TRUE or<br>FALSE.|
||AllowPurchaseWithPoints|Boolean|N|A flag indicating whether or not this product can be<br>purchased with Product Points. Allowed values: TRUE or<br>FALSE.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 145 | 317 

Firestorm® Web Services API | Version 2.2.33 

||PriceInPoints|Double|Y<br>Theprice of theproduct in Product Points.|
|---|---|---|---|
||AllowAsFreeProduct|Boolean|N<br>A flag indicating whether or not this product can be<br>purchased at zero cost through coupons, awards, or other<br>means. Allowed values: TRUE or FALSE.|
||MaxWebQty|Integer|N<br>The maximum number of this product that can be ordered<br>on the web in a single order.|
||FreeShipping|Boolean|N<br>A flag indicating whether or not this product will have free<br>shippingapplied to it. Allowed values: TRUE or FALSE.|
||DropCountryFee|Boolean|N<br>A flag indicating whether or not country specific fees<br>should be charged for this product. Allowed values: TRUE<br>or FALSE.|
||StartDate|Datetime|N<br>The date and time that this product initially becomes<br>available for ordering.|
||EndDate|Datetime|N<br>The last date and time that thisproduct maybe ordered.|
||CustomActionArgument|String|N<br>A special argument string to pass into the defined<br>CustomAction. Please contact Firestorm support for<br>product specific instructions before usingthis field.|
||IsEnrollmentSpecial|Boolean|N<br>A flag indicating whether or not this product should be<br>offered as an enrollment special during the enrollment<br>process. Allowed values: TRUE or FALSE.<br>NOTE: This field is only supported in enrollment<br>catalogues.|
||SuppressInShoppingCart|Boolean|N<br>A flag indicating whether or not product should be hidden<br>in the shoppingcart. Allowed values: TRUE or FALSE.|
||Use4Digits|Boolean|N<br>A flag indicating whether or not the product price points<br>(PSV, UPLINE, RETAIL, WHOLESALE) should be carried to 4<br>decimal places. Consult with Firestorm support to discuss<br>the ramifications of this setting before using it. Allowed<br>values: TRUE or FALSE.|
||FlatShippingRate|Double|N<br>An override flat rate shipping dollar amount that will be<br>used when shipping is calculated on the order. For any<br>product defined with a flat shipping rate, that value will be<br>added to the remaining calculated shipping cost of the<br>order.|
||WebTag|String|N<br>A custom tag that can be applied to the mark up of the<br>product information. Consult with Firestorm support for<br>specific use cases.|
||MaximumPointsRedeemable|Double|N<br>The maximum number of Product Points which can be<br>redeemed toward the product. This setting is only<br>honored when the Firestorm system is configured to allow<br>partial points redemption towards products. Please<br>consult with Firestorm support before usingthis setting.|
|]]>|||Y<br>Required closingof CDATA tag|



##### **<u>Additional Information</u>** 

When updating an existing product in Firestorm, the linked Product Item record **cannot** be updated using the fields in the OptionsXML. Any field passed in the OptionsXML that is tagged as record type “Product Item” will be ignored if a Product ID is also passed into this method. If you are attempting to update the inventory levels of a product, please use the FirestormInventoryWS.AdjustInventory() method instead. 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

Return XML: 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 146 | 317 

Firestorm® Web Services API | Version 2.2.33 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 147 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.GetProductList 

Returns a datatable containing all defined products in the system. Can optionally return additional information for products and suppress products that are flagged as inactive to reduce payload size. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|WithDetail|Y|Option to return additional product detail<br>information|Boolean|True or False|
|SuppressInactive|Y|Option to exclude inactive products from the result<br>set|Boolean|True or False|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Return Values</u>** 

|Returned Data - Default<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ProductID|Integer|The unique ID for theproduct.|
|ProductNumber|String|The Product Number(SKU)of theproduct.|
|Name|String|The name of theproduct.|
|Active|Integer|A Boolean value indicating if the product is active in the<br>system. 0 = False, Non-Zero = True.<br>NOTE: This field will not be returned to you if<br>SuppressInactive = TRUE.|
|DisplayFontName|String|The name of the display font for the product. NOTE: this field<br>is rarelyused.|
|WebName|string|The web displayname of theproduct.|



|Returned Data – WithDetail = True<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ProductID|Integer|The unique ID for theproduct.|
|ProductNumber|String|The Product Number(SKU)of theproduct.|
|Name|String|The name of theproduct.|
|Description|String|The description of theproduct.|
|Taxable|Integer|A Boolean value indicating if the product is taxable. 0 = False,<br>Non-Zero = True.|
|CreateDate|Datetime|The datetime theproduct was created in the system.|
|CreateBy|String|The login ID of the user who created theproduct.|
|MaintDate|Datetime|The datetime theproduct’s configuration was last updated.|
|MaintBy|String|The login ID of the user who last updated the product<br>configuration.|
|Active|Integer|A Boolean value indicating if the product is active in the<br>system. 0 = False, Non-Zero = True.<br>NOTE: This field will not be returned to you if<br>SuppressInactive = TRUE.|
|PictureURL|String|The configured URL of theproductpicture.|
|WebDescription|String|The web description of theproduct.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 148 | 317 

Firestorm® Web Services API | Version 2.2.33 

|PageURL|String|The configured URL of the additional infopage.|
|---|---|---|
|DisplayFontName|String|The name of the display font for the product. NOTE: this field<br>is rarelyused.|
|WebName|String|The web displayname of theproduct.|
|IsBinaryProduct|Integer|A Boolean value indicating if the product is a binary product. 0<br>= False,Non-Zero = True.|
|IsSequentialProduct|Integer|A Boolean value indicating if the product is a sequential<br>product. 0 = False,Non-Zero = True.|
|InventoryGroupID|Integer|The ID of the InventoryGroupthisproduct is assigned to.|
|IsParentProduct|Integer|A Boolean value indicating if the product is a parent product<br>forproduct variations. 0 = False,Non-Zero = True.|
|CountsTowardsFreeThreshold|Integer|A Boolean value indicating if the product counts toward<br>configured free product thresholds. 0 = False, Non-Zero =<br>True.|
|CountsTowardsDiscountThreshold|Integer|A Boolean value indicating if the product is counts towards<br>configured discount thresholds. 0 = False,Non-Zero = True.|
|LargePictureURL|String|The configured URL of the Large Product Picture image.|
|ProductTypeID|Integer|The ID of the Taxable Product Type this product has been<br>assigned.|
|SalesTaxProductGroup|String|The configured Sales Tax Group code value (for use with<br>Avalara)|
|SalesTaxProductItem|String|The configured Sales Tax Item code value (for use with<br>Avalara)|
|UserCode1|String|A custom defined AccountingCode value|
|UserCode2|String|A secondarycustom defined AccountingCode value|
|SequentialProductLoop|Integer|A Boolean value indicating if the sequential product loop<br>should be restarted once the initial sequence has been<br>completed. 0 = False,Non-Zero = True.|
|UseAddtoCartHook|Integer|A Boolean value indicating if the product should call a special<br>hook when the product is added to a shopper’s cart. 0 = False,<br>Non-Zero = True.|
|AddToCartHook|String|The name of the Add to Cart Hook that will be called when<br>the product is added to a shopper’s cart, if UseAddtoCartHook<br>is TRUE|
|HookIsStoredProc|Integer|A Boolean value indicating if the Add to Cart Hook is a SQL<br>Stored Procedure. 0 = False,Non-Zero = True.|
|HookIsWebPage|Integer|A Boolean value indicating if the Add to Cart Hook is a web<br>page. 0 = False,Non-Zero = True.|
|ViewportHeight|Integer|The height in pixels of the viewport for web page based Add<br>to Cart hooks.|
|ViewportWidth|Integer|The width in pixels of the viewport for web page based Add to<br>Cart hooks.|
|UseImageMagnification|Integer|A Boolean value indicating if the product picture should use<br>image maginification. 0 = False,Non-Zero = True.|
|MagnifyImageURL|String|The defined URL to the image that should be used for image<br>maginifcation.|
|ImageMagHeight|Integer|The height inpixels of the magnifyimage|
|ImageMagWidth|Integer|.<br>The width inpixels of the magnifyimage.|
|CartSortValue1|String|<br>The defined Custom Cart SortingValue 1.|
|CartSortValue2|String|The defined Custom Cart SortingValue 2.|
|CartSortValue3|String|The defined Custom Cart SortingValue 3.|
|CartSortValue4|String|The defined Custom Cart SortingValue 4.|
|CartSortValue5|String|The defined Custom Cart SortingValue 5.|
|ShortDescription|String|A shorter description of theproduct.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 149 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.GetInventoryGroupCodes 

Returns a datatable containing all defined Inventory Group Codes in the system. Can optionally suppress Inventory Group Codes that are flagged as inactive to reduce payload size. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|SuppressInactive|Y|Option to exclude inactive inventory group codes<br>from the result set|Boolean|True or False|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Return Values</u>** 

|Returned Data - Default<br>Field Name|SQL Datatype|Comments|
|---|---|---|
|InventoryGroupCodeID|Integer|The unique ID for the inventory groupcode.|
|Code|String|The displayed code for the inventory groupcode.|
|Description|String|The description of the inventory groupcode.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 150 | 317 

Firestorm® Web Services API | Version 2.2.33 

### FirestormOrderWS 

|General Information||
|---|---|
|Name|FirestormOrderWS.asmx|
|WSDL|https://www.firestormwebservices.com/FirestormWebServices/FirestormOrderWS.asmx|
|Description|Provides access into specific areas of the Firestorm® orderingsubsystem.|



|Method Summary<br>||
|---|---|
|Method Name|Return Type|
|SaveOrder|Complex XML Document|
|SaveOrderExtended|Complex XML Document|
|ValidatePurchase|Boolean|
|GetOrders|Datatable|
|PostTrackingNumber|Boolean|
|PostMultipleTrackingNumbers|Complex XML Document|
|PayForOrderWithCommissions|Complex XML Document|
|GetFirestormTaxRate|DataTable|
|VoidOrder|Complex XML Document|
|VoidOrderDetail|Complex XML Document|
|GetShipperListWithRates|Complex XML Document|
|GetShipperList|Complex XML Document|
|FulfillOrder|Complex XML Document|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 151 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.SaveOrder 

Allows an external shopping cart to transmit an order into the Firestorm® system for processing. Typically used by 3<sup>rd</sup> party shopping carts that a company might want to use in lieu of the shopping cart included with the Firestorm® system. 

**PCI/DSS WARNING:** This web service uses sensitive personal and payment information to process an order. It is YOUR responsibility to ensure that you are following all proper PCI/DSS procedures in addition to accessing the web service over a secure (https) link in your production environment!! 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|C|DealerID of an existing dealer in the system. This<br>value must be supplied is CustomerDealerID is not.|Integer|-1 or any existing<br>DealerID in Firestorm<br>that is not flagged as<br>a customer.|
|ShippingCode|Y|The code defined by Firestorm® to identify the<br>shipping method to use for this order|String|Any valid shipper<br>code defined in<br>Firestorm®|
|ShipAddress1|Y|ShippingAddress Line 1|String||
|ShipAddress2|Y|Shipping Address Line 2|String|May be an empty<br>string|
|ShipCity|Y|ShippingCity|String||
|ShipState|Y|Shipping State|String|Any valid state code<br>defined in Firestorm®|
|ShipZip|Y|Shipping postal code|String||
|ShipCountry|Y|Shipping Country|String|Any valid country<br>code defined in<br>Firestorm®|
|Phone|Y|Phone number|String||
|OrderTotalAmount|Y|Total dollar amount of the products on the order.<br>(do not include any other fees) This value is used to<br>validate the calculated amount contained in the<br>order detail XML.<br>OVERRIDE: When you pass -99 in this field, the<br>system will calculate the total amount of the order<br>from the order detail XML passed in and will NOT<br>compare it to this number.||-99 or actual dollar<br>amount|
|SpecialInstructions|Y|Any special instructions for this order. Typically<br>collected from the purchaser. This value will appear<br>on the shippingorder(or shippingexport).|String||
|CatalogueID|Y|The Firestorm® catalog ID from Firestorm®|Integer|Any valid catalog ID<br>defined in Firestorm®|
|BillFirstName|C|BillingFirst Name|String||
|BillLastName|C|BillingLast Name|String||
|BillCompanyName|C|Billing Company Name (must be provided if first and<br>last name are blank)|String||
|BillAddress1|Y|BillingAddress Line 1|String||
|BillAddress2|Y|Billing Address Line 2|String|May be an empty<br>string|
|BillCity|Y|BillingCity|String||
|BillState|Y|BillingState|String||
|BillZip|Y|Billing postal code|String||



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 152 | 317 

Firestorm® Web Services API | Version 2.2.33 

|BillCountry|Y|Billing Country|String|Any valid country<br>code defined in<br>Firestorm®|
|---|---|---|---|---|
|CustomerDealerID|C|DealerID of an existing customer. Must be supplied if<br>DealerID is not supplied.|Integer|-1 or Any existing<br>DealerID that is<br>flagged as a<br>customer record|
|TotalOrderDiscount|Y|Total dollar value of the discount applied to this<br>order|Double|Must be >= 0|
|ShipTo|Y|First and Last Name of the purchaser. This value (if<br>passed in) will be used as part of the shipping<br>address in the system. If the values is passed as an<br>empty string, the BillFirstName and BillLastName will<br>be used in the shippingaddress,|String||
|TotalOrderDiscountPercentage|Y|The total discount applied as a percentage of the<br>total order.|Double|Must be a value<br>between 0 and 1|
|AutoshipOrder|Y|Flag to indicate if this order should count as an<br>autoship (recurring order) (generally for qualification<br>purposes).<br>When this flag is set to TRUE (non-zero) the system<br>will populate the value of 88888888 into the<br>RecurringParentOrderID field on the order header.|Boolean|0 = False<br>-1 = True|
|OrderDetail|Y|Complex XML document describing the contents of<br>the order(see details below)|String|See description<br>below|
|AddlPaymentInfo|Y|Any additional payment information you wish to be<br>stored with this order. This data is NOT used by<br>Firestorm® and is stored for historical purposes only.<br>NOTE: This value is only saved when the order<br>successfully processes in the system.|String||
|PaymentTypeCode|Y|Code representing the type of payment to use to pay<br>for this order.<br>**Note: E-Check payment types are not currently**<br>**supported by this web service.**|String|Any valid payment<br>type code defined in<br>Firestorm®|
|CardAccountNumber|C*|Credit card account number|String||
|CVV2Code|C*|Securitycode from the back of the credit card|String||
|CardHolderName|C*|Name as it appears on the credit card|String||
|CardExpirationMonth|C*|Expiration date month expressed as a 2 digit<br>number,zero filled.|String|Must be between 01<br>and 12|
|CardExpirationYear|C*|Expirationyear expressed as a 4 digit number|String|Anyvalidyear|
|Email|Y|Email address where order receipt will be sent|String|A valid email address|



* **Note: If the payment type code flagged as a credit card in Firestorm, these conditional fields are required.** 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

##### <u>Required Fields You Do Not Have A Value For</u> 

As there are no “optional” arguments in this web service, If a field calls for a string datatype and you do not wish to pass a value or do not need to (i.e.: credit card fields), simply pass an empty (“”) string in place of that argument. If you pass an empty string in an argument where the requirement is not optional, an error will be 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 153 | 317 

Firestorm® Web Services API | Version 2.2.33 

generated and sent back to you. 

##### <u>Normal Processing Still Occurs</u> 

When an order is passed to this web service, it will be treated exactly like a regular shopping cart order. All autoresponder emails (such as an order receipt) will be sent out per normal system operations. Any other special actions that can be triggered by a shopping cart order will still be triggered normally. It is not possible to suppress this behavior. Be aware of this when transmitting orders in this manner. 

##### <u>Payment</u> 

When an order is submitted to Firestorm® via this web service, the system WILL charge the payment method if the value of the order is greater than $0. Therefore, if your external system is processing the payment PRIOR to submitting the order to Firestorm®, you must specify a non-credit card payment type such as “CASH”. You may set up a custom payment type expressly for this purpose as long as it is not flagged as a credit card type. (See the Firestorm® Use and Operations Manual for details on how to accomplish this) 

If the order amount is greater than $0, and you specified a payment type that is flagged as a credit card in Firestorm®, the credit card engine in the system will process the request normally per the current system configurations. Please note that the credit card will be validated before being submitted. The system will perform basic validation such as mod10, expiration date check and will ensure all required data items are present. Per PCI guidelines, the CVV2 code will not be stored in the system and will only be used to process the current request. 

##### <u>Currency Conversion</u> 

When an order is being processed by the system for this enrollment, the system will look up the country specified in “BillingCountry” to see if a default currency has been defined for that country. If it has, the currency type and the defined conversion ratio for that currency will be saved as part of the order. Normal Firestorm® currency processing will still occur based on system setup and configurations. 

##### <u>Member Orders</u> 

When the incoming order is for a member in the system, their DealerID must be supplied. In this scenario, CustomerDealerID should be passed as -1. The DealerID passed in MUST already exist in the system, 

##### <u>Customer Orders</u> 

When the incoming order is for a customer (non-member), the DealerID field should be set to -1 and the CustomerDealerID should be set to the customer’s DealerID. The customer’s DealerID must already exist in the system. 

Note that when a customer order is sent through this web service, the system will look up the original referring dealer for this customer and will credit this order to that member for commission and qualification purposes. 

##### <u>Order Detail XML</u> 

When calling this web service, this field allows you to build the order on your system, then pass it over to Firestorm® as an XML document as shown below.  You will build an <ORDERDETAIL> element for each line item in your order, then embed them all in a containing <ORDER> element. This payload is not limited to the number of items that may be specified for a single order, allowing you to specify the order contents and pricing in any way necessary to meet your need. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 154 | 317 

Firestorm® Web Services API | Version 2.2.33 

When building this document, remember that even though you can override pricing for a given product, that product MUST exist in the catalog specified in your call. If a product is missing, the call will fail. 

The <ORDER> element must contain at least 1 <ORDERDETAIL> element. 

If you have passed over a valid value in the “OrderTotalAmount” field, the system will calculate the total price of the products on the order based on this XML document and will then compare the calculated value to the amount you passed over. The amounts must match exactly or the order will be rejected. This facility is intended to be a final “sanity” check to ensure that the XML document contains everything it is supposed to. You may disable this check by passing “-99” in the “OrderTotalAmount” field. 

**_Hint:_** _The passed XML document must be completely valid so that it may be parsed correctly by Firestorm®. Please test your XML document thoroughly to ensure that it can be loaded without error by an XML parser. This will avoid problems with your successful use of this web service._ 

**Uppercase and lowercase matter in XML** . Opening and closing tags must match exactly. For example, `<ROOT>` , `<Root>` , and `<root>` are three different tags 

The following is a sample of the XML document required: 

```
' ///////////////////////////
' Sample order detail XML
' ///////////////////////////
<![CDATA[
<?xml version='1.0' encoding='utf-8'?>
<ORDER itemcount='1'>
   <ORDERDETAIL>
       <PRODUCTNUMBER>string</PRODUCTNUMBER>
       <PRODUCTQTY>integer</PRODUCTQTY>
       <PRICEEACH>double</PRICEEACH>
       <RETAILPRICEEACH></RETAILPRICEEACH>
       <WHOLESALEPRICEEACH></WHOLESALEPRICEEACH>
       <UPLINEVOLUMEEACH></UPLINEVOLUMEEACH>
       <PSVAMOUNTEACH></PSVAMOUNTEACH>
       <ISFREEPRODUCT>boolean</ISFREEPRODUCT>
       <FREESHIPPING>boolean</FREESHIPPING>
   </ORDERDETAIL>
</ORDER>
]]>
```

This XML document is constructed by your system and is passed over to Firestorm® in the “OrderDetail” argument. The layout of the XML document is not optional and must be followed exactly to ensure that your order can be read and processed successfully by the Firestorm® system. 

The following table describes in detail the various elements of this document along with definitions and requirements for each section: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|<![CDATA[|||Required openingCDATA tag|
|<?xml ……|||Required XML document header(see example above)|
|ORDER||Itemcount|Containing envelope for the order.|
||||Attribute “itemcount” must be set to the total number of ORDERDETAIL<br>envelopes that arepresent on the order.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 155 | 317 

Firestorm® Web Services API | Version 2.2.33 

|ORDERDETAIL||Containing envelope for a single line item on the order<br>Each line item from the order will be contained in a separate ORDERDETAIL<br>envelope. Don’t forget to increment the attributor “itemcount” on the ORDER<br>envelope by1 for each ORDERDETAILpresent in the document.|
|---|---|---|
|PRODUCTNUMBER|String|Product number that exists in the catalogspecified in the web service call|
|PRODUCTQTY|Integer|Quantityof this item to order|
|PRICEEACH|Double|Actual price paid for EACH item (do not multiply this by PRODUCTQTY. The<br>system will do that for you).<br>**WARNING: Only set this value if you are NOT providing**<br>**Retail/Wholesale/Upline/PSV. If you set this value it will override what is in the**<br>**RETAILPRICEEACH and WHOLESALEPRICEEACH price fields!**<br>**If you are providing explicit pricing using the fields below, set this value to $0**|
|RETAILPRICEEACH|Double|Retail price for each product. Do not multiply by PRODUCTQTY. Setting this value<br>to -1 will cause the system to use theprice configured in the catalog.|
|WHOLESALEPRICEEACH|Double|Wholesale price for each product. Do not multiply by PRODUCTQTY. Setting this<br>value to -1 will cause the system to use theprice configured in the catalog.|
|UPLINEVOLUMEEACH|Double|Upline (commissionable) volume for each product. Do not multiply by<br>PRODUCTQTY. Setting this value to -1 will cause the system to use the price<br>configured in the catalog.|
|PSVAMOUNTEACH|Double|PSV Amount for each product. Do not multiply by PRODUCTQTY. Setting this<br>value to -1 will cause the system to use theprice configured in the catalog.|
|ISFREEPRODUCT|Boolean|Flag to indicate if this is a free product. “True” = is a free product, “False” = not a<br>freeproduct|
|FREESHIPPING|Boolean|Flag to indicate if shipping charges should be suppressed for this product. “True”<br>= no shipping will be calculated, “False” = shipping charges will be calculated<br>normally.|
|]]>||Required closingof CDATA tag|



##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS,this node will contain the new OrderID created bythe system.|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 156 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.SaveOrderExtended 

Allows an external shopping cart to transmit an order into the Firestorm® system for processing. Typically used by 3<sup>rd</sup> party shopping carts that a company might want to use in lieu of the shopping cart included with the Firestorm® system. 

This extended version of SaveOrder() adds the ability to partially or completely pay for the order with unpaid commissions from the Dealer’s commission account. 

**PCI/DSS WARNING:** This web service uses sensitive personal and payment information to process an order. It is YOUR responsibility to ensure that you are following all proper PCI/DSS procedures in addition to accessing the web service over a secure (https) link in your production environment!! 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|C|DealerID of an existing dealer in the system. This<br>value must be supplied if CustomerDealerID is not.|Integer|-1 or any existing<br>DealerID in Firestorm<br>that is not flagged as<br>a customer.|
|ShippingCode|Y|The code defined by Firestorm® to identify the<br>shipping method to use for this order|String|Any valid shipper<br>code defined in<br>Firestorm®|
|ShipAddress1|Y|ShippingAddress Line 1|String||
|ShipAddress2|Y|Shipping Address Line 2|String|May be an empty<br>string|
|ShipCity|Y|ShippingCity|String||
|ShipState|Y|Shipping State|String|Any valid state code<br>defined in Firestorm®|
|ShipZip|Y|Shipping postal code|String||
|ShipCountry|Y|Shipping Country|String|Any valid country<br>code defined in<br>Firestorm®|
|Phone|Y|Phone number|String||
|OrderTotalAmount|Y|Total dollar amount of the products on the order.<br>(do not include any other fees) This value is used to<br>validate the calculated amount contained in the<br>order detail XML.<br>OVERRIDE: When you pass -99 in this field, the<br>system will calculate the total amount of the order<br>from the order detail XML passed in and will NOT<br>compare it to this number.||-99 or actual dollar<br>amount|
|SpecialInstructions|Y|Any special instructions for this order. Typically<br>collected from the purchaser. This value will appear<br>on the shippingorder(or shippingexport).|String||
|CatalogueID|Y|The Firestorm® catalog ID from Firestorm®|Integer|Any valid catalog ID<br>defined in Firestorm®|
|BillFirstName|C|BillingFirst Name|String||
|BillLastName|C|BillingLast Name|String||
|BillCompanyName|C|Billing Company Name (must be provided if first and<br>last name are blank)|String||
|BillAddress1|Y|BillingAddress Line 1|String||
|BillAddress2|Y|Billing Address Line 2|String|May be an empty<br>string|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 157 | 317 

Firestorm® Web Services API | Version 2.2.33 

|BillCity|Y|BillingCity|String||
|---|---|---|---|---|
|BillState|Y|BillingState|String||
|BillZip|Y|Billing postal code|String||
|BillCountry|Y|Billing Country|String|Any valid country<br>code defined in<br>Firestorm®|
|CustomerDealerID|C|DealerID of an existing customer. Must be supplied if<br>DealerID is not supplied.|Integer|-1 or Any existing<br>DealerID that is<br>flagged as a<br>customer record|
|TotalOrderDiscount|Y|Total dollar value of the discount applied to this<br>order|Double|Must be >= 0|
|ShipTo|Y|First and Last Name of the purchaser. This value (if<br>passed in) will be used as part of the shipping<br>address in the system. If the values is passed as an<br>empty string, the BillFirstName and BillLastName will<br>be used in the shippingaddress,|String||
|TotalOrderDiscountPercentage|Y|The total discount applied as a percentage of the<br>total order.|Double|Must be a value<br>between 0 and 1|
|AutoshipOrder|Y|Flag to indicate if this order should count as an<br>autoship (recurring order) (generally for qualification<br>purposes).<br>When this flag is set to TRUE the system will<br>populate the value of 88888888 into the<br>RecurringParentOrderID field on the order header.|Boolean|true OR false|
|OrderDetail|Y|Complex XML document describing the contents of<br>the order (see details below)|String|See description<br>below<br>_Hint: Don’t forget_<br>_CDATA tags!_|
|AddlPaymentInfo|Y|Any additional payment information you wish to be<br>stored with this order. This data is NOT used by<br>Firestorm® and is stored for historical purposes only.<br>NOTE: This value is only saved when the order<br>successfully processes in the system.|String||
|PaymentTypeCode|Y|Code representing the type of payment to use to pay<br>for this order.<br>**Note: E-Check payment types are not currently**<br>**supported by this web service.**|String|Any valid payment<br>type code defined in<br>Firestorm®|
|CardAccountNumber|C*|Credit card account number|String||
|CVV2Code|C*|Securitycode from the back of the credit card|String||
|CardHolderName|C*|<br>Name as it appears on the credit card|String||
|CardExpirationMonth|C*|Expiration date month expressed as a 2 digit<br>number,zero filled.|String|Must be between 01<br>and 12|
|CardExpirationYear|C*|Expirationyear expressed as a 4 digit number|String|Anyvalidyear|
|Email|Y|Email address where order receipt will be sent|String|A valid email address|
|CommissionAmountToUse|Y|The amount of unpaid commission to use from the<br>Dealer’s commission account to help pay for this<br>order.|Double||
|||**This capability may only be used for member**<br>**orders. Customer orders will not be allowed to use**<br>**this capability.**|||



* **Note: If the payment type code flagged as a credit card in Firestorm, these conditional fields are required.** 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
||C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c .P a g e158 | 317|



Firestorm® Web Services API | Version 2.2.33 

|Fields|No|
|---|---|
|Max Records|No|



##### **<u>Additional Information</u>** 

##### <u>Using Commissions To Pay</u> 

When commission is requested to be used as payment, the system will validate that there is enough unpaid commission in the Dealer’s account to cover the request. If there is not, an error will be generated and returned to you. 

For commission to be used, it must be “unpaid”. That is, it must not have been put on a check (or wired) for payment. Once it has been allocated to a check, then it is no longer available for use to pay for an order. 

If your compensation plan calls for commissions to be place on hold (for any reason) before they are released to the Dealer, any commissions that are currently on hold will NOT be available to be used to pay for the order. 

Commission CAN be used to partially pay for an order. When this is desired, simply pass the amount of commission to use in the field “CommissionAmountToUse” and the system will deduct this amount from the total amount due before charging the payment method for the balance. If you desire to pay for the order 100% with commissions, then the amount passed in this field must match the total amount due for the order. You must still pass over a valid payment type in this event just in case you miscalculated the system will be able to collect the remaining balance from the payment type specified. If there is no remaining balance the payment type will not be charged. 

##### <u>Required Fields You Do Not Have A Value For</u> 

As there are no “optional” arguments in this web service, If a field calls for a string datatype and you do not wish to pass a value or do not need to (i.e.: credit card fields), simply pass an empty (“”) string in place of that argument. If you pass an empty string in an argument where the requirement is not optional, an error will be generated and sent back to you. 

##### <u>Normal Processing Still Occurs</u> 

When an order is passed to this web service, it will be treated exactly like a regular shopping cart order. All autoresponder emails (such as an order receipt) will be sent out per normal system operations. Any other special actions that can be triggered by a shopping cart order will still be triggered normally. It is not possible to suppress this behavior. Be aware of this when transmitting orders in this manner. 

##### <u>Payment</u> 

When an order is submitted to Firestorm® via this web service, the system WILL charge the payment method if the value of the order is greater than $0. Therefore, if your external system is processing the payment PRIOR to submitting the order to Firestorm®, you must specify a non-credit card payment type such as “CASH”. You may set up a custom payment type expressly for this purpose as long as it is not flagged as a credit card type. (See the Firestorm® Use and Operations Manual for details on how to accomplish this) 

If the order amount is greater than $0, and you specified a payment type that is flagged as a credit card in Firestorm®, the credit card engine in the system will process the request normally per the current system 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 159 | 317 

Firestorm® Web Services API | Version 2.2.33 

configurations. Please note that the credit card will be validated before being submitted. The system will perform basic validation such as mod10, expiration date check and will ensure all required data items are present. Per PCI guidelines, the CVV2 code will not be stored in the system and will only be used to process the current request. 

##### <u>Currency Conversion</u> 

When an order is being processed by the system for this enrollment, the system will look up the country specified in “BillingCountry” to see if a default currency has been defined for that country. If it has, the currency type and the defined conversion ratio for that currency will be saved as part of the order. Normal Firestorm® currency processing will still occur based on system setup and configurations. 

##### <u>Member Orders</u> 

When the incoming order is for a member in the system, their DealerID must be supplied. In this scenario, CustomerDealerID should be passed as -1. The DealerID passed in MUST already exist in the system, 

##### <u>Customer Orders</u> 

When the incoming order is for a customer (non-member), the DealerID field should be set to -1 and the CustomerDealerID should be set to the customer’s DealerID. The customer’s DealerID must already exist in the system. 

Note that when a customer order is sent through this web service, the system will look up the original referring dealer for this customer and will credit this order to that member for commission and qualification purposes. 

##### <u>Order Detail XML</u> 

When calling this web service, this field allows you to build the order on your system, then pass it over to Firestorm® as an XML document as shown below.  You will build an <ORDERDETAIL> element for each line item in your order, then embed them all in a containing <ORDER> element. This payload is not limited to the number of items that may be specified for a single order, allowing you to specify the order contents and pricing in any way necessary to meet your need. 

When building this document, remember that even though you can override pricing for a given product, that product MUST exist in the catalog specified in your call. If a product is missing, the call will fail. 

##### The <ORDER> element must contain at least 1 <ORDERDETAIL> element. 

If you have passed over a valid value in the “OrderTotalAmount” field, the system will calculate the total price of the products on the order based on this XML document and will then compare the calculated value to the amount you passed over. The amounts must match exactly or the order will be rejected. This facility is intended to be a final “sanity” check to ensure that the XML document contains everything it is supposed to. You may disable this check by passing “-99” in the “OrderTotalAmount” field. 

**_Hint:_** _The passed XML document must be completely valid so that it may be parsed correctly by Firestorm®. Please test your XML document thoroughly to ensure that it can be loaded without error by an XML parser. This will avoid problems with your successful use of this web service._ 

**Uppercase and lowercase matter in XML** . Opening and closing tags must match exactly. For example, `<ROOT>` , `<Root>` , and `<root>` are three different tags 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 160 | 317 

Firestorm® Web Services API | Version 2.2.33 

The following is a sample of the XML document required: 

```
' ///////////////////////////
' Sample order detail XML
' ///////////////////////////
<![CDATA[
<?xml version='1.0' encoding='utf-8' ?>
<ORDER itemcount='1'>
   <ORDERDETAIL>
       <PRODUCTNUMBER>string</PRODUCTNUMBER>
       <PRODUCTQTY>integer</PRODUCTQTY>
       <PRICEEACH>double</PRICEEACH>
       <RETAILPRICEEACH></RETAILPRICEEACH>
       <WHOLESALEPRICEEACH></WHOLESALEPRICEEACH>
       <UPLINEVOLUMEEACH></UPLINEVOLUMEEACH>
       <PSVAMOUNTEACH></PSVAMOUNTEACH>
       <ISFREEPRODUCT>boolean</ISFREEPRODUCT>
       <FREESHIPPING>boolean</FREESHIPPING>
   </ORDERDETAIL>
</ORDER>
]]>
```

This XML document is constructed by your system and is passed over to Firestorm® in the “OrderDetail” argument. The layout of the XML document is not optional and must be followed exactly to ensure that your order can be read and processed successfully by the Firestorm® system. 

The following table describes in detail the various elements of this document along with definitions and requirements for each section: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|<![CDATA[|||Required openingCDATA tag|
|<?xml ……|||Required XML document header(see example above)|
|ORDER||Itemcount|Containing envelope for the order.<br>Attribute “itemcount” must be set to the total number of ORDERDETAIL<br>envelopes that arepresent on the order.|
|ORDERDETAIL|||Containing envelope for a single line item on the order<br>Each line item from the order will be contained in a separate ORDERDETAIL<br>envelope. Don’t forget to increment the attributor “itemcount” on the ORDER<br>envelope by1 for each ORDERDETAILpresent in the document.|
|PRODUCTNUMBER|String||Product number that exists in the catalogspecified in the web service call|
|PRODUCTQTY|Integer||Quantityof this item to order|
|PRICEEACH|Double||Actual price paid for EACH item (do not multiply this by PRODUCTQTY. The<br>system will do that for you).<br>**WARNING: Only set this value if you are NOT providing**<br>**Retail/Wholesale/Upline/PSV. If you set this value it will override what is in the**<br>**RETAILPRICEEACH and WHOLESALEPRICEEACH price fields!**<br>**If you are providing explicit pricing using the fields below, set this value to $0**|
|RETAILPRICEEACH|Double||Retail price for each product. Do not multiply by PRODUCTQTY. Setting this value<br>to -1 will cause the system to use theprice configured in the catalog.|
|WHOLESALEPRICEEACH|Double||Wholesale price for each product. Do not multiply by PRODUCTQTY. Setting this<br>value to -1 will cause the system to use theprice configured in the catalog.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 161 | 317 

Firestorm® Web Services API | Version 2.2.33 

|UPLINEVOLUMEEACH|Double|Upline (commissionable) volume for each product. Do not multiply by<br>PRODUCTQTY. Setting this value to -1 will cause the system to use the price<br>configured in the catalog.|
|---|---|---|
|PSVAMOUNTEACH|Double|PSV Amount for each product. Do not multiply by PRODUCTQTY. Setting this<br>value to -1 will cause the system to use theprice configured in the catalog.|
|ISFREEPRODUCT|Boolean|Flag to indicate if this is a free product. “True” = is a free product, “False” = not a<br>freeproduct|
|FREESHIPPING|Boolean|Flag to indicate if shipping charges should be suppressed for this product. “True”<br>= no shipping will be calculated, “False” = shipping charges will be calculated<br>normally.|
|]]>||Required closingof CDATA tag|



##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS,this node will contain the new OrderID created bythe system.|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 162 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.SaveOrderExtendedWithOptions 

Allows an external shopping cart to transmit an order into the Firestorm® system for processing. Typically used by 3<sup>rd</sup> party shopping carts that a company might want to use in lieu of the shopping cart included with the Firestorm® system. 

This super extended version of SaveOrder() adds the ability to provide an additional XML document that will contain all future extensions to this web service in the form of an XML document that will continue to grow as additional options are added. Please refer to the options XML further down for full details on which options are available and how they work. 

**PCI/DSS WARNING:** This web service uses sensitive personal and payment information to process an order. It is YOUR responsibility to ensure that you are following all proper PCI/DSS procedures in addition to accessing the web service over a secure (https) link in your production environment!! 

|Method Definition|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|C|DealerID of an existing dealer in the system.<br>This value must be supplied if<br>CustomerDealerID is not.|Integer|-1 or any existing<br>DealerID in<br>Firestorm that is<br>not flagged as a<br>customer.|
|ShippingCode|Y|The code defined by Firestorm® to identify the<br>shipping method to use for this order|String|Any valid shipper<br>code defined in<br>Firestorm®|
|ShipAddress1|Y|ShippingAddress Line 1|String||
|ShipAddress2|Y|Shipping Address Line 2|String|May be an empty<br>string|
|ShipCity|Y|ShippingCity|String||
|ShipState|Y|Shipping State|String|Any valid state<br>code defined in<br>Firestorm®|
|ShipZip|Y|Shipping postal code|String||
|ShipCountry|Y|Shipping Country|String|Any valid country<br>code defined in<br>Firestorm®|
|Phone|Y|Phone number|String||
|OrderTotalAmount|Y|Total dollar amount of the products on the<br>order. (do not include any other fees) This value<br>is used to validate the calculated amount<br>contained in the order detail XML.<br>OVERRIDE: When you pass -99 in this field, the<br>system will calculate the total amount of the<br>order from the order detail XML passed in and<br>will NOT compare it to this number.||-99 or actual dollar<br>amount|
|SpecialInstructions|Y|Any special instructions for this order. Typically<br>collected from the purchaser. This value will<br>appear on the shipping order (or shipping<br>export).|String||
|CatalogueID|Y|The Firestorm® catalog ID from Firestorm®|Integer|Any valid catalog ID<br>defined in<br>Firestorm®|
|BillFirstName|C|BillingFirst Name|String||



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 163 | 317 

Firestorm® Web Services API | Version 2.2.33 

|BillLastName<br>|C|BillingLast Name<br>|String||
|---|---|---|---|---|
|BillCompanyName<br>BillAddress1|C<br>Y|Billing Company Name (must be provided if first<br>and last name are blank)<br>BillingAddress Line 1|String<br>String||
|BillAddress2|Y|Billing Address Line 2|String|May be an empty<br>string|
|BillCity|Y|BillingCity|String||
|BillState|Y|BillingState|String||
|BillZip|Y|Billing postal code|String||
|BillCountry|Y|Billing Country|String|Any valid country<br>code defined in<br>Firestorm®|
|CustomerDealerID|C|DealerID of an existing customer. Must be<br>supplied if DealerID is not supplied.|Integer|-1 or Any existing<br>DealerID that is<br>flagged as a<br>customer record|
|TotalOrderDiscount|Y|Total dollar value of the discount applied to this<br>order|Double|<br>Must be >= 0|
|ShipTo|Y|First and Last Name of the purchaser. This value<br>(if passed in) will be used as part of the shipping<br>address in the system. If the values is passed as<br>an empty string, the BillFirstName and<br>BillLastName will be used in the shipping<br>address|String||
|TotalOrderDiscountPercentage|Y|,<br>The total discount applied as a percentage of<br>the total order.|Double|Must be a value<br>between 0 and 1|
|AutoshipOrder|Y|Flag to indicate if this order should count as an<br>autoship (recurring order) (generally for<br>qualification purposes).<br>When this flag is set to TRUE the system will<br>populate the value of 88888888 into the<br>RecurringParentOrderID field on the order<br>header.|Boolean|true OR false|
|OrderDetail|Y|Complex XML document describing the<br>contents of the order (see details below)|String|See description<br>below<br>_Hint: Don’t forget_<br>_CDATA tags!_|
|AddlPaymentInfo|Y|Any additional payment information you wish<br>to be stored with this order. This data is NOT<br>used by Firestorm® and is stored for historical<br>purposes only.<br>NOTE: This value is only saved when the order<br>successfully processes in the system.|String||
|PaymentTypeCode|Y|Code representing the type of payment to use<br>to pay for this order.<br>**WARNING: When passing in a payment token**<br>**in the options XML document, this field MUST**<br>**be set to “TOKEN”, and this payment type**<br>**must exist in Firestorm® and be flagged as**<br>**“IsToken”**|String|Any valid payment<br>type code defined<br>in Firestorm®|
|||**Note: E-Check payment types are not currently**<br>**supported by this web service.**|||
|CardAccountNumber|C*|Credit card account number|String||
|CVV2Code|C*|Securitycode from the back of the credit card|String||
|CardHolderName|C*|Name as it appears on the credit card|String||
|CardExpirationMonth|C*|Expiration date month expressed as a 2 digit<br>bflld|String|Must be between<br>d|
|CardExpirationYear|C*|numer,zero ie.<br>Expirationyear expressed as a 4 digit number|String|01 an 12<br>Anyvalidyear|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 164 | 317 

Firestorm® Web Services API | Version 2.2.33 

|Email|Y|Email address where order receipt will be sent|String|A valid email<br>address|
|---|---|---|---|---|
|CommissionAmountToUse|Y|The amount of unpaid commission to use from<br>the Dealer’s commission account to help pay for<br>this order.<br>**This capability may only be used for member**<br>**orders. Customer orders will not be allowed to**<br>**use this capability.**|Double||
|OptionsXML||Complex XML document describing the<br>contents of the order (see details below)|String|See description<br>below<br>_Hint: Don’t forget_<br>_CDATA tags!_|



- **Note: If the payment type code flagged as a credit card in Firestorm, these conditional fields are required.** 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

##### <u>Using Commissions To Pay</u> 

When commission is requested to be used as payment, the system will validate that there is enough unpaid commission in the Dealer’s account to cover the request. If there is not, an error will be generated and returned to you. 

For commission to be used, it must be “unpaid”. That is, it must not have been put on a check (or wired) for payment. Once it has been allocated to a check, then it is no longer available for use to pay for an order. 

If your compensation plan calls for commissions to be placed on hold (for any reason) before they are released to the Dealer, any commissions that are currently on hold will NOT be available to be used to pay for the order. 

Commission CAN be used to partially pay for an order. When this is desired, simply pass the amount of commission to use in the field “CommissionAmountToUse” and the system will deduct this amount from the total amount due before charging the payment method for the balance. If you desire to pay for the order 100% with commissions, then the amount passed in this field must match the total amount due for the order. You must still pass over a valid payment type in this event just in case you miscalculated the system will be able to collect the remaining balance from the payment type specified. If there is no remaining balance the payment type will not be charged. 

##### <u>Required Fields You Do Not Have A Value For</u> 

As there are no “optional” arguments in this web service, If a field calls for a string datatype and you do not wish to pass a value or do not need to (i.e.: credit card fields), simply pass an empty (“”) string in place of that argument. If you pass an empty string in an argument where the requirement is not optional, an error will be generated and sent back to you. 

##### <u>Normal Processing Still Occurs</u> 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 165 | 317 

Firestorm® Web Services API | Version 2.2.33 

When an order is passed to this web service, it will be treated exactly like a regular shopping cart order. All autoresponder emails (such as an order receipt) will be sent out per normal system operations. Any other special actions that can be triggered by a shopping cart order will still be triggered normally. It is not possible to suppress this behavior. Be aware of this when transmitting orders in this manner. 

##### <u>Payment</u> 

When an order is submitted to Firestorm® via this web service, the system WILL charge the payment method if the value of the order is greater than $0. Therefore, if your external system is processing the payment PRIOR to submitting the order to Firestorm®, you must specify a non-credit card payment type such as “CASH”. You may set up a custom payment type expressly for this purpose as long as it is not flagged as a credit card type. (See the Firestorm® Use and Operations Manual for details on how to accomplish this) 

If the order amount is greater than $0, and you specified a payment type that is flagged as a credit card in Firestorm®, the credit card engine in the system will process the request normally per the current system configurations. Please note that the credit card will be validated before being submitted. The system will perform basic validation such as mod10, expiration date check and will ensure all required data items are present. Per PCI guidelines, the CVV2 code will not be stored in the system and will only be used to process the current request. 

##### <u>Currency Conversion</u> 

When an order is being processed by the system for this enrollment, the system will look up the country specified in “BillingCountry” to see if a default currency has been defined for that country. If it has, the currency type and the defined conversion ratio for that currency will be saved as part of the order. Normal Firestorm® currency processing will still occur based on system setup and configurations. 

##### <u>Member Orders</u> 

When the incoming order is for a member in the system, their DealerID must be supplied. In this scenario, CustomerDealerID should be passed as -1. The DealerID passed in MUST already exist in the system, 

##### <u>Customer Orders</u> 

When the incoming order is for a customer (non-member), the DealerID field should be set to -1 and the CustomerDealerID should be set to the customer’s DealerID. The customer’s DealerID must already exist in the system. 

Note that when a customer order is sent through this web service, the system will look up the original referring dealer for this customer and will credit this order to that member for commission and qualification purposes. 

##### <u>Order Detail XML</u> 

When calling this web service, this field allows you to build the order on your system, then pass it over to Firestorm® as an XML document as shown below.  You will build an <ORDERDETAIL> element for each line item in your order, then embed them all in a containing <ORDER> element. This payload is not limited to the number of items that may be specified for a single order, allowing you to specify the order contents and pricing in any way necessary to meet your need. 

When building this document, remember that even though you can override pricing for a given product, that product MUST exist in the catalog specified in your call. If a product is missing, the call will fail. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 166 | 317 

Firestorm® Web Services API | Version 2.2.33 

The <ORDER> element must contain at least 1 <ORDERDETAIL> element. 

If you have passed over a valid value in the “OrderTotalAmount” field, the system will calculate the total price of the products on the order based on this XML document and will then compare the calculated value to the amount you passed over. The amounts must match exactly or the order will be rejected. This facility is intended to be a final “sanity” check to ensure that the XML document contains everything it is supposed to. You may disable this check by passing “-99” in the “OrderTotalAmount” field. 

**_Hint:_** _The passed XML document must be completely valid so that it may be parsed correctly by Firestorm®. Please test your XML document thoroughly to ensure that it can be loaded without error by an XML parser. This will avoid problems with your successful use of this web service._ 

**Uppercase and lowercase matter in XML** . Opening and closing tags must match exactly. For example, `<ROOT>` , `<Root>` , and `<root>` are three different tags 

The following is a sample of the XML document required: 

```
' ///////////////////////////
' Sample order detail XML
' ///////////////////////////
<![CDATA[
<?xml version='1.0' encoding='utf-8' ?>
<ORDER itemcount='1'>
   <ORDERDETAIL>
       <PRODUCTNUMBER>string</PRODUCTNUMBER>
       <PRODUCTQTY>integer</PRODUCTQTY>
       <PRICEEACH>double</PRICEEACH>
       <RETAILPRICEEACH></RETAILPRICEEACH>
       <WHOLESALEPRICEEACH></WHOLESALEPRICEEACH>
       <UPLINEVOLUMEEACH></UPLINEVOLUMEEACH>
       <PSVAMOUNTEACH></PSVAMOUNTEACH>
       <ISFREEPRODUCT>boolean</ISFREEPRODUCT>
       <FREESHIPPING>boolean</FREESHIPPING>
   </ORDERDETAIL>
</ORDER>
]]>
```

This XML document is constructed by your system and is passed over to Firestorm® in the “OrderDetail” argument. The layout of the XML document is not optional and must be followed exactly to ensure that your order can be read and processed successfully by the Firestorm® system. 

The following table describes in detail the various elements of this document along with definitions and requirements for each section: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|<![CDATA[|||Required openingCDATA tag|
|<?xml ……|||Required XML document header(see example above|
|ORDER||Itemcount|Containing envelope for the order.<br>Attribute “itemcount” must be set to the total number of ORDERDETAIL<br>envelopes that arepresent on the order.|
|ORDERDETAIL|||Containing envelope for a single line item on the order<br>Each line item from the order will be contained in a separate ORDERDETAIL|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 167 | 317 

Firestorm® Web Services API | Version 2.2.33 

|||envelope. Don’t forget to increment the attributor “itemcount” on the ORDER<br>envelope by1 for each ORDERDETAILpresent in the document.|
|---|---|---|
|PRODUCTNUMBER|String|Product number that exists in the catalogspecified in the web service call|
|PRODUCTQTY|Integer|Quantityof this item to order|
|PRICEEACH|Double|Actual price paid for EACH item (do not multiply this by PRODUCTQTY. The<br>system will do that for you).<br>**WARNING: Only set this value if you are NOT providing**<br>**Retail/Wholesale/Upline/PSV. If you set this value it will override what is in the**<br>**RETAILPRICEEACH and WHOLESALEPRICEEACH price fields!**<br>**If you are providing explicit pricing using the fields below, set this value to $0**|
|RETAILPRICEEACH|Double|Retail price for each product. Do not multiply by PRODUCTQTY. Setting this value<br>to -1 will cause the system to use theprice configured in the catalog.|
|WHOLESALEPRICEEACH|Double|Wholesale price for each product. Do not multiply by PRODUCTQTY. Setting this<br>value to -1 will cause the system to use theprice configured in the catalog.|
|UPLINEVOLUMEEACH|Double|Upline (commissionable) volume for each product. Do not multiply by<br>PRODUCTQTY. Setting this value to -1 will cause the system to use the price<br>configured in the catalog.|
|PSVAMOUNTEACH|Double|PSV Amount for each product. Do not multiply by PRODUCTQTY. Setting this<br>value to -1 will cause the system to use theprice configured in the catalog.|
|ISFREEPRODUCT|Boolean|Flag to indicate if this is a free product. “True” = is a free product, “False” = not a<br>freeproduct|
|FREESHIPPING|Boolean|Flag to indicate if shipping charges should be suppressed for this product. “True”<br>= no shipping will be calculated, “False” = shipping charges will be calculated<br>normally.|
|]]>||Required closingof CDATA tag|



##### <u>Options XML</u> 

When calling this web service, it is possible to pass in an extended set of options using this field. It is only necessary to include the XML for the options you are trying to use for a given call to the system. 

NOTE: As new options are added to the system, this XML document will expand to include those new options. Please refer to the most current version of this document to obtain the most current sample xml for this field 

**Uppercase and lowercase matter in XML** . Opening and closing tags must match exactly. For example, `<ROOT>` , `<Root>` , and `<root>` are three different tags 

The following is an example of the options XML document: 

‘////////////////////////////////////////// ‘ SAMPLE OPTIONS XML ‘////////////////////////////////////////// `<![CDATA[` <?xml version='1.0' encoding='utf-8' ?> 

<OPTIONS optioncount='2'> 

<DONOTSENDORDERRECEIPTEMAIL>TRUE</DONOTSENDORDERRECEIPTEMAIL> 

<PAYMENTTOKEN> 

<TOKEN>d080d56d-f377-44ab-9728-cc51927ea346</TOKEN> <CCVENDORID>7</CCVENDORID> <DEALERID>43096</DEALERID> <CARDTYPE>VISA</CARDTYPE> <LAST4>2221</LAST4> 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 168 | 317 

Firestorm® Web Services API | Version 2.2.33 

<EXPIRATIONDATE>09/19/2019</EXPIRATIONDATE> <NAMEONCARD>TED FRENCH</NAMEONCARD> <ONETIMEUSE>false</ONETIMEUSE> 

</PAYMENTTOKEN> 

</OPTIONS> `]]>` 

This XML document is constructed by your system and is passed over to Firestorm® in the “OptionsXML” argument. The layout of the XML document and each possible option is not optional and must be followed exactly to ensure that your order can be read and processed successfully by the Firestorm® system. 

The following table describes in detail the various elements of this document along with definitions and requirements for each section: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|<![CDATA[|||Required openingCDATA tag|
|<?xml ……|||Required XML document header(see example above)|
|OPTIONS||optioncount|Containing envelope for the option containers being used.<br>Attribute “optioncount” must be set to the total number of options<br>that arepresent.|
|DONOTSENDORDERRECEIPTEMAIL|Boolean||Must be set to “true” or “false”.<br>This option will allow the suppression of the order receipt email that<br>Firestorm® would normally send out whenever an order is saved into<br>the system through this web service. The net result is that Firestorm®<br>will save the order silently.<br>If you choose to suppress this email, your system will be responsible<br>for notifyingthepurchaser that their order was received.|
|PAYMENTTOKEN|Envelope||Containing envelope for defined a payment token that should be used<br>to process the order being sent via this web service. Please note that<br>there are NO optional nodes in this envelope. All requested data must<br>be provided in order to successfully use the token.<br>**WARNING: When passing in a payment token in the options XML**<br>**document, the payment type field  MUST be set to “TOKEN”, and this**<br>**payment type must exist in Firestorm® and be flagged as “IsToken”**|
|<br>TOKEN|String||Actual payment token in whatever format is required by the credit card<br>vendor.(Typicallya GUID)|
|<br>CCVENDORID|Numeric||The credit card vendor ID as assigned by Firestorm®. You must obtain<br>this value from the Firestorm® admin console.<br>_Please note: If administrative personnel ever change the ID value, your_<br>_web service call MUST also change. This CCVendorID must exist in the_<br>_Firestorm® system or the request will be rejected._|
|<br>DEALERID|||The Firestorm® DealerID of the owner of the credit card. If this is a<br>customer order, you may pass in the Firestorm® CustomerDealerID if<br>available, or you may pass in “-1” if the DealerID is unknown.<br>_Warning: If a valid DealerID is not passed in with this node, the system_<br>_will automatically mark the token as a one time use token._|
|<br>CARDTYPE|String||Type of credit card.(i.e. VISA,MASTERCARD,etc)|
|<br>LAST4|String||Last 4 digits of the card represented bythe token<br>|
|<br>EXPIRATIONDATE|||The expiration date of the credit card in format MM/DD/YYYY|
|<br>NAMEONCARD|||First and Last name of the account holder|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 169 | 317 

Firestorm® Web Services API | Version 2.2.33 

|<br>ONETIME|USE|String|“true” or “false”. If this token is to be used only for this order, then the<br>value should be set to true. Otherwise, the system will store the token<br>for future use by this person.<br>_Remember: If no DealerID is supplied, the system will automatically set_<br>_thisflag to “true”._|
|---|---|---|---|
|]]><br>**Return Values**<br>This web service<br>this document al|will return<br>ong with d|a complex X<br>efinitions of|Required closingof CDATA tag<br>ML document containing the results of the call. The table below<br>each node:|
|**Element**|**DataType**|**Attribute**|**Definition**|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS,this node will contain the new OrderID created bythe system.|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 170 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.ValidatePurchase 

Allows a remote system to determine if a purchase of a specific product was made by a Dealer within a specific time frame. Generally used to validate a membership purchase of some type before granting access to a remote system. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The dealer who is being checked|Integer|Any valid existing<br>DealerID.|
|ProductNumber|Y|The product number to search for|String|Any valid product<br>number as defined in<br>Firestorm®|
|StartDate|Y|The starting date for the range|Date|Must be a date that<br>occurs before the<br>end date|
|EndDate|Y|The ending date for the range|Date|Must be a date that<br>occurs after the start<br>date|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The system will search for any order placed by the dealer that was placed during the time frame designated by the start and end date. 

The start date time stamp will be overridden to “00:00:00 AM” 

The end date timestamp will be overridden to “11:59:59 PM” 

The order must not be voided, and must not be on hold. 

##### **<u>Return Values</u>** 

The web service will return a string containing the results of the search.  The format of the returned string is as follows: 

##### **If one or more orders have been processed for the requested product** : 

Returned String: “TRUE” 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 171 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **If no orders have been processed successfully** : 

Returned string: “FALSE: Requested product not purchased within the timeframe;” 

-or- 

Returned String: “FALSE: No record returned by order query;” 

If multiple errors occurred during the timeframe, the system will concatenate each error together separated by “;” 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 172 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.GetFirestormTaxRate 

Gives a remote system the ability to get the calculated Firestorm sales tax rate based on current system configurations. This will ensure that a remote system will be using the exact same tax rate as Firestorm®. 

|Method Definitio|n<br>||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DestinationState|Y|The state to calculate tax for|String|State code as defined<br>in Firestorm® where<br>package is being<br>shipped to|
|DestinationCity|Y|The city to calculate tax for|String|City name where<br>package is being<br>shipped to|
|DestinationCountry|Y|The country to calculate sale tax for|String|State code as defined<br>in Firestorm® where<br>package is being<br>shipped to|
|DestinationZip|Y|The postal code to calculate tax for|String|The destination zip<br>code where package<br>is beingshipped to|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This web service will invoke the Firestorm® sales tax engine and will calculate tax based on current system configurations. Please coordinate with the system administrator to determine how your system is configured to determine what type of results to expect from this call. 

NOTE: If your system is configured to use a 3<sup>rd</sup> party tax service such as Avalara® or CCH®, this web service will not return results from those services. This web service may only be used if you are using the tax engine included with the Firestorm® system. 

##### **<u>Return Values</u>** 

|Returned Data<br>Field Name|SQL Datatype|Comments|
|---|---|---|
|TaxRate|Double|Sales tax rate|
|ShipTaxRate|Double|If shipping charges are taxable this will be the tax rate to use<br>for shippingcharges|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 173 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.GetOrders 

This web service is intended to be used as a detailed report of order activity that can be used by a 3<sup>rd</sup> party 

fulfillment house or shipping service that needs to pull detailed order information from the Firestorm system. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|StartDate|Y|The start of the range|Date|Must occur before<br>end date|
|EndDate|Y|The end of the range|Date|Must occur after start<br>date|
|IncludeFullfilledOrders|Y|Flag to indicate whether or not to include orders<br>that are alreadymarked as fulfilled byFirestorm®|Boolean|0 = Do not include<br>-1 = Include|
|ProductNumber|Y|If provided, the system will only pull orders that<br>contain the specified product number.<br>**Note: If you do not want to use this filter, simply**<br>**pass in an empty string (“”)**|String|Any valid product<br>number define in<br>Firestorm®|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This web service will return all information regarding any order placed that falls within the parameters provided. The output of this service is LARGE, and your system must be prepared to deal with it’s output. 

The web service will output 1 line for each detail item on an order. This means that the order header information is repeated on each line, with the detail information being different. 

Please note that the data delivered by this web service is basically a “report” of orders in the system. **<u>No action is taken against the orders pulled</u>** <u>. If you are using this web service as a pull from a fulfillment center, YOU MUST</u> TAKE FURTHER ACTION to ensure that the orders are marked as fulfilled properly in Firestorm®. 

##### <u>Output not filtered</u> 

The information retuned by the web service does not filter out voided orders, and will include orders that are already fulfilled unless you specifically tell it not to. It is up to you to perform all additional processing necessary to do this type of filtering as required. 

##### **<u>Return Values</u>** 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 174 | 317 

Firestorm® Web Services API | Version 2.2.33 

|Returned Data|||
|---|---|---|
|Field Name<br>|SQL Datatype<br>|Comments<br>|
|ProductNumber<br>ProductID|String<br>Integer|Product number from catalog<br>Unique ID for theproduct number|
|OrderID|Integer|Unique ID from the order|
|Account|String|Internal account number|
|ShipperID|Integer|Unique ID from tblShipper. Correlates to the shipper selected<br>for this order.|
|SubAccount<br>|String|Internal sub account number<br>|
|DealershipID|Integer|Unique ID for the dealership associated with this order. If this<br>is a member order, this is their own dealershipID. If thisis a<br>customer order,this value is their sponsor’s dealershipID.|
|ShipTo<br>|String<br>|Theperson this order is shippingto.|
|ShipAddress1|String||
|ShipAddress2|String||
|ShipCity <br>|String<br>||
|ShipState|String||
|ShipZip <br>|String<br>||
|ShipCountry|String||
|UCFirstName|String|Unicode enabled|
|UCLastName|String|Unicode enabled|
|UCCompanyName|String|Unicode enabled|
|UCShipAddress1|String|Unicode enabled|
|UCShipAddress2|String|Unicode enabled|
|UCShipCity <br>|String|Unicode enabled<br>|
|UCShipState<br>UCShiZi|String<br>Sti|Unicode enabled<br>Uid bld|
|pp<br>UCShipCountry|rng<br>String|ncoe enae<br>Unicode enabled|
|Phone|String|Phone number for the person receiving this order (no<br>formattingapplied bythe system)|
|OrderDate|Date|Date this order was placed. (Note: This date may be<br>overridden in Firestorm®. People routinely backdate an order<br>to get it within a specific commission period. Use field<br>“OrderCreateDate” to see the date and time the order was<br>actuallycreated)|
|OrderFulFillDate|Date|Date that this order was fulfilled in Firestorm®.|
|Shipping|Double|Total shippingcharges for the order|
|Tax|Double|Total sales tax collected for this order|
|PrintDate|Date|Date the order wasprinted from within Firestorm®|
|RecurringFreq|integer|A number representing the number of “RecurringUnit” that<br>were used to control this recurring order. This value is only<br>populated if this live order was generated from a recurring<br>order template.|
|RecurringUnit|String|“DAYS”, “WEEKS” or “MONTHS”. This value is only populated<br>if this live order was generated from a recurring order<br>template.|
|RecurringLastOrderDate|Date|<br>The LAST time the “RecurringParentOrderID” was use dto<br>generate an order. This value is only populated if this live<br>order wasgenerated from a recurringorder template.|
|RecurringParentOrderID|Integer|<br>The unique ID of the recurring order template that was used<br>to generate this actual order. This value is only populated if<br>this live order was generated from a recurring order template.<br>**Note: If this field is populated with the value 88888888 or**<br>**99999999, then this order was manually flagged to count as**<br>**a recurring order (usually for qualification purposes)**|
|VoidedOrder|Boolean|Flag to indicate that this order has been voided.|
|||0 = not voided<br>Non-zero = voided|
|OrderVoidReason|String|Why this order was voided. Only populated on voided orders<br>that were voided in Firestorm®|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 175 | 317 

Firestorm® Web Services API | Version 2.2.33 

|SpecialInstructions|String|Special instructions that were entered by the person placing<br>the order. (Typically these are special delivery instructions<br>entered by the purchaser through the shopping cart. These<br>will print on the shipping order when printed through<br>Firestorm®)|
|---|---|---|
|Wholesale|Boolean|Flag to indicate that this is a wholesale order|
|||0 = Retail order<br>Non-zero = wholesale order|
|ReferringDealerID|Integer|The dealer ID of thememberwho referred the purchaser.<br>Only populated on customer orders.|
|ReferringDealershipID|Integer|The dealership ID of thememberwho referred the purchaser.<br>Only populated on customer orders.|
|ReadyToPrint|Boolean|Flag to indicate that this order is ready to print|
|||0 = Already printed<br>non-zero = Readytoprint|
|Other|Double|Total other fees that were collected (configured in Firestorm®.<br>This field is used for such things as processing fees, general<br>fees,,etc)|
|CatalogueID<br>|Integer<br>|The unique ID for the catalogused for this order|
|BillFirstName<br>|String<br>||
|BillLastname<br>BillAddress1|String<br>String||
|BillAddress2|String||
|BillCity|String||
|BillState|String||
|BillZip|String||
|BillCountry|String||
|RecurringDay|Integer|1 – 31. The day of the month that this recurring order is set up<br>to generate on. This value is only populated if this live order<br>wasgenerated from a recurringorder template.|
|OrderCreateDate|Date|Actual date and time that this order was created in the<br>database. (This date cannot be overridden by the user. Do not<br>use this date to control anything! Use “OrderDate” instead.)|
|RecurringBatchID|Integer|When this order was created as part of a recurring order<br>batch, this is the unique ID of that batch. This value is only<br>populated if this live order was generated from a recurring<br>order template.|
|PrintBatchID|Integer|When this order was printed as part of a batch or orders that<br>were allprinted at once,this is the unique ID of that batch.|
|OrderCreateBy|String|The login ID of the person who created the order. If this order<br>was created by a web shopping cart user, this field will<br>contain a value such as “WEB:813604” where the number<br>portion is the DealerID of the member/customer who placed<br>the order.|
|OrderMaintDate|Date|The date and time the order was edited in Firestorm®|
|OrderMaintBy|String|The login ID of the user whoperformed the edit|
|CustomerDealerID|Integer|If this is a customer order, then this is the DealerID associated<br>with the customer whoplaced the order.|
|NonProductPointsUsed|Double|If points were used to pay for any non-product charges (tax,<br>shipping,etc)this is the numberpoints used for thatpurpose.|
|PointValue|Double|The number ofpoints earned bythepurchase of thisproduct|
|PointBreakage|Double|If point rounding is in use (configured in the point system in<br>Firestorm®) then this is the number of points that were<br>considered as breakage to the company|
|OrderStatusID|Integer|<br>The unique of the status code that represents the current<br>status of this order. tblOrderStatus.OrderStatusID|
|WebOrder|Boolean|Flag to indicate that this order was placed through the web<br>shoppingcart|
|TotalOrderDiscount|Double|Total discount(in dollars)that wasgiven on this order|
|ParentOrderID|Integer|DO NOT USE. Custom Process Use Only|
|PartyID|Integer|The unique ID of the party that this order is credited to. This<br>value will onlybepresent on apartyorder.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 176 | 317 

Firestorm® Web Services API | Version 2.2.33 

|PartyGuestID|Integer|The unique ID of the party guest that is making the purchase.<br>(Note: Remember thatartuests DO NOT have a dealerID)|
|---|---|---|
|SoldTo|String|py g <br>The full name of theperson makingthepurchase|
|ShipToHost|Boolean|Flag indicating the this order is shipping to the party host<br>Non-zero = ship to the host<br>0 = not shippingdirectlyto thepartyhost|
|ShipToGuest|Boolean|Flag indicating the this order is shipping directly to the party<br>guest (drop ship)|
|||Non-zero = ship to the gues<br>0 = not shippingdirectlyto theguest|
|ShipToDealer|Boolean|Flag indicating the this order is shipping directly to the<br>member who sponsored the host.|
|||Non-zero = ship to the dealer<br>0 = not shippingdirectlyto the dealer|
|PartyShipTo|String|The name of the person the party order is shipping to (this<br>could be thepartyhost,the member or theguest|
|PartyShipAddress1|String|The address that the party order will ship to.|
|||**Note: This address could be the party host, member or guest**<br>|
|||**address depending on how the system is configured.**|
|PartyShipAddress2|String|“|
|<br>PartyShipCity|<br>String|“|
|PartyShipState|String|“|
|PartyShipZip|String|“|
|PartyShipCountry|String|“|
|PartyHostOrder|Boolean|Flag indicating that this is the party host award order.<br>0 = Not the host award order for the party<br>non-zero = This IS the host award order|
|PartyShipPhone|string|The phone number of the person that this party order is<br>shippingto|
|PartyBulkOrder|Boolean|LEGACY – DO NOT USE|
|OrderTypeID|Integer|The unique ID of the order type code.<br>tblOrderType.OrderTypeID|
|DateExported|Date|The date that this order was exported to a third party system.<br>Do not use this field unless you have been specifically told to<br>do so.  It is only populated bycustomprocesses.|
|TotalOrderDiscountPercentage|Double|The total discount applied to this order expressed as a<br>percentage. Will be between 0 and 1. (i.e.: a 10% discount<br>would be listed as .10)|
|AmountPaidByCommissions|Double|If commissions were used to pay for part or all of this order,<br>this is the total amount that was used.|
|LinkedParentOrderID|Integer|If this is a linked order, this is the OrderID in the system that<br>the current order is linked to. (The RMA system will link a<br>replacement order to the original order. The administrative<br>interface in Firestorm® also allows the customer service rep to<br>link two orders together for anyreason)|
|DealershipTypeCode|String|The code representing the members current Pay Rank when<br>the order wasplaced. tblDealershipType.Code|
|OrderDetailID|Integer|The unique ID for the order detail line this record represents|
|Qty|Integer|Thequantityof theproductpurchased|
|QtyFullfilled|Integer|The quantity of the product that was fulfilled. (For fulfilled<br>orders only)|
|BackorderedQty|Integer|<br>If the order detail could not be completely fulfilled because of<br>a backorder situation, this number represents the number of<br>items that are currentlyon backorder|
|VoidedOrderDetail|Boolean|Flag to indicate if this order detail was voided.|
|||0 = Not voided<br>non-zero = voided|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 177 | 317 

Firestorm® Web Services API | Version 2.2.33 

|OrderDetailVoidReason|String|If the detail is voided, this is the comment that was entered<br>bythe administrator|
|---|---|---|
|PriceEach|Double|<br>Price paid for each product (could be retail or wholesale<br>depending on how the system is configured). This number<br>does NOT takequantityinto account.|
|Discount|Double|Discount applied to this item|
|LineTotal<br>|Double<br>|(Pricepaid *Quantity)- Discount<br>|
|WeightLbs|Double|Total weight of this product in pounds.|
|||**Note**: When the system calculates total weight, quantity<br>ordered is multiplied by the configured weight for each item.<br>The system then breaks up tot total weight in pounds and<br>ounces andplaces the result into these fields.|
|WeightOzs|Double|Total weight of this product in ounces.   (see note under<br>“WeightLBS”|
|OrderDetailFulFillDate|Date|The date and time this item was fullfilled|
|FullfilledBy|String|The login ID of theperson who fulfilled the order|
|FullfillComments|String|Comments entered bytheperson who fulfilled the order|
|UplineVolume|Double|Total Upline volume for the order detail(Quantity* upline)|
|PSVAmount|Double|Total PSV for the order detail(PSV * upline)|
|NewStagedQty|Integer|INTERNAL USE ONLY|
|SponsorBonus|Double|INTERNAL USE ONLY|
|CountsAsXUnits|Integer|For system that sell product by the box, but need to know<br>how many units were in the box, this number represents the<br>total number of individual units that were in the box that was<br>sold. (i.e.: A case of water contains 24 bottles. This field would<br>be set to 24)|
|LevelCommissionsPaid|Boolean|INTERNAL USE ONLY|
|SponsorBonusProcedureName|<br>String|INTERNAL USE ONLY|
|SponsorBonusClassName|String|INTERNAL USE ONLY|
|SponsorBonusPaid|Boolean|INTERNAL USE ONLY|
|ProductBonusPaid|Boolean|INTERNAL USE ONLY|
|VolumePushDate|Date|INTERNAL USE ONLY|
|UnilevelVolumePushDate|Date|INTERNAL USE ONLY|
|BonusPayoutPending|Boolean|INTERNAL USE ONLY|
|PointsUsed|Double|If points were used to purchase this product, this is the<br>number ofpoints that were applied|
|PointsEarned|Double|If points are awarded for purchasing this product, then this is<br>the number ofproductpoints awarded.|
|PayWithPoints|Boolean|Flag to indicate that this detail item was paid for with points<br>0 = was not paid for with points<br>non-zero = Waspaid for withpoints|
|CataloguePriceInPoints|Double|The configuredprice inpoints for this item|
|AccumulatorNumber|Integer|INTERNAL USE ONLY|
|IsFreeProduct|Boolean|Flag to indicate that this product was added to the order as a<br>freeproduct.(i.e.: An award)|
|CodingBonusPaid|Boolean|INTERNAL USE ONLY|
|CodingBonusPayoutPending|Boolean|INTERNAL USE ONLY|
|FreeShipping|Boolean|Flag to indicate that this item should not be included in<br>calculating shipping charges|
|||0 = Include this item in chipping calculations<br>non-zero = Do not include this item in shippingcalculations|
|SaleComment|String|If this item was on sale, this comment will contain the name<br>of the sale as entered in Firestorm®|
|QuestionAnswers|String|If this product was configured to ask questions when it is<br>purchased, this is a special delimited string containing the<br>answers to those questions. The string will be formatted as<br>follows:<br>“1. item1/Blue 2. item2/Yellow 3. item3/Red 4. item4/Red 5.<br>item5/Yellow”|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 178 | 317 

Firestorm® Web Services API | Version 2.2.33 

|||Each set of questions will be asked one time for each quantity<br>of a product ordered. Each set of answers is separated by a<br>number and a period (i.e.: “1.”). Each question answer is<br>separated by a “/” character.<br>So, in the example above, the customer ordered 5 of this<br>product and there were two questions defined on the<br>product.<br>**Note: This method of storing the answers to product**<br>**questions has been deprecated and will go away in the**<br>**future. For now these fields are being maintained, but there**<br>**is a new system in place that will also store the text of the**<br>**question with the answer.  These records will be available on**<br>**a future release of the web API.**|
|---|---|---|
|EnrollerBonusPaid|Boolean|INTERNAL USE ONLY|
|RetailPrice|Double|Total retailprice for this detail(Qty* Retail)|
|WholesalePrice|Double|Total wholesaleprice for this detail(Qty* Wholesale)|
|PriceOverride|Boolean|Flag to indicate if the price was overridden by administrative<br>personnel<br>0 = Price not overridden<br>Non-zero = Price was overridden to new values|
|DealerID|Integer|DealerID of the member associated with this order. If this is a<br>customer order, then this is the DealerID of the customer’s<br>sponsor.|
|PaymentID|Integer|Unique ID of the payment record for this order<br>tblPayment.PaymentID|
|PaymentType|String|Code representing the type of payment used for the order<br>(VISA,AMEX,etc)|
|PaymentTypeID|Integer|The unique ID representingthe “PaymentType” code|
|WebEmail|String|For shopping cart orders only, this is the email address that is<br>collected duringthe checkoutprocess|
|ShipFirstName|String|For shoppingcart orders only.|
|ShipLastName|String|For shoppingcart orders only.|
|ShipCompanyName|String|For shoppingcart orders only.|
|VAT|Numeric|Amount of VAT tax charged|
|VATShipping|Numeric|Amount of VAT tax charged for shipping|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 179 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.GetOrdersByDealerID 

This web service is intended to be used as a detailed report of order activity for a specific Dealer (Member) in the Firestorm® system. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The DealerID of the member topull orders for|Integer|Anyvalid dealerID|
|StartDate|Y|The start of the date range to pull orders for|Date|Must occur before<br>end date|
|EndDate|Y|The end of the date range to pull orders for|Date|Must occur after start<br>date|
|IncludeFullfilledOrders|Y|Flag to indicate whether or not to include orders<br>that are alreadymarked as fulfilled byFirestorm®|Boolean|0 = Do not include<br>-1 = Include|
|ProductNumber|Y|If provided, the system will only pull orders that<br>contain the specified product number.<br>**Note: If you do not want to use this filter, simply**<br>**pass in an empty string (“”)**|String|Any valid product<br>number define in<br>Firestorm®|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This web service will return all information regarding any order placed that falls within the parameters provided for the DealerID provided. The output of this service can be LARGE, and your system must be prepared to deal with it’s output. 

The web service will output 1 line for each detail item on an order. This means that the order header information is repeated on each line, with the detail information being different. 

##### <u>Output not filtered</u> 

The information retuned by the web service does not filter out voided orders, and will include orders that are already fulfilled unless you specifically tell it not to. It is up to you to perform all additional processing necessary to do this type of filtering as required. 

Customer orders for this member can be identified by the presence of a “CustomerDealerID” greater than zero 

##### **<u>Return Values</u>** 

|Returned Data<br>Field Name|SQL Datatype|Comments|
|---|---|---|
|ProductNumber|String|Product number from catalog|
|ProductID|Integer|Unique ID for theproduct number|
|OrderID|Integer|Unique ID from the order|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 180 | 317 

Firestorm® Web Services API | Version 2.2.33 

|Account|String|Internal account number|
|---|---|---|
|ShipperID|Integer|Unique ID from tblShipper. Correlates to the shipper selected<br>for this order.|
|SubAccount|String|Internal sub account number|
|DealershipID|Integer|Unique ID for the dealership associated with this order. If this<br>is a member order, this is their own dealershipID. If thisis a<br>customer order,this value is their sponsor’s dealershipID.|
|ShipTo|String|Theperson this order is shippingto.|
|ShipAddress1<br>ShipAddress2<br>|String<br>String<br>||
|ShipCity|String||
|ShipState|String||
|ShipZip|String||
|ShipCountry <br>UCFirstName|String<br>String|Unicode enabled|
|UCLastName|String|Unicode enabled<br>|
|UCCompanyName|String|Unicode enabled|
|UCShipAddress1|String|Unicode enabled|
|UCShipAddress2|String|Unicode enabled|
|UCShipCity|String|Unicode enabled|
|UCShipState|String|Unicode enabled|
|UCShipZip|String|Unicode enabled|
|UCShipCountry|String|Unicode enabled|
|Phone|String|Phone number for the person receiving this order (no<br>formattingapplied bythe system)|
|OrderDate|Date|Date this order was placed. (Note: This date may be<br>overridden in Firestorm®. People routinely backdate an order<br>to get it within a specific commission period. Use field<br>“OrderCreateDate” to see the date and time the order was<br>actuallycreated)|
|OrderFulFillDate|Date|Date that this order was fulfilled in Firestorm®.|
|Shipping|Double|Total shippingcharges for the order|
|Tax|Double|Total sales tax collected for this order|
|PrintDate|Date|Date the order wasprinted from within Firestorm®|
|RecurringFreq|integer|A number representing the number of “RecurringUnit” that<br>were used to control this recurring order. This value is only<br>populated if this live order was generated from a recurring<br>order template.|
|RecurringUnit|String|“DAYS”, “WEEKS” or “MONTHS”. This value is only populated<br>if this live order was generated from a recurring order<br>template.|
|RecurringLastOrderDate|Date|The LAST time the “RecurringParentOrderID” was use dto<br>generate an order. This value is only populated if this live<br>order wasgenerated from a recurringorder template.|
|RecurringParentOrderID|Integer|The unique ID of the recurring order template that was used<br>to generate this actual order. This value is only populated if<br>this live order was generated from a recurring order template.<br>**Note: If this field is populated with the value 88888888 or**<br>**99999999, then this order was manually flagged to count as**<br>**a recurring order (usually for qualification purposes)**|
|VoidedOrder|Boolean|Flag to indicate that this order has been voided.<br>0 = not voided<br>Non-zero = voided|
|OrderVoidReason|String|<br>Why this order was voided. Only populated on voided orders<br>that were voided in Firestorm®|
|SpecialInstructions|String|Special instructions that were entered by the person placing<br>the order. (Typically these are special delivery instructions<br>entered by the purchaser through the shopping cart. These<br>will print on the shipping order when printed through<br>Firestorm®)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 181 | 317 

Firestorm® Web Services API | Version 2.2.33 

|Wholesale|Boolean|Flag to indicate that this is a wholesale order|
|---|---|---|
|||0 = Retail order<br>Non-zero = wholesale order|
|ReferringDealerID|Integer|The dealer ID of thememberwho referred the purchaser.<br>Only populated on customer orders.|
|ReferringDealershipID|Integer|The dealership ID of thememberwho referred the purchaser.<br>Only populated on customer orders.|
|ReadyToPrint|Boolean|Flag to indicate that this order is ready to print|
|||0 = Already printed|
|||non-zero = Readytoprint|
|Other|Double|Total other fees that were collected (configured in Firestorm®.<br>This field is used for such things as processing fees, general<br>fees,,etc)|
|CatalogueID|Integer|The unique ID for the catalogused for this order|
|BillFirstName<br>|String<br>||
|BillLastname<br>|String<br>||
|BillAddress1<br>BillAddress2|String<br>String||
|BillCity|String||
|BillState|String||
|BillZip|String||
|BillCountry|String||
|RecurringDay|Integer|1 – 31. The day of the month that this recurring order is set up<br>to generate on. This value is only populated if this live order<br>wasgenerated from a recurringorder template.|
|OrderCreateDate|Date|Actual date and time that this order was created in the<br>database. (This date cannot be overridden by the user. Do not<br>use this date to control anything! Use “OrderDate” instead.)|
|RecurringBatchID|Integer|When this order was created as part of a recurring order<br>batch, this is the unique ID of that batch. This value is only<br>populated if this live order was generated from a recurring<br>order template.|
|PrintBatchID|Integer|When this order was printed as part of a batch or orders that<br>were allprinted at once,this is the unique ID of that batch.|
|OrderCreateBy|String|The login ID of the person who created the order. If this order<br>was created by a web shopping cart user, this field will<br>contain a value such as “WEB:813604” where the number<br>portion is the DealerID of the member/customer who placed<br>|
|||the order.|
|OrderMaintDate|Date|The date and time the order was edited in Firestorm®|
|OrderMaintBy|String|The login ID of the user whoperformed the edit|
|CustomerDealerID|Integer|If this is a customer order, then this is the DealerID associated<br>with the customer whoplaced the order.|
|NonProductPointsUsed|Double|If points were used to pay for any non-product charges (tax,<br>shipping,etc)this is the numberpoints used for thatpurpose.|
|PointValue|Double|The number ofpoints earned bythepurchase of thisproduct|
|PointBreakage|Double|If point rounding is in use (configured in the point system in<br>Firestorm®) then this is the number of points that were<br>considered as breakage to the company|
|OrderStatusID|Integer|The unique of the status code that represents the current<br>status of this order. tblOrderStatus.OrderStatusID|
|WebOrder|Boolean|Flag to indicate that this order was placed through the web<br>shoppingcart|
|TotalOrderDiscount|Double|<br>Total discount(in dollars)that wasgiven on this order|
|ParentOrderID|Integer|DO NOT USE. Custom Process Use Only|
|PartyID|Integer|The unique ID of the party that this order is credited to. This<br>value will onlybepresent on apartyorder.|
|PartyGuestID|Integer|The unique ID of the party guest that is making the purchase.<br>(Note: Remember thatparty guests DO NOT have a dealerID)|
|SoldTo|String|<br>The full name of theperson makingthepurchase|
|ShipToHost|Boolean|Flag indicating the this order is shipping to the party host|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 182 | 317 

Firestorm® Web Services API | Version 2.2.33 

|||Non-zero = ship to the host<br>0 = not shippingdirectlyto thepartyhost|
|---|---|---|
|ShipToGuest|Boolean|<br>Flag indicating the this order is shipping directly to the party<br>guest (drop ship)|
|||Non-zero = ship to the gues<br>0 = not shippingdirectlyto theguest|
|ShipToDealer|Boolean|Flag indicating the this order is shipping directly to the<br>member who sponsored the host.|
|||Non-zero = ship to the dealer|
|||0 = not shippingdirectlyto the dealer|
|PartyShipTo|String|The name of the person the party order is shipping to (this<br>could be thepartyhost,the member or theguest|
|PartyShipAddress1|String|The address that the party order will ship to.|
|||**Note: This address could be the party host, member or guest**<br>**address depending on how the system is configured.**|
|PartyShipAddress2|String|“|
|PartyShipCity|String|“|
|PartyShipState<br>PartyShipZip|String<br>String|“<br>“|
|PartyShipCountry|String|“|
|PartyHostOrder|Boolean|Flag indicating that this is the party host award order.<br>0 = Not the host award order for the party<br>non-zero = This IS the host award order|
|PartyShipPhone|string|The phone number of the person that this party order is<br>hiit|
|PartyBulkOrder|Boolean|sppngo<br>LEGACY – DO NOT USE|
|OrderTypeID|Integer|The unique ID of the order type code.<br>tblOrderType.OrderTypeID|
|DateExported|Date|The date that this order was exported to a third party system.<br>Do not use this field unless you have been specifically told to<br>do so.  It is only populated bycustomprocesses.|
|TotalOrderDiscountPercentage|Double|The total discount applied to this order expressed as a<br>percentage. Will be between 0 and 1. (i.e.: a 10% discount<br>would be listed as .10)|
|AmountPaidByCommissions|Double|If commissions were used to pay for part or all of this order,<br>this is the total amount that was used.|
|LinkedParentOrderID|Integer|If this is a linked order, this is the OrderID in the system that<br>the current order is linked to. (The RMA system will link a<br>replacement order to the original order. The administrative<br>interface in Firestorm® also allows the customer service rep to<br>link two orders together for anyreason)|
|DealershipTypeCode|String|The code representing the members current Pay Rank when<br>the order wasplaced. tblDealershipType.Code|
|OrderDetailID|Integer|The unique ID for the order detail line this record represents|
|Qty|Integer|Thequantityof theproductpurchased|
|QtyFullfilled|Integer|The quantity of the product that was fulfilled. (For fulfilled<br>orders only)|
|BackorderedQty|Integer|<br>If the order detail could not be completely fulfilled because of<br>a backorder situation, this number represents the number of<br>items that are currentlyon backorder|
|VoidedOrderDetail|Boolean|Flag to indicate if this order detail was voided.<br>0 = Not voided|
|||non-zero = voided|
|OrderDetailVoidReason|String|<br>If the detail is voided, this is the comment that was entered<br>bythe administrator|
|PriceEach|Double|<br>Price paid for each product (could be retail or wholesale<br>depending on how the system is configured). This number<br>does NOT takequantityinto account.|
|Discount|Double|<br>Discount applied to this item|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 183 | 317 

Firestorm® Web Services API | Version 2.2.33 

|LineTotal|Double|(Pricepaid *Quantity)- Discount|
|---|---|---|
|WeightLbs|Double|Total weight of this product in pounds.|
|||**Note**: When the system calculates total weight, quantity<br>ordered is multiplied by the configured weight for each item.<br>The system then breaks up tot total weight in pounds and<br>ounces andplaces the result into these fields.|
|WeightOzs|Double|Total weight of this product in ounces.   (see note under<br>“WeightLBS”|
|OrderDetailFulFillDate|Date|The date and time this item was fullfilled|
|FullfilledBy<br>|String<br>|The login ID of theperson who fulfilled the order<br>|
|FullfillComments|String|Comments entered bytheperson who fulfilled the order|
|UplineVolume<br>|Double<br>|Total Upline volume for the order detail(Quantity* upline)<br>f*|
|PSVAmount|Double|Total PSV or the order detail(PSV  upline)|
|NewStagedQty|Integer|INTERNAL USE ONLY|
|SponsorBonus|Double|INTERNAL USE ONLY|
|CountsAsXUnits|Integer|For system that sell product by the box, but need to know<br>how many units were in the box, this number represents the<br>total number of individual units that were in the box that was<br>sold. (i.e.: A case of water contains 24 bottles. This field would<br>be set to 24)|
|LevelCommissionsPaid|Boolean|INTERNAL USE ONLY|
|SponsorBonusProcedureName|<br>String|INTERNAL USE ONLY|
|SponsorBonusClassName|String|INTERNAL USE ONLY|
|<br>SponsorBonusPaid|Boolean|<br>INTERNAL USE ONLY|
|ProductBonusPaid|Boolean|INTERNAL USE ONLY|
|VolumePushDate|Date|INTERNAL USE ONLY|
|UnilevelVolumePushDate|Date|INTERNAL USE ONLY|
|BonusPayoutPending|Boolean|INTERNAL USE ONLY|
|PointsUsed|Double|If points were used to purchase this product, this is the<br>number ofpoints that were applied|
|PointsEarned|Double|If points are awarded for purchasing this product, then this is<br>the number ofproductpoints awarded.|
|PayWithPoints|Boolean|Flag to indicate that this detail item was paid for with points<br>0 = was not paid for with points|
|||non-zero = Waspaid for withpoints|
|CataloguePriceInPoints|Double|<br>The configuredprice inpoints for this item|
|AccumulatorNumber|Integer|INTERNAL USE ONLY|
|IsFreeProduct|Boolean|Flag to indicate that this product was added to the order as a<br>freeproduct.(i.e.: An award)|
|CodingBonusPaid|Boolean|INTERNAL USE ONLY|
|CodingBonusPayoutPending|Boolean|INTERNAL USE ONLY|
|FreeShipping|Boolean|Flag to indicate that this item should not be included in<br>calculating shipping charges|
|||0 = Include this item in chipping calculations<br>non-zero = Do not include this item in shippingcalculations|
|SaleComment|String|If this item was on sale, this comment will contain the name<br>of the sale as entered in Firestorm®|
|QuestionAnswers|String|If this product was configured to ask questions when it is<br>purchased, this is a special delimited string containing the<br>answers to those questions. The string will be formatted as<br>follows:<br>“1. item1/Blue 2. item2/Yellow 3. item3/Red 4. item4/Red 5.<br>item5/Yellow”<br>Each set of questions will be asked one time for each quantity<br>of a product ordered. Each set of answers is separated by a<br>number and a period (i.e.: “1.”). Each question answer is<br>separated by a “/” character.|
|||So,in the example above,the customer ordered 5 of this|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 184 | 317 

Firestorm® Web Services API | Version 2.2.33 

|||product and there were two questions defined on the<br>product.<br>**Note: This method of storing the answers to product**<br>**questions has been deprecated and will go away in the**<br>**future. For now these fields are being maintained, but there**<br>**is a new system in place that will also store the text of the**<br>**question with the answer.  These records will be available on**<br>**a future release of the web API.**|
|---|---|---|
|EnrollerBonusPaid|Boolean|INTERNAL USE ONLY|
|RetailPrice|Double|Total retailprice for this detail(Qty* Retail)|
|WholesalePrice|Double|Total wholesaleprice for this detail(Qty* Wholesale)|
|PriceOverride|Boolean|Flag to indicate if the price was overridden by administrative<br>personnel<br>0 = Price not overridden<br>Non-zero = Price was overridden to new values|
|DealerID|Integer|DealerID of the member associated with this order. If this is a<br>customer order, then this is the DealerID of the customer’s<br>sponsor.|
|PaymentID|Integer|Unique ID of the payment record for this order<br>tblPayment.PaymentID|
|PaymentType|String|Code representing the type of payment used for the order<br>(VISA,AMEX,etc)|
|PaymentTypeID|Integer|The unique ID representingthe “PaymentType” code|
|WebEmail|String|For shopping cart orders only, this is the email address that is<br>collected duringthe checkoutprocess|
|ShipFirstName|String|For shoppingcart orders only.|
|ShipLastName|String|For shoppingcart orders only.|
|ShipCompanyName|String|For shoppingcart orders only.|
|VAT|Numeric|Amount of VAT tax charged|
|VATShipping|Numeric|Amount of VAT tax charged for shipping|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 185 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.GetOrderDetail 

This web service is intended to be used the line item details of an order that exists in the Firestorm system. 

|Method Definition<br>Argument|Required|Description|Datatype|Valid Values|
|---|---|---|---|---|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|OrderID|Y|The Firestorm Order ID topull the detail for|Integer||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This web service will return all information regarding the passed in Order ID. The output of this service is LARGE, and your system must be prepared to deal with its output. 

The web service will output 1 line for each detail item on an order. This means that the order header information is repeated on each line, with the detail information being different. 

Please note that the data delivered by this web service is basically a “report” of the requested order in the system. **<u>No action is taken against the orders pulled</u>** <u>. If you are using this web service as a pull from a fulfillment</u> center, YOU MUST TAKE FURTHER ACTION to ensure that the orders are marked as fulfilled properly in Firestorm®. 

Additionally, this method will return the last 4 digits of the credit card number that was used to pay for the order, if it exists in the data. If it does not, the relevant credit card number field below will be blank. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ProductNumber|String|Product number from catalog|
|ProductID|Integer|Unique ID for theproduct number|
|OrderID|Integer|Unique ID from the order|
|Account|String|Internal account number|
|ShipperID|Integer|Unique ID from tblShipper. Correlates to the shipper selected<br>for this order.|
|SubAccount|String|Internal sub account number|
|DealershipID|Integer|Unique ID for the dealership associated with this order. If this<br>is a member order, this is their own dealershipID. If this is a<br>customer order,this value is their sponsor’s dealershipID.|
|ShipTo|String|Theperson this order is shippingto.|
|ShipAddress1|String||
|ShipAddress2|String||
|ShipCity|String||
|ShipState|String||
|ShipZip|String||



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 186 | 317 

Firestorm® Web Services API | Version 2.2.33 

|ShipCountry <br>UCFirstName|String<br>String|Unicode enabled|
|---|---|---|
|<br>UCLastName|<br>String|<br>Unicode enabled|
|UCCompanyName|String|Unicode enabled|
|UCShipAddress1|String|Unicode enabled|
|UCShipAddress2|String|Unicode enabled|
|UCShipCity|String|Unicode enabled|
|UCShipState|String|Unicode enabled|
|UCShipZip|String|Unicode enabled|
|UCShipCountry|String|Unicode enabled|
|Phone|String|Phone number for the person receiving this order (no<br>formattingapplied bythe system)|
|OrderDate|Date|Date this order was placed. (Note: This date may be<br>overridden in Firestorm®. People routinely backdate an order<br>to get it within a specific commission period. Use field<br>“OrderCreateDate” to see the date and time the order was<br>actuallycreated)|
|OrderFulFillDate|Date|Date that this order was fulfilled in Firestorm®.|
|Shipping|Double|Total shippingcharges for the order|
|Tax|Double|Total sales tax collected for this order|
|PrintDate|Date|Date the order wasprinted from within Firestorm®|
|RecurringFreq|integer|A number representing the number of “RecurringUnit” that<br>were used to control this recurring order. This value is only<br>populated if this live order was generated from a recurring<br>order template.|
|RecurringUnit|String|“DAYS”, “WEEKS” or “MONTHS”. This value is only populated<br>if this live order was generated from a recurring order<br>template.|
|RecurringLastOrderDate|Date|The LAST time the “RecurringParentOrderID” was used to<br>generate an order. This value is only populated if this live<br>order wasgenerated from a recurringorder template.|
|RecurringParentOrderID|Integer|The unique ID of the recurring order template that was used<br>to generate this actual order. This value is only populated if<br>this live order was generated from a recurring order template.|
|||**Note: If this field is populated with the value 88888888 or**<br>**99999999, then this order was manually flagged to count as**<br>**a recurring order (usually for qualification purposes)**|
|VoidedOrder|Boolean|Flag to indicate that this order has been voided.<br>0 = not voided<br>Non-zero = voided|
|OrderVoidReason|String|<br>Why this order was voided. Only populated on voided orders<br>that were voided in Firestorm®|
|SpecialInstructions|String|Special instructions that were entered by the person placing<br>the order. (Typically these are special delivery instructions<br>entered by the purchaser through the shopping cart. These<br>will print on the shipping order when printed through<br>Firestorm®)|
|Wholesale|Boolean|Flag to indicate that this is a wholesale order<br>0 = Retail order|
|||Non-zero = wholesale order|
|ReferringDealerID|Integer|<br>The dealer ID of thememberwho referred the purchaser.<br>Only populated on customer orders.|
|ReferringDealershipID|Integer|The dealership ID of thememberwho referred the purchaser.<br>Only populated on customer orders.|
|ReadyToPrint|Boolean|Flag to indicate that this order is ready to print<br>0 = Already printed<br>non-zero = Readytoprint|
|Other|Double|Total other fees that were collected (configured in Firestorm®.<br>This field is used for such things as VAT tax,etc)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 187 | 317 

Firestorm® Web Services API | Version 2.2.33 

|CatalogueID<br>BillFirstName|Integer<br>String|The unique ID for the catalogused for this order|
|---|---|---|
|<br>BillLastname|<br>String||
|BillAddress1<br>|String<br>||
|BillAddress2<br>BillCity|String<br>String||
|BillState|String||
|BillZip|String||
|BillCountry|String||
|RecurringDay|Integer|1 – 31. The day of the month that this recurring order is set up<br>to generate on. This value is only populated if this live order<br>wasgenerated from a recurringorder template.|
|OrderCreateDate|Date|Actual date and time that this order was created in the<br>database. (This date cannot be overridden by the user. Do not<br>use this date to control anything! Use “OrderDate” instead.)|
|RecurringBatchID|Integer|When this order was created as part of a recurring order<br>batch, this is the unique ID of that batch. This value is only<br>populated if this live order was generated from a recurring<br>order template.|
|PrintBatchID|Integer|When this order was printed as part of a batch or orders that<br>were allprinted at once,this is the unique ID of that batch.|
|OrderCreateBy|String|The login ID of the person who created the order. If this order<br>was created by a web shopping cart user, this field will<br>contain a value such as “WEB:813604” where the number<br>portion is the DealerID of the member/customer who placed<br>the order.|
|OrderMaintDate|Date|The date and time the order was edited in Firestorm®|
|OrderMaintBy|String|The login ID of the user whoperformed the edit|
|CustomerDealerID|Integer|If this is a customer order, then this is the DealerID associated<br>with the customer whoplaced the order.|
|NonProductPointsUsed|Double|If points were used to pay for any non-product charges (tax,<br>shipping,etc)this is the numberpoints used for thatpurpose.|
|PointValue|Double|The number ofpoints earned bythepurchase of thisproduct|
|PointBreakage|Double|If point rounding is in use (configured in the point system in<br>Firestorm®) then this is the number of points that were<br>considered as breakage to the company|
|OrderStatusID|Integer|The unique of the status code that represents the current<br>status of this order. tblOrderStatus.OrderStatusID|
|WebOrder|Boolean|Flag to indicate that this order was placed through the web<br>shoppingcart|
|TotalOrderDiscount|Double|Total discount(in dollars)that wasgiven on this order|
|ParentOrderID|Integer|DO NOT USE. Custom Process Use Only|
|PartyID|Integer|The unique ID of the party that this order is credited to. This<br>value will onlybepresent on apartyorder.|
|PartyGuestID|Integer|The unique ID of the party guest that is making the purchase.<br>(Note: Remember thatpartyguests DO NOT have a dealerID)|
|SoldTo|String|<br>The full name of theperson makingthepurchase|
|ShipToHost|Boolean|Flag indicating the this order is shipping to the party host<br>Non-zero = ship to the host|
|||0 = not shippingdirectlyto thepartyhost|
|ShipToGuest|Boolean|Flag indicating the this order is shipping directly to the party<br>guest (drop ship)|
|||Non-zero = ship to the gues|
|||<br>0 = not shippingdirectlyto theguest|
|ShipToDealer|Boolean|Flag indicating the this order is shipping directly to the<br>member who sponsored the host.|
|||Non-zero = ship to the dealer<br>0 = not shippingdirectlyto the dealer|
|PartyShipTo|String|The name of the person the party order is shipping to (this|
|||<br>could be thepartyhost,the member or theguest|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 188 | 317 

Firestorm® Web Services API | Version 2.2.33 

|PartyShipAddress1|String|The address that the party order will ship to.|
|---|---|---|
|||**Note: This address could be the party host, member or guest**<br>**address depending on how the system is configured.**|
|PartyShipAddress2<br>|String<br>|“<br>“|
|PartyShipCity|String||
|PartyShipState|String|“|
|PartyShipZip|String|“|
|PartyShipCountry|String|“|
|PartyHostOrder|Boolean|Flag indicating that this is the party host award order.|
|||0 = Not the host award order for the party<br>non-zero = This IS the host award order|
|PartyShipPhone|string|The phone number of the person that this party order is<br>shippingto|
|PartyBulkOrder|Boolean|LEGACY – DO NOT USE|
|OrderTypeID|Integer|The unique ID of the order type code.<br>tblOrderType.OrderTypeID|
|DateExported|Date|The date that this order was exported to a third party system.<br>Do not use this field unless you have been specifically told to<br>do so.  It is only populated bycustomprocesses.|
|TotalOrderDiscountPercentage|Double|The total discount applied to this order expressed as a<br>percentage. Will be between 0 and 1. (i.e.: a 10% discount<br>would be listed as .10)|
|AmountPaidByCommissions|Double|If commissions were used to pay for part or all of this order,<br>this is the total amount that was used.|
|LinkedParentOrderID|Integer|If this is a linked order, this is the OrderID in the system that<br>the current order is linked to. (The RMA system will link a<br>replacement order to the original order. The administrative<br>interface in Firestorm® also allows the customer service rep to<br>link two orders together for anyreason)|
|DealershipTypeCode|String|The code representing the members current Pay Rank when<br>the order wasplaced. tblDealershipType.Code|
|OrderDetailID|Integer|The unique ID for the order detail line this record represents|
|Qty|Integer|Thequantityof theproductpurchased|
|QtyFullfilled|Integer|The quantity of the product that was fulfilled. (For fulfilled<br>orders only)|
|BackorderedQty|Integer|If the order detail could not be completely fulfilled because of<br>a backorder situation, this number represents the number of<br>items that are currentlyon backorder|
|VoidedOrderDetail|Boolean|Flag to indicate if this order detail was voided.|
|||0 = Not voided<br>non-zero = voided|
|OrderDetailVoidReason|String|If the detail is voided, this is the comment that was entered<br>bythe administrator|
|PriceEach|Double|Price paid for each product (could be retail or wholesale<br>depending on how the system is configured). This number<br>does NOT takequantityinto account.|
|Discount|Double|Discount applied to this item|
|LineTotal|Double|(Pricepaid *Quantity)- Discount|
|WeightLbs|Double|Total weight of this product in pounds.|
|||**Note**: When the system calculates total weight, quantity<br>ordered is multiplied by the configured weight for each item.<br>The system then breaks up tot total weight in pounds and<br>ounces andplaces the result into these fields.|
|WeightOzs|Double|Total weight of this product in ounces.   (see note under<br>“WeightLBS”|
|OrderDetailFulFillDate|Date|The date and time this item was fullfilled|
|<br>FullfilledBy|String|<br>The login ID of theperson who fulfilled the order|
|FullfillComments|String|Comments entered bytheperson who fulfilled the order|
|UplineVolume|Double|Total Upline volume for the order detail(Quantity* upline)|
|<br>PSVAmount|Double|<br>Total PSV for the order detail(PSV * upline)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 189 | 317 

Firestorm® Web Services API | Version 2.2.33 

|NewStagedQty<br>SponsorBonus|Integer<br>Double|INTERNAL USE ONLY<br>INTERNAL USE ONLY|
|---|---|---|
|CountsAsXUnits|Integer|For system that sell product by the box, but need to know<br>how many units were in the box, this number represents the<br>total number of individual units that were in the box that was<br>sold. (i.e.: A case of water contains 24 bottles. This field would<br>be set to 24)|
|LevelCommissionsPaid<br>|Boolean<br>|INTERNAL USE ONLY|
|SponsorBonusProcedureName|<br>String|INTERNAL USE ONLY|
|SponsorBonusClassName|String|INTERNAL USE ONLY|
|SponsorBonusPaid|Boolean|INTERNAL USE ONLY|
|ProductBonusPaid|Boolean|INTERNAL USE ONLY|
|VolumePushDate<br>|Date<br>|INTERNAL USE ONLY<br>|
|UnilevelVolumePushDate<br>BonusPayoutPending|Date<br>Boolean|INTERNAL USE ONLY<br>INTERNAL USE ONLY|
|PointsUsed|Double|If points were used to purchase this product, this is the<br>number ofpoints that were applied|
|PointsEarned|Double|If points are awarded for purchasing this product, then this is<br>the number ofproductpoints awarded.|
|PayWithPoints|Boolean|Flag to indicate that this detail item was paid for with points|
|||0 = was not paid for with points<br>non-zero = Waspaid for withpoints|
|CataloguePriceInPoints|Double|The configuredprice inpoints for this item|
|AccumulatorNumber|Integer|INTERNAL USE ONLY|
|IsFreeProduct|Boolean|Flag to indicate that this product was added to the order as a<br>freeproduct.(i.e.: An award)|
|CodingBonusPaid|Boolean|INTERNAL USE ONLY|
|CodingBonusPayoutPending|Boolean|INTERNAL USE ONLY|
|FreeShipping|Boolean|Flag to indicate that this item should not be included in<br>calculating shipping charges<br>0 = Include this item in chipping calculations<br>|
|||non-zero = Do not include this item in shippingcalculations|
|SaleComment|String|If this item was on sale, this comment will contain the name<br>of the sale as entered in Firestorm®|
|QuestionAnswers|String|If this product was configured to ask questions when it is<br>purchased, this is a special delimited string containing the<br>answers to those questions. The string will be formatted as<br>follows:<br>“1. item1/Blue 2. item2/Yellow 3. item3/Red 4. item4/Red 5.<br>item5/Yellow”<br>Each set of questions will be asked one time for each quantity<br>of a product ordered. Each set of answers is separated by a<br>number and a period (i.e.: “1.”). Each question answer is<br>separated by a “/” character.|
|||So, in the example above, the customer ordered 5 of this<br>product and there were two questions defined on the<br>product.<br>**Note: This method of storing the answers to product**<br>**questions has been deprecated and will go away in the**<br>**future. For now these fields are being maintained, but there**<br>**is a new system in place that will also store the text of the**<br>**question with the answer.  These records will be available on**<br>**a future release of the web API.**|
|EnrollerBonusPaid|Boolean|INTERNAL USE ONLY|
|<br>RetailPrice|Double|<br>Total retailprice for this detail(Qty* Retail)|
|WholesalePrice|Double|Total wholesaleprice for this detail(Qty* Wholesale)|
|PriceOverride|Boolean|Flag to indicate if the price was overridden by administrative<br>personnel|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 190 | 317 

Firestorm® Web Services API | Version 2.2.33 

|||0 = Price not overridden<br>Non-zero = Price was overridden to new values|
|---|---|---|
|DealerID|Integer|DealerID of the member associated with this order. If this is a<br>customer order, then this is the DealerID of the customer’s<br>sponsor.|
|PaymentID|Integer|Unique ID of the payment record for this order<br>tblPayment.PaymentID|
|PaymentType|String|Code representing the type of payment used for the order<br>(VISA,AMEX,etc)|
|PaymentTypeID|Integer|The unique ID representingthe “PaymentType” code|
|WebEmail|String|For shopping cart orders only, this is the email address that is<br>collected duringthe checkoutprocess|
|ShipFirstName|String|For shoppingcart orders only.|
|ShipLastName|String|For shoppingcart orders only.|
|ShipCompanyName|String|For shoppingcart orders only.|
|VAT|Numeric|Amount of VAT tax charged|
|VATShipping|Numeric|Amount of VAT tax charged for shipping|
|WebName|String|Web Display Name of the Product purchased on the current<br>line item.|
|CCLast4|String|Last 4 digits of the credit card used to pay for the order. Will<br>be blank if on Consultant Pay party orders, multi credit card<br>orders, and orders where a credit card was not used to pay<br>for the order.|
|RealTimeConversionRatio|Numeric|The currency conversion ratio that was used for this order, if<br>any.|
|CustomerName|String|The full name of the purchasing customer. Will only be<br>populated on retail catalogue orders.|
|ReferrerName|String|The full name of the referringdealer of the order.|
|UnilevelPlacementDealerID|Integer|The Unilevel Placement Dealer ID of the consultant attached<br>to the order. This will be the immediate upline consultant in<br>thephysicalplacement tree.|
|UnilevelPlacementDealershipID|Integer|The Unilevel Placement Dealership ID of the consultant<br>attached to the order. This will be the immediate upline<br>consultant in thephysicalplacement tree.|
|UnilevelPlacementDealerName|String|The full name of the immediate upline consultant in the<br>physicalplacement tree.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 191 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.PayForOrderWithCommissions 

Allows an order to be paid for with a member’s unpaid commissions from their commission account. The member must have adequate funds to pay for the entire order. No partial payments are allowed through this web service. 

**WARNING** : This web service is provided for legacy support only and **has been deprecated** . If you need to pay for an order with commissions, you should be using FirestormOrderWS.SaveOrderExtended() 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|TotalAmount|Y|The total amount of commissions to capture as<br>payment for an order|Double|Must be > 0|
|ForOrderID|Y|The OrderID to capture funds for|||
|FromDealerID|Y||||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This web service is provided as a way to capture payment for an order by removing funds from a Dealer’s unpaid commission account and placing them on a special check type and flagging that check as the payout for the order in questions. 

In order for this web service to be used, the order must already exist in the system. The actual commissions capture will occur AFTER the order is created. The basic flow for using this service correctly would be as follows: 

1. Create the order in the system using a “CASH” payment type (or one created specifically for this purpose) 

2. Call this web service to capture commissions in the amount equal to the amount of the order 

3. If this web service call fails, you must perform the following steps: a) Void the order, b) Make sure the commissions are placed back in the Dealer’s account. 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS,this node will contain the new OrderID created bythe system.|
|ERROR|string||a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 192 | 317 

Firestorm® Web Services API | Version 2.2.33 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 193 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.PostTrackingNumber 

Allows a remote system to post a tracking number to an order that is stored in the Firestorm® system. Typically used by 3<sup>rd</sup> party shipping software to be able to post a generated tracking number into the system 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|OrderID|Y|The ID of the order you are posting a tracking<br>number to|integer|Any existing order ID<br>in Firestorm®|
|ShipperID|Y|The unique ID of the shipper that this tracking<br>number is for|integer|Any valid shipperID as<br>defined in Firestorm®<br>(tblShipper.ShipperID)|
|TrackingNumber|Y|The actual tracking number|string|As supplied by the<br>shipper|
|ShipDate|Y|The date thepackage was shipped to the customer|Date|Anyvalid date|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This web service is intended to post a single tracking number to an order. If you need to post multiple tracking numbers to a single order, you may make multiple calls to this service for the same OrderID. 

If you need to perform a batch upload of many tracking numbers at once, please see the web service “FirestormOrderWS.PostMultipleTrackingNumbers” 

##### **<u>Return Values</u>** 

##### BOOLEAN 

True if the tracking number was posted successfully False if an error occurred. (to see the specific error, you will need to consult the logs on our server) 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 194 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.PostTrackingNumberWithEmail 

Allows a remote system to post a tracking number to an order that is stored in the Firestorm® system and also causes a special tracking number email to be sent to the purchaser. Typically used by 3<sup>rd</sup> party shipping software to be able to post a generated tracking number into the system 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|OrderID|Y|The ID of the order you are posting a tracking<br>number to|integer|Any existing order ID<br>in Firestorm®|
|ShipperID|Y|The unique ID of the shipper that this tracking<br>number is for|integer|Any valid shipperID as<br>defined in Firestorm®<br>(tblShipper.ShipperID)|
|TrackingNumber|Y|The actual tracking number|string|As supplied by the<br>shipper|
|ShipDate|Y|The date thepackage was shipped to the customer|Date|Anyvalid date|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This web service is intended to post a single tracking number to an order. If you need to post multiple tracking numbers to a single order, you may make multiple calls to this service for the same OrderID. 

If you need to perform a batch upload of many tracking numbers at once, please see the web service “FirestormOrderWS.PostMultipleTrackingNumbers” (this services does NOT support sending emails at this time) 

The email is defined on the shipper screen in the Firestorm® administrative console. The specific email that will be sent is the one defined for the shipper (ShipperID) passed into this web service. 

##### **<u>Return Values</u>** 

##### BOOLEAN 

True if the tracking number was posted successfully and the email was sent. False if an error occurred. (to see the specific error, you will need to consult the logs on our server) 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 195 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.PostMultipleTrackingNumbers 

This web service is intended to allow you to post as many tracking numbers as desired using a single web service call.  This post also has the ability to “auto-fullfill” an order if desired. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|OrderXML|Y|XML document describing each order/tracking<br>number|String|See descriptionbelow|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

##### <u>Entire list is processed</u> 

This service will process the entire list of orders supplied in the XML document, even if one or more of the orders triggers an error. When an error occurs, the resulting error message is reported back to the caller in the returned XML document. 

##### <u>Order XML</u> 

The order XML document that you construct and supply as an argument to this web service will be used to control its behavior. An example document is supplied below: 

```
' Sample XML Document Format
' --------------------------------------------
<?xml version='1.0' encoding='utf-8' ?>
<ORDERLIST count="1">
    <ORDER>
        <ORDERID>integer</ORDERID>
        <SHIPPER>string</SHIPPER>
        <TRACKINGNUMBER>string</TRACKINGNUMBER>
        <SHIPDATE>date</SHIPDATE>
        <AUTOFULLFILL>boolean</AUTOFULLFILL>
    </ORDER>
</ORDERLIST>
```

<mark>The table below defines each node and its purpose, along with formatting requirements as required.</mark> 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|<?xml….|||Header of XML document|
|ORDERLIST||count<br>The total<br>number of<br>“ORDER”|Containing envelope for all ORDER envelopes|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 196 | 317 

Firestorm® Web Services API | Version 2.2.33 

||nodes in the<br>document||
|---|---|---|
|ORDER||Containingenvelope for a single order|
|ORDERID|Integer|The OrderIDpreviously generated byFirestorm|
|SHIPPER|String|The code corresponding to a known shipper in the Firestorm system (UPS, FEDEX,<br>etc..)This code must exist in the shipper table|
|TRACKINGNUMBER|String|The actual trackingnumber of the shipment formattedper the shipper standards|
|SHIPDATE|Date|Format “MM/DD/YYYY”,The date the shipment was shipped|
|AUTOFULLFILL|Boolean|“TRUE” or “FALSE”. Flag to Indicate whether or not this order will be automatically<br>fulfilled in Firestorm. Note thatpartial fulfillments are NOT allowed.|



##### <u>Automatic Fulfillment</u> 

This web service also offers the ability to automatically fulfill the order once the tracking number is posted simply by setting the appropriate flag in the OrderXML document. **_This capability should be used with caution_** , as you are circumventing the normal process of the system. In some cases, this is appropriate to do, but not always. Please call our support department before implementing this to discuss the ramifications of using this feature. 

##### <u>Multiple Tracking Numbers for a Single Shipment</u> 

If you need to post multiple tracking numbers to a single order (i.e.: the order would not fit into a single box) You will need to include a separate ORDER envelope for each tracking number for the order. All elements (Except AUTOFULLFILL) would be the same values with only the tracking number changing between envelopes. If you are using the autofullfill feature, you should only set this value to TRUE on the FIRST order envelope. (Setting AUTOFULLFILL to TRUE on multiple envelopes for the same order will generate an error) 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call for each order.  Please not that this return XML is different from other web service calls. Not specifically that the system will return an ORDER envelope for every order that was passed into this method. A sample document is provided below: 

```
' Return XML
' ---------------------------------------------
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
   <ORDERLIST count="2">
       <ORDER>
           <ORDERID>8132256</ORDERID>
   <TRACKINGNUMBER>1Z8933009837389993</TRACKINGNUMBER>
           <STATUS>SUCCESS</STATUS>
           <ERROR></ERROR>
       </ORDER>
       <ORDER>
           <ORDERID>8132257</ORDERID>
   <TRACKINGNUMBER>1Z87273832872872872</TRACKINGNUMBER>
           <STATUS>FAIL</STATUS>
           <ERROR>Order could not be 197ulfilled</ERROR>
       </ORDER>
   </ORDERLIST>
</FIRESTORMRESULT>
```

The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|<?xml….|||Header of XML document|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 197 | 317 

Firestorm® Web Services API | Version 2.2.33 

|ORDERLIST|string|count<br>Set to the<br>total number<br>of “ORDER”<br>nodes|Containing envelope for list of all orders|
|---|---|---|---|
|ORDER|||Containingenvelope for a single order|
|ORDERID|numeric||The OrderID beingreported|
|TRACKINGNUMBER|String||The tracking number that was sent to this web service for this order. You must<br>remember to check the STATUS node to determine if this tracking number was<br>actually posted to the system. A status of FAIL means the number did notpost.|
|STATUS|String||SUCCESS or FAIL,depending on whether or not the tracking number was posted<br>successfullyand autofullfill(if applicable)was successful.|
|ERROR|String||If status is “FAIL” then this node will contain the error that occurred on this order|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 198 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.PreCalculateOrderTotals 

This web service will allow an order to be sent to the Firestorm® system to have several items calculated by the system for you. These items include Sales Tax, Shipping charges, VAT tax, Country Specific Fees, Discounts and the total amount due on the order. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|OrderXML|Y|XML document describing the order to perform<br>calculations for|String||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

It is necessary to allow Firestorm® to perform these calculations for you, as all of them can be affected by the dozens of configuration options available in each area. By allowing Firestorm® to pre-process the order and perform the necessary calculations for the order based on current system configurations, you will be guaranteed to get consistent results for these calculations every time. 

**WARNING** : If you implement your own calculations in any of these areas, you will run the extreme risk of arriving at different results since system configurations could change without your knowledge which would lead to inconsistent results. 

Make sure you wrap your XML in <CDATA> tags to prevent any parser errors! You must begin your document with “<![CDATA[“ then append your XML document and then append “]]>”. This will prevent the Firestorm® XML parser from getting an error. 

**Uppercase and lowercase matter in XML** . Opening and closing tags must match exactly. For example, `<ROOT>` , `<Root>` , and `<root>` are three different tags 

##### <u>Order XML</u> 

In order to successfully call this web service it will be necessary for you to build out an XML document describing the order to perform calculations against. A sample XML document is provided below: 

```
' ///////////////////////////
```

```
' Sample order XML
```

```
' ///////////////////////////
<![CDATA[
```

```
<?xml version='1.0' encoding='utf-8' ?>
<ORDER itemcount='1'>
<DEALERID>integer</DEALERID>
<CATALOGUEID>integer</CATALOGUEID>
<SHIPPERID>integer</SHIPPERID>
<CURRENCY>string</CURRENCY>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 199 | 317 

Firestorm® Web Services API | Version 2.2.33 

```
<ADDITIONALPOINTS>double</ADDITIONALPOINTS>
<COMMISSIONAMOUNTTOUSE>double</COMMISSIONAMOUNTTOUSE>
<SHIPPINGADDRESS>
```

```
<FIRSTNAME>string</FIRSTNAME>
<LASTNAME>string</LASTNAME>
<COMPANYNAME>string</COMPANYNAME>
<ADDR1>string</ADDR1>
<ADDR2>string</ADDR2>
<CITY>string</CITY>
<STATE>string</STATE>
<POSTALCODE>string</POSTALCODE>
<COUNTRY>string</COUNTRY>
</SHIPPINGADDRESS>
<ORDERDETAIL>
<PRODUCTNUMBER>string</PRODUCTNUMBER>
<PRODUCTQTY>integer</PRODUCTQTY>
<PRICEEACH>double</PRICEEACH>
<RETAILPRICEEACH></RETAILPRICEEACH>
<WHOLESALEPRICEEACH></WHOLESALEPRICEEACH>
<UPLINEVOLUMEEACH></UPLINEVOLUMEEACH>
<PSVAMOUNTEACH></PSVAMOUNTEACH>
<ISFREEPRODUCT>boolean</ISFREEPRODUCT>
<FREESHIPPING>boolean</FREESHIPPING>
</ORDERDETAIL>
```

```
</ORDER>
```

```
]]>
```

The xml document contains the basic information required to perform the necessary calculations on the Firestorm® system for the specific order. The following table describes each node and its requirements: 

|Element|Datatype|Attribute|Definition|
|---|---|---|---|
|<![CDATA[|||OpeningCDATA tag|
|<?xml version='1.0' encoding='utf-8' ?>|||Xml document declaration|
|ORDER||itemcount|Containing envelope for the order.<br>The “itemcount” attribute will contain the total number of<br>ORDERDETAIL elelments that are present in the document. This<br>number mut be accurate or the XML document will be rejected.|
|DEALERID|integer||If this is a member order, this should be set to the DealerID of the<br>member who is placing the order.<br>If this is a retail customer order,set this value to -1|
|CATALOGUEID|integer||The catalogueID of the catalog that this order is being placed against.<br>You must obtain this ID from the Firestorm® system.<br>**TIP**: A list of valid catalogueIDs may be obtained by calling<br>FirestormInventoryWS.GetCatalogueList() and then selecting the<br>correct catalog from the list. You will need to work with the owner of<br>the Firestorm® system to determine the best method for selecting<br>the correct ID.|
|SHIPPERID|integer||The shipperID that will be used to shipthis order.|
|CURRENCY|String||ISO Currency code representing the currency that the calculated<br>results will be**returned**in.<br>**Warning**: Any financial numbers passed in to this method MUST be<br>passed in using the base currency type as defined in Firestorm®.  If<br>you are unsure of the base currencytype, please contact the client.|
|ADDITIONALPOINTS|||If the order is being paid for (completely or partially) with product<br>reward points, this field will contain the number of points to use<br>when calculating payments due on this order.|
|COMMISSIONAMOUNTTOUSE|||If the purchaser is trying to use earned and unpaid commissions to<br>pay for this order (completely or partially), this is the amount of<br>commission to use towards payment.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 200 | 317 

Firestorm® Web Services API | Version 2.2.33 

||||**Warning:**This value must be passed in the base currency of the<br>sstem|
|---|---|---|---|
|SHIPPIN|GADDRESS||y.<br>Containingenvelope for the shippingaddress elements|
||FIRSTNAME||First name<br>|
||LASTNAME<br>||Last Name<br>|
||COMPANYNAME||Companyname|
||ADDR1||Address line 1|
||ADDR2||Address line 2|
||CITY||Cityname|
||STATE||State code – This code must exist in Firestorm®! Verify state codes<br>with the client,as theyare important for sales tax calculations.|
||POSTALCODE||Postal Code(Zipcode)|
||COUNTRY||Country code - This code must exist in Firestorm®! Verify country<br>codes with the client,as theyare important for VAT tax calculations.|
|ORDERD|ETAIL||Containing envelope for a single order detail element. The document<br>may contain 1 to n ORDERDETAIL elements.<br>**Warning:**Make sure the attribute “itemcount” on the ORDER node is<br>set to the total number of ORDERDETAIL elements contained in the<br>document|
||PRODUCTNUMBER|String|Product number that exists in the catalog specified in the web service<br>call|
||PRODUCTQTY|Integer|Quantityof this item to order|
||PRICEEACH|Double|Actual price paid for EACH item (do**not**multiply this by<br>PRODUCTQTY. The system will do that for you).<br>**WARNING: Only set this value if you are NOT providing**<br>**Retail/Wholesale/Upline/PSV. If you set this value it will override**<br>**what is in the RETAILPRICEEACH and WHOLESALEPRICEEACH price**<br>**fields!**<br>**If you are providing explicit pricing using the fields below, set this**<br>**value to $0**|
||||**Warning:**This value must be passed in the base currency of the<br>system.|
||RETAILPRICEEACH|Double|Retail price for each product. Do not multiply by PRODUCTQTY.<br>Setting this value to -1 will cause the system to use the price<br>configured in the catalog.<br>**Warning:**This value must be passed in the base currency of the<br>system.|
||WHOLESALEPRICEEACH|Double|Wholesale price for each product. Do not multiply by PRODUCTQTY.<br>Setting this value to -1 will cause the system to use the price<br>configured in the catalog.|
||||**Warning:**This value must be passed in the base currency of the<br>system.|
||UPLINEVOLUMEEACH|Double|Upline (commissionable) volume for each product. Do not multiply by<br>PRODUCTQTY. Setting this value to -1 will cause the system to use<br>the price configured in the catalog.<br>**Warning:**This value must be passed in the base currency of the<br>system.|
||PSVAMOUNTEACH|Double|PSV Amount for each product. Do not multiply by PRODUCTQTY.<br>Setting this value to -1 will cause the system to use the price<br>configured in the catalog.|
||||**Warning:**This value must be passed in the base currency of the<br>system.|
||ISFREEPRODUCT|Boolean|Flag to indicate if this is a free product. “True” = is a free product,<br>“False” = not a freeproduct|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 201 | 317 

Firestorm® Web Services API | Version 2.2.33 

|<br>FREESHIPPIN|G|Boolean|Flag to indicate if shipping charges should be suppressed for this<br>product. “True” = no shipping will be calculated, “False” = shipping<br>charges will be calculated normally.|
|---|---|---|---|
|]]><br>**Return Values**<br>This web service wi<br>this document alon|ll return a<br>g with def|complex XM<br>initions of e|ClosingCDATA tag<br>L document containing the results of the call. The table below<br>ach node:|
|**Element**|**DataType**|**Attribute**|**Definition**|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the<br>number of errors that occurred during the call, which will coorelate directly to the<br>number of <ERRORMSG> elements that will be present. All argument validation<br>errors will be returned in this manner|
|<br>ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

If no errors are encountered during the processing of the received XML document and the STATUS node is set to SUCCESS, the system will embed a copy of the order into the FIRESTORMRESULT envelope, with nodes added to the document to indicate the calculated values. See the example return xml document below (Nodes in RED are added to the original xml document you passed in): 

|Element|Datatype|Attribute|Definition|
|---|---|---|---|
|ORDER||itemcount|Containing envelope for the order.<br>The “itemcount” attribute will contain the total number of<br>ORDERDETAIL elelments that are present in the document. This<br>number mut be accurate or the XML document will be rejected.|
|DEALERID|integer||If this is a member order, this should be set to the DealerID of the<br>member who is placing the order.|
||||If this is a retail customer order,set this value to -1|
|CATALOGUEID|integer||The catalogueID of the catalogthat this order is being placed against.|
|SHIPPERID|integer||The shipperID that will be used to shipthis order.|
|CURRENCY|String||ISO Currency code representing the currency that the calculated<br>results will be**returned**in.<br>**Be Aware:**This web service will look up the current conversion rates<br>for this currency type, and will apply it to the financial numbers<br>returned in this document.|
|ADDITIONALPOINTS|integer||If the order is being paid for (completely or partially) with product<br>reward points, this field will contain the number of points to use<br>when calculating payments due on this order.|
|COMMISSIONAMOUNTTOUSE|double||If the purchaser is trying to use earned and unpaid commissions to<br>pay for this order (completely or partially), this is the amount of<br>commission to use towardspayment.|
|SALESTAX|Double||Sales tax for the orderper current system configurations|
|VAT|Double||VAT tax (if applicable) for the order. This is the amount of VAT for the<br>entire order.|
|SHIPPING|Double||Shipping charges for the entire order, based on system configrations<br>for the requested ShipperID.|
|COUNTRYSPECIFICFEES|Double||Any country specific fees that are assessed by country currently<br>configured in Firestorm® will be returned here.|
|PRODUCTTOTAL|Double||The total amount due for the products on the order. This value WILL<br>NOT include sales tax or any other fees. This number is product cost<br>only.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 202 | 317 

Firestorm® Web Services API | Version 2.2.33 

|ORDERD|ISCOUNT|Double|The monetaryvalue of anydiscount applied to this order|
|---|---|---|---|
|AFTERDI|SCOUNTPRODUCTTOTAL|Double|ProductTotal minus OrderDiscount|
|ORDERT|OTAL|Double|The total amount of payment due from the shopper for this order.<br>This number is calculated as follows:<br>`OrderTotal = ((AfterDiscountProductTotal) +`<br>`Shipping + CountrySpecificFees + SalesTax + VAT) –`<br>`AdditionalPointsValue`|
|SHIPPIN|GADDRESS||Containingenvelope for the shippingaddress elements|
||FIRSTNAME|string|First name|
||LASTNAME|String|Last Name|
||COMPANYNAME|String|Companyname|
||ADDR1|String|Address line 1|
||ADDR2|String|Address line 2|
||CITY|String|Cityname|
||STATE|String|State code|
||POSTALCODE|String|Postal Code(Zipcode)|
||COUNTRY|String|Countrycode|
|ORDERD|ETAIL||Containing envelope for a single order detail element. The document<br>maycontain 1 to n ORDERDETAIL elements.|
||PRODUCTNUMBER|String|Product number that exists in the catalog specified in the web service<br>call|
||PRODUCTQTY|Integer|Quantityof this item to order|
||PRICEEACH|Double|Actualpricepaid for EACH item|
||RETAILPRICEEACH|Double|Retailprice for eachproduct.|
||WHOLESALEPRICEEACH|Double|Wholesaleprice for eachproduct.|
||UPLINEVOLUMEEACH|Double|Upline(commissionable)volume for eachproduct.|
||PSVAMOUNTEACH|Double|PSV Amount for eachproduct.|
||ISFREEPRODUCT|Boolean|Flag to indicate if this is a free product. “True” = is a free product,<br>“False” = not a freeproduct|
||FREESHIPPING|Boolean|Flag to indicate if shipping charges should be suppressed for this<br>product. “True” = no shipping will be calculated, “False” = shipping<br>charges will be calculated normally.|
||INSTOCK|Boolean|Flag to indicate if the item is in stock and available for purchase.<br>True = In stock<br>False = Out of stock|



See the example SUCCESS return document (with embedded order XML) below: 

```
<FIRESTORMRESULT>
```

```
    <STATUS>SUCCESS</STATUS>
    <ERRORS errorcount='0'></ERRORS>
    <ORDER itemcount='1'>
```

```
        <CATALOGUEID>211</CATALOGUEID>
        <SHIPPERID>62</SHIPPERID>
        <CURRENCY>USD</CURRENCY>
        <ADDITIONALPOINTS>0</ADDITIONALPOINTS>
        <COMMISSIONAMOUNTTOUSE>0</COMMISSIONAMOUNTTOUSE>
        <SALESTAX>3.85</SALESTAX>
        <VAT>0</VAT>
        <SHIPPING>0</SHIPPING>
```

```
        <COUNTRYSPECIFICFEES>0</COUNTRYSPECIFICFEES>
```

```
        <PRODUCTTOTAL>769.5</PRODUCTTOTAL>
        <ORDERDISCOUNT>0</ORDERDISCOUNT>
        <AFTERDISCOUNTPRODUCTTOTAL>0</AFTERDISCOUNTPRODUCTTOTAL>
        <ORDERTOTAL>773.35</ORDERTOTAL>
        <SHIPPINGADDRESS>
            <FIRSTNAME>Jerry</FIRSTNAME>
            <LASTNAME>Bob</LASTNAME>
            <ADDR1>123 Anywhere Lane</ADDR1>
            <ADDR2>Apt 2B</ADDR2>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 203 | 317 

Firestorm® Web Services API | Version 2.2.33 

```
            <CITY>Dallas</CITY>
```

```
            <STATE>Texas</STATE>
```

```
            <POSTALCODE>76108</POSTALCODE>
            <COUNTRY>USA</COUNTRY>
```

```
        </SHIPPINGADDRESS>
```

```
        <ORDERDETAIL>
```

```
            <PRODUCTNUMBER>F-014</PRODUCTNUMBER>
```

```
            <PRODUCTQTY>10</PRODUCTQTY>
```

```
            <PRICEEACH>76.95</PRICEEACH>
```

```
            <RETAILPRICEEACH>76.95</RETAILPRICEEACH>
```

```
            <WHOLESALEPRICEEACH>76.95</WHOLESALEPRICEEACH>
            <UPLINEVOLUMEEACH>72</UPLINEVOLUMEEACH>
            <PSVAMOUNTEACH>72</PSVAMOUNTEACH>
            <ISFREEPRODUCT>False</ISFREEPRODUCT>
            <FREESHIPPING>False</FREESHIPPING>
            <INSTOCK>True</INSTOCK>
        </ORDERDETAIL>
```

```
    </ORDER>
```

```
</FIRESTORMRESULT>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 204 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.VoidOrder 

Voids an existing order in the system. Several options are provided to claw back commissions, send negative volume upline, etc. Your compensation plan will dictate which of these options you will need to use in your situation. 

|Method Definition|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|OrderID|Y|The unique ID of the order to be voided|Integer|Any valid non voided<br>Order ID|
|VoidReason|Y|The reason for the voiding of the order. This will be<br>recorded in the historyof the order.|String||
|Override|Y|Force a void on an order that has already been<br>fulfilled.|Boolean|TRUE or FALSE|
|SendNegativeVolumeUp|Y|Send negative volume up the tree. This should only<br>be set to TRUE on Binary systems when you truly<br>wish to remove the volume from the structure. This<br>will affect all positions upline from the order being<br>voided. Use with caution.|Boolean|TRUE or FALSE|
|CreditDeclined|Y|A Boolean value indicating whether or not the Void<br>is due to a Credit Card payment being<br>declined/rejected.|Boolean|TRUE or FALSE|
|DeclineReason|Y|When CreditDeclined is TRUE, this is the reason the<br>Credit Card was declined.|String||
|DoClawback|Y|Clawback any commissions that have been paid on<br>this order. If set to TRUE this will clawback ALL<br>commissions that have been linked to this order,<br>regardless of whether or not the commissions have<br>been issued on a check or wired via ACH. This can<br>potentially cause commission accounts to go into a<br>negative state. Use with caution.|Boolean|TRUE or FALSE|
|NegativeBinaryOnly|Y|A Boolean value telling the system to only send<br>negative volume upline for products that are flagged<br>as Binary products. Can only be TRUE when<br>SendNegativeVolumeUp is also TRUE. Must be<br>FALSE if NegativeUnilevelOnlyis TRUE.|Boolean|TRUE or FALSE|
|NegativeUnilevelOnly|Y|A Boolean value telling the system to only send<br>negative volume upline for products that are NOT<br>flagged as Binary products. Can only be TRUE when<br>SendNegativeVolumeUp is also TRUE. Must be<br>FALSE if NegativeBinaryOnlyis TRUE.|Boolean|TRUE or FALSE|
|NegativeBoth|Y|A Boolean value telling the system to send negative<br>volume upline for all products on the order,<br>regardless of whether or not they are flagged as<br>Binary products. Can only be TRUE when<br>SendNegativeVolumeUpis also TRUE|Boolean|TRUE or FALSE|
|VoidChildOrders|Y|A Boolean value to specify whether or not Child<br>Orders linked to this order should also be voided.<br>Use with extreme caution, as setting this to TRUE<br>could have unexpected results. For further<br>information, please contact our support<br>department.|Boolean|TRUE or FALSE|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 205 | 317 

Firestorm® Web Services API | Version 2.2.33 

|Fields|No|
|---|---|
|Max Records|No|



##### **<u>Additional Information</u>** 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 206 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.VoidOrderDetail 

Voids an existing order detail in the system. Several options are provided to claw back commissions, send negative volume upline, etc. Your compensation plan will dictate which of these options you will need to use in your situation. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|OrderDetailID|Y|The Unique OrderDetailID as assigned in Firestorm<br>to be voided.|Integer||
|VoidReason|Y|The reason for the voiding of the order detail. This<br>will be recorded in the historyof the order.|String||
|SendNegativeVolumeUp|Y|Send negative volume up the tree. This should only<br>be set to TRUE on Binary systems when you truly<br>wish to remove the volume from the structure. This<br>will affect all positions upline from the order being<br>voided. Use with caution.|Boolean|TRUE or FALSE|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 207 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.GetShipperListWithRates 

Returns a list of shippers that are valid for the passed in order. This method will take into account all configurations in Firestorm that can affect which shippers are available for a given order. You may use the output of this web service to reliably display shipping options with actual rates for the order to your end user. 

|Method Definition<br>Argument|Required|Description|Datatype|Valid Values|
|---|---|---|---|---|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|OrderXML|Y|XML Document describingthe order|String|See write upbelow|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

When implementing your own shopping display, it will be necessary for you to call this web service to obtain a list of available shippers for the order, along with shipping rates for each shipper. 

The rates presented are dependant on dozens of possible configurations in Firestorm®, and you should never attempt to calculate shipping charges yourself, as configurations can change at any time based on a given customer’s business requirements. These changes can result is shipping charges changing for any given shipper at any given time. 

Using this web service will allow you to simply present a rate for a given shipper that you can have confidence in because it has taken into account all of the different rules governing which shipper can be used on a given order. 

##### <u>Order XML</u> 

In order to successfully call this web service it will be necessary for you to build out an XML document describing the order to perform calculations against. (This XML document is the same used for other order based web services) A sample XML document is provided below: 

```
' ///////////////////////////
' Sample order XML
' ///////////////////////////
<![CDATA[
<?xml version='1.0' encoding='utf-8' ?>
<ORDER itemcount='1'>
<DEALERID>integer</DEALERID>
<CATALOGUEID>integer</CATALOGUEID>
<SHIPPERID>integer</SHIPPERID>
<CURRENCY>string</CURRENCY>
<ADDITIONALPOINTS>double</ADDITIONALPOINTS>
<COMMISSIONAMOUNTTOUSE>double</COMMISSIONAMOUNTTOUSE>
<SHIPPINGADDRESS>
<FIRSTNAME>string</FIRSTNAME>
<LASTNAME>string</LASTNAME>
<COMPANYNAME>string</COMPANYNAME>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 208 | 317 

Firestorm® Web Services API | Version 2.2.33 

```
<ADDR1>string</ADDR1>
<ADDR2>string</ADDR2>
<CITY>string</CITY>
<STATE>string</STATE>
<POSTALCODE>string</POSTALCODE>
<COUNTRY>string</COUNTRY>
</SHIPPINGADDRESS>
<ORDERDETAIL>
<PRODUCTNUMBER>string</PRODUCTNUMBER>
<PRODUCTQTY>integer</PRODUCTQTY>
<PRICEEACH>double</PRICEEACH>
<RETAILPRICEEACH></RETAILPRICEEACH>
<WHOLESALEPRICEEACH></WHOLESALEPRICEEACH>
<UPLINEVOLUMEEACH></UPLINEVOLUMEEACH>
<PSVAMOUNTEACH></PSVAMOUNTEACH>
<ISFREEPRODUCT>boolean</ISFREEPRODUCT>
<FREESHIPPING>boolean</FREESHIPPING>
</ORDERDETAIL>
```

```
</ORDER>
]]>
```

The xml document contains the basic information required to perform the necessary calculations on the Firestorm® system for the specific order. The following table describes each node and its requirements: 

|Element|Datatype|Attribute|Definition|
|---|---|---|---|
|<![CDATA[|||OpeningCDATA tag|
|<?xml version='1.0' encoding='utf-8' ?>|||Xml document declaration|
|ORDER||itemcount|Containing envelope for the order.<br>The “itemcount” attribute will contain the total number of<br>ORDERDETAIL elelments that are present in the document. This<br>number mut be accurate or the XML document will be rejected.|
|DEALERID|integer||If this is a member order, this should be set to the DealerID of the<br>member who is placing the order.|
||||If this is a retail customer order,set this value to -1|
|CATALOGUEID|integer||The catalogueID of the catalog that this order is being placed against.<br>You must obtain this ID from the Firestorm® system.<br>**TIP**: A list of valid catalogueIDs may be obtained by calling<br>FirestormInventoryWS.GetCatalogueList() and then selecting the<br>correct catalog from the list. You will need to work with the owner of<br>the Firestorm® system to determine the best method for selecting<br>the correct ID.|
|SHIPPERID|integer||The shipperID that will be used to shipthis order.|
|CURRENCY|String||ISO Currency code representing the currency that the calculated<br>results will be**returned**in.<br>**Warning**: Any financial numbers passed in to this method MUST be<br>passed in using the base currency type as defined in Firestorm®.  If<br>you are unsure of the base currencytype, please contact the client.|
|ADDITIONALPOINTS|||If the order is being paid for (completely or partially) with product<br>reward points, this field will contain the number of points to use<br>when calculating payments due on this order.<br>Pass in 0 if nopoints are beingused.|
|COMMISSIONAMOUNTTOUSE|||If the purchaser is trying to use earned and unpaid commissions to<br>pay for this order (completely or partially), this is the amount of<br>commission to use towards payment.<br>Pass in 0 if you are not using commissions to pay.<br>**Warning:**This value must be passed in the base currency of the<br>system.|
|SHIPPINGADDRESS|||Containingenvelope for the shippingaddress elements|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 209 | 317 

Firestorm® Web Services API | Version 2.2.33 

|<br>|FIRSTNAME<br>LASTNAME||First name<br>Last Name|
|---|---|---|---|
||<br>COMPANYNAME||<br>Companyname|
||ADDR1||Address line 1|
||ADDR2||Address line 2|
||CITY||Cityname|
||STATE||State code – This code must exist in Firestorm®! Verify state codes<br>with the client,as theyare important for sales tax calculations.|
||POSTALCODE||Postal Code(Zipcode)|
||COUNTRY||Country code – This code must exist in Firestorm®! Verify country<br>codes with the client,as theyare important for VAT tax calculations.|
|ORDERD|ETAIL||Containing envelope for a single order detail element. The document<br>may contain 1 to n ORDERDETAIL elements.<br>**Warning:**Make sure the attribute “itemcount” on the ORDER node is<br>set to the total number of ORDERDETAIL elements contained in the<br>document|
||PRODUCTNUMBER|String|Product number that exists in the catalog specified in the web service<br>call|
||PRODUCTQTY|Integer|Quantityof this item to order|
||PRICEEACH|Double|Actual price paid for EACH item (do**not**multiply this by<br>PRODUCTQTY. The system will do that for you).<br>**WARNING: Only set this value if you are NOT providing**<br>**Retail/Wholesale/Upline/PSV. If you set this value it will override**<br>**what is in the RETAILPRICEEACH and WHOLESALEPRICEEACH price**<br>**fields!**|
||||**If you are providing explicit pricing using the fields below, set this**<br>**value to $0**<br>**Warning:**This value must be passed in the base currency of the<br>system.|
||RETAILPRICEEACH|Double|Retail price for each product. Do not multiply by PRODUCTQTY.<br>Setting this value to -1 will cause the system to use the price<br>configured in the catalog.<br>**Warning:**This value must be passed in the base currency of the<br>system.|
||WHOLESALEPRICEEACH|Double|Wholesale price for each product. Do not multiply by PRODUCTQTY.<br>Setting this value to -1 will cause the system to use the price<br>configured in the catalog.|
||||**Warning:**This value must be passed in the base currency of the<br>system.|
||UPLINEVOLUMEEACH|Double|Upline (commissionable) volume for each product. Do not multiply by<br>PRODUCTQTY. Setting this value to -1 will cause the system to use<br>the price configured in the catalog.<br>**Warning:**This value must be passed in the base currency of the<br>system.|
||PSVAMOUNTEACH|Double|PSV Amount for each product. Do not multiply by PRODUCTQTY.<br>Setting this value to -1 will cause the system to use the price<br>configured in the catalog.<br>**Warning:**This value must be passed in the base currency of the<br>system.|
||ISFREEPRODUCT|Boolean|<br>Flag to indicate if this is a free product. “True” = is a free product,<br>“False” = not a freeproduct|
|<br>]]>|FREESHIPPING|Boolean|Flag to indicate if shipping charges should be suppressed for this<br>product. “True” = no shipping will be calculated, “False” = shipping<br>charges will be calculated normally.<br>ClosingCDATA tag|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 210 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the<br>number of errors that occurred during the call, which will coorelate directly<br>to the number of <ERRORMSG> elements that will be present. All argument<br>validation errors will be returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|
|SHIPPERS|||Containing envelope for all available shippers. Attribute “shippercount” will<br>contain the total number of shipper envelopes to expect.|
|SHIPPER|||Containingenvelope for a single shipper.|
|<br>SHIPPERID|integer||The Firestorm uniques identifier for this shipper|
|<br>CODE|string||Short codefor the shipper(i.e.: UPSG)|
|<br>DESCRIPTION|string||Longdescription of the shipper(i.e.: UPS Ground)|
|<br>ISDEFAULT|boolean||Flagto indicate if this is the default shipper|
|<br>SHIPPINGCHARGE|string||The amount of the charge to ship the submitted order with this shipper. This<br>amount will be presented in the same currency that was requested in the<br>order (CURRENCY node). Currency formatting will be performed using<br>currency setup configrations in Firestorm.<br>**NOTE: The system could return a value of-999in this field if no shipping**<br>**zone has been defined in Firestorm for the destination address for the**<br>**specific shipper. This means that the system was unable to calculate a**<br>**charge for this shipper to the destination shipping address.**<br>**If you detect this value, you should SUPPRESS this shipper as an option for**<br>**the user to select.**<br>This is indicative that there is a possible configuration problem on the<br>administrative side of Firestorm that must be resolved or it can also be an<br>indicator that the person purchasing the order cannot use that shipper, even<br>though it is assigned to the catalog.|



##### <u>Sample Return XML Document</u> 

Note that in this example, shipper FEDEXG (ShipperID 65) has returned a shipping charge of -999. In this case, this shipper should be suppressed and not displayed as a choice for the purchaser to select. 

<?xml version='1.0' encoding='utf-8' ?> 

<FIRESTORMRESULT> 

<STATUS>SUCCESS</STATUS> <ERRORS errorcount='0'></ERRORS> 

<SHIPPERS shippercount=3> <SHIPPER> <SHIPPERID>63</SHIPPERID> <CODE>FEDEX1DAY</CODE> <DESCRIPTION>Fed Ex Overnight </DESCRIPTION> <ISDEFAULT>0</ISDEFAULT> <SHIPPINGCHARGE>23.15</SHIPPINGCHARGE> </SHIPPER> <SHIPPER> <SHIPPERID>65</SHIPPERID> <CODE>FEDEXG</CODE> 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 211 | 317 

Firestorm® Web Services API | Version 2.2.33 

<DESCRIPTION>Fed Ex Ground </DESCRIPTION> <ISDEFAULT>0</ISDEFAULT> <SHIPPINGCHARGE>-999.00</SHIPPINGCHARGE> </SHIPPER> <SHIPPER> <SHIPPERID>64</SHIPPERID> <CODE>USPSEX</CODE> <DESCRIPTION>USPS Express Mail</DESCRIPTION> <ISDEFAULT>0</ISDEFAULT> <SHIPPINGCHARGE>5.20</SHIPPINGCHARGE> 

</SHIPPER> </SHIPPERS> 

</FIRESTORMRESULT> 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 212 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.GetShipperList 

Returns a list of all shippers that are configured in the system. You may also pass in a ShipperID or ShipperCode to return the details of a specific Shipper. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|ShipperID||The Firestorm assigned ID of a Shipper record|Numeric|Must be a positive<br>numeric value. Non-<br>numeric or negative<br>values will be<br>ignored.|
|ShipperCode||The configured Code of a Shipper record|String||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

If you pass in a ShipperID or ShipperCode, only the matching shipper record will be returned. Omitting both of these values will cause the full shipper list to be returned to you. 

NOTE: If you pass in both a ShipperID and a ShipperCode as part of the same request, the ShipperID will take precedence over the ShipperCode, and the ShipperCode value will be ignored. 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**||**DataType**|**Attribute**|**Definition**|
|---|---|---|---|---|
|FIRESTOR|MRESULT|n/a||Containingenvelope for the result document|
|STATUS||string||SUCCESS or FAIL|
|ERRORS||n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the<br>number of errors that occurred during the call, which will coorelate directly<br>to the number of <ERRORMSG> elements that will be present. All argument<br>validation errors will be returned in this manner|
|ERRORMS|G|string||For each failure that occurred,a stringdescribingthe error.|
|SHIPPERS||||Containing envelope for all available shippers. Attribute “shippercount” will<br>contain the total number of shipper envelopes to expect.|
|SHIPPER||||Containingenvelope for a single shipper.|
||SHIPPERID|integer||The Firestorm uniques identifier for this shipper|
||CODE|string||Short codefor the shipper(i.e.: UPSG)|
||DESCRIPTION|string||Longdescription of the shipper(i.e.: UPS Ground)|
||ACTIVE|Boolean||Flagto indicate if this shipper is active|
||ISDEFAULT|boolean||Flagto indicate if this is the default shipper|
||USER1|string||Custom defined user data|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 213 | 317 

Firestorm® Web Services API | Version 2.2.33 

||USER2|string|Custom defined user data|
|---|---|---|---|
||USER3|string|Custom defined user data|
||USER4|string|Custom defined user data|
||USER5|string|Custom defined user data|
||IMAGEURL|String|The configured imagepath for the logo of the shippingservice|
||TRACKINGSITEURL|string|The configured url for tracking status updates. Note: This value may contain<br>replacement tokens (eg: <TRACKINGNUMBER>) that are meant to be<br>replaced with the tracking number of the shipment to view. As such, the<br>data contained in this element is wrapped in a CDATA tag.|



##### <u>Sample Return XML Document</u> 

Note that in this example, shipper FEDEXG (ShipperID 65) has returned a shipping charge of -999. In this case, this shipper should be suppressed and not displayed as a choice for the purchaser to select. 

<?xml version='1.0' encoding='utf-8' ?> 

<FIRESTORMRESULT> 

<STATUS>SUCCESS</STATUS> <ERRORS>0</ERRORS> <ERRORMSG></ERRORMSG> <SHIPPER> <SHIPPERID>59</SHIPPERID> <CODE>PAID-SHIP</CODE> <DESCRIPTION>Shipment included in price</DESCRIPTION> <ACTIVE>-1</ACTIVE> <ISDEFAULT>0</ISDEFAULT> <USER1></USER1> <USER2></USER2> <USER3></USER3> <USER4></USER4> <USER5></USER5> <IMAGEURL></IMAGEURL> <TRACKINGSITEURL> <![CDATA[]]> </TRACKINGSITEURL> </SHIPPER> <SHIPPER> <SHIPPERID>60</SHIPPERID> <CODE>UPS Overnight</CODE> <DESCRIPTION>UPS Overnight Shipping</DESCRIPTION> <ACTIVE>-1</ACTIVE> <ISDEFAULT>0</ISDEFAULT> <USER1></USER1> <USER2></USER2> <USER3></USER3> <USER4></USER4> <USER5></USER5> <IMAGEURL>../art/ShipperLogos/UPSLogo.jpg</IMAGEURL> 

<TRACKINGSITEURL> 

<![CDATA[http://wwwapps.ups.com/WebTracking/processInputRequest?HTMLVersion=5.0&loc=en_US&Requester=UPSHome&tracknum=<TRA CKINGNUMBER>&AgreeToTermsAndConditions=yes&ignore=&track.x=17&track.y=11]]> 

</TRACKINGSITEURL> 

</SHIPPER> 

</FIRESTORMRESULT> 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 214 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormOrderWS.FulfillOrder 

Returns a list of all shippers that are configured in the system. You may also pass in a ShipperID or ShipperCode to return the details of a specific Shipper. 

|Method Definition|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|OrderID|Y|The ID of the order to be fulfilled|Integer|A valid Firestorm<br>Order ID|
|OrderDetailID|Y|The ID of the order detail record to be fulfilled. If an<br>Order Detail ID is passed in, only that Order Detail<br>will be fulfilled. To process the entire order, pass -1.|Integer|A valid Firestorm<br>Order Detail ID that<br>is attached to the<br>specified Order ID or<br>-1|
|FullfilledQty|Y|The quantity of product fulfill. This value must be<br>greater than 0 of an Order Detail ID is passed in.<br>Pass in -1 if no Order Detail ID is used.|Integer|Any non zero<br>positive value, or -1|
|FullfillComments|Y|The comments to be applied to the fulfillment<br>historyrecord.|String|Any non-zero length<br>string|
|OverrideQuantityValue|Y|A flag to indicate if the FullfilledQty should be<br>ignored, and the current Staged Qty be used<br>instead.|Boolean|TRUE or FALSE|
|FullyFullfilled|Y|A flag to inidicate if the order will be fully fulfilled<br>with the completion of this fulfillment.|Boolean|TRUE or FALSE|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

If you pass in a valid OrderDetailID, the fulfillment request will only be processed against that single line item. Passing -1 for OrderDetailID will cause the system to attempt to fulfill the entire order. 

Passing TRUE for FullyFullfilled will cause the order detail (or the entire order if no order detail is specified) to be marked as completely fulfille, and no further fulfillment operations will be possible on the order detail (or order). Only set this value to TRUE if you will not need to do any other fulfillment operations against this order detail (or order). 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**<br>**Definition**|
|---|---|---|
|FIRESTORMRESULT|n/a|Containingenvelope for the result document|
|STATUS|string|SUCCESS or FAIL|
|C o p|y r i g h t|2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c .P a g e215 | 317|



Firestorm® Web Services API | Version 2.2.33 

|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the<br>number of errors that occurred during the call, which will coorelate directly<br>to the number of <ERRORMSG> elements that will be present. All argument<br>validation errors will be returned in this manner|
|---|---|---|---|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



##### <u>Sample Return XML Document</u> 

<?xml version='1.0' encoding='utf-8' ?> <FIRESTORMRESULT> 

<STATUS>SUCCESS</STATUS> <ERRORS>0</ERRORS> <ERRORMSG></ERRORMSG> 

</FIRESTORMRESULT> 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 216 | 317 

Firestorm® Web Services API | Version 2.2.33 

### FirestormPartyWS 

|General Inform|ation|
|---|---|
|Name|FirestormPartyWS.asmx|
|WSDL|https://www.firestormwebservices.com/FirestormWebServices/FirestormPartyWS.asmx|
|Description|Provides access into specific areas of the Firestorm®partysubsystem.|



|Method Summary||
|---|---|
|Method Name|Return Type|
|AssignGuestToParty|Complex XML document|
|FindPartyGuest|DataTable|
|GetOpenPartiesByDealer|DataTable|
|GetGuestListByPartyID|Datatable|
|GetPartiesByDate|DataTable|
|SavePartyOrder|Complex XML document|
|SavePartyGuest|Complex XML Document|
|GetPartyHostDetail|DataTable|
|SavePartyHost|Complex XML Document|
|SaveParty|Complex XML Document|
|CloseParty|Complex XML Document|
|GetPartyTypeList|Datatable|
|GetPartyStatusList|DataTable|
|GetCampaignList|DataTable|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 217 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormPartyWS.AssignGuestToParty 

Will assign (invite) a specified Party Guest to the specified Party. Additionally, the system will automatically handle any evite processing that is required, based on the Party Type of the specified Party. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|PartyID|Y|The unique ID number assigned to the Party by<br>Firestorm®|Integer|Any valid Party ID<br>that exists in<br>Firestorm®|
|PartyGuestID|Y|The unique ID number assigned to the Party Guest<br>by Firestorm®|Integer|Any valid Party Guest<br>ID that exists in<br>Firestorm® that is<br>also assigned to the<br>Party Host of the<br>PartyIDpassed in.|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The Party Guest that is being assigned to the Party ID passed in, must be sponsored by the Party Host that is hosting the party. If this is not true, this call will fail. Please use FirestormPartyWS.SavePartyGuest() instead to create a new guest record for the correct host. 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 218 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormPartyWS.FindPartyGuest 

Retrieves a list of all Party Guests matching the specified criteria. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|PartyGuestID|Y|The unique ID number assigned to the Party Guest<br>by Firestorm®|Integer|Any valid Party Guest<br>ID that exists in<br>Firestorm®|
|PartyHostID|Y|The unique ID number assigned to the Party Host by<br>Firestorm®|Integer|Any valid Party Host<br>ID that exists in<br>Firestorm®|
|FirstName|Y|The first name of the PartyGuest|String||
|LastName|Y|The last name of the PartyGuest|String||
|CompanyName|Y|The companyname of the PartyGuest.|String||
|Email|Y|Theprimaryemail address of the PartyGuest|String||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

All fields are required to be supplied, but you do not need to specify a known value for each field. For instance, if you want to retrieve a list of all Party Guests for a specific Party Host, you can specify the PartyHostID in the appropriate argument, a -1 for the PartyGuestID argument, and empty strings (“”) for the remaining search fields. This call would return to you a list of all Party Guests that exist in the system who are sponsored by the Party Host you specified. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|PartyGuestID|Integer|The unique PartyGuestID as assigned byFirestorm®|
|GenderID|Integer|If used, the unique ID of the Gender assigned to the Party<br>Guest.|
|RaceID|Integer|If used,the unique ID of the Race assigned to the PartyGuest.|
|PartyHostID|Integer|The unique PartyHostID as assigned byFirestorm®|
|FirstName|String|The First Name of the PartyGuest|
|LastName|String|The Last Name of the PartyGuest|
|CompanyName|String|The CompanyName of the PartyGuest|
|Address1|String|The Street address of the PartyGuest|
|Address2|String|The second line Street Address(Suite,etc)of the PartyGuest|
|City|String|The Cityof the PartyGuest|
|State|String|The State Code of the Party Guest (State Codes defined in<br>Firestorm®)|
|Zip|String|The Zip/Postal Code of the PartyGuest|
|Country|String|The Country Code of the Party Guest (Country Codes defined<br>in Firestorm®)|
|Email|String|The PrimaryEmail Address of the PartyGuest|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 219 | 317 

Firestorm® Web Services API | Version 2.2.33 

|EmailOptOut|Integer|A flag indicating whether or not he Party Guest has opted out<br>of email communications.<br>0 = False<br>Non-Zero = True.<br>If this field is True, it is advised that you respect the settings of<br>the PartyGuest and do not contact thisguest via email.|
|---|---|---|
|Phone|String|The Phone number of the PartyGuest|
|CreateDate|Date|The date this record was created in Firestorm®|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 220 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormPartyWS.GetOpenPartiesByDealer 

Retrieves a list of open parties where the sponsoring dealer is the dealer ID that is passed in to this call. This service can be used in integrations where the external system needs to know a party ID for a given dealer. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The unique ID number assigned to the Dealer by<br>Firestorm®|Integer|Any valid DealerID<br>that exists in<br>Firestorm®|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

When your system needs to know the party ID for a given dealer (Member or Customer) use this web service to retrieve a list of all currently open parties that are sponsored by the passed in DealerID. 

##### <u>Close Date</u> 

Be aware that is a party is already passed its close date, it will NOT be returned by this call even if the party is still in an OPEN status. This behavior is consistent with other areas of the system. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|PartyID|Integer|The uniquepartyID as assigned byFirestorm®|
|HostName|String|The name of the host of theparty presented as “Last,First”|
|EventDate|Date|The date (mm/dd/yyyy) that the party is schedule to be held<br>on.|
|EventTime|String|The time of the event.|
|OpenDate|Date|The date that thispartyis open to take orders(mm/dd/yyyy)|
|CloseDate|Date|The date that this party will close. (mm/dd/yyyy). Remember<br>that is this date is passed this party will no longer show up in<br>the results returned by this call, even if the party is still in<br>OPEN status.|
|Location|String|The location of theparty presented as “City,State”|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 221 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormPartyWS.GetGuestListByPartyID 

Retrieves a list of party guest records that are currently assigned to the designated party. This information can be used by a remote system to manage the guest list for a party. Contact information for each guest is included as well as e-vite response status. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|PartyID|Y|The unique ID number assigned to the party|Integer|Any valid party ID<br>that exists in<br>Firestorm®|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The system will allow a host or member to send multiple e-vites to a party guest. These can consist of the initial invite, reminder emails, invite resends, etc. The records returned by this web service will contain response information only to the initial invitation. 

The returned data will also contain information about the last e-vite message that was sent to the guest. There is no limit to the number of e-vites that host or member can send to the party guest. The total number of available e-vites are controlled by the company and what they wish to make available to the consultant for use. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|PartyGuestID|Integer|The unique ID assigned to theparty guest|
|LastName|String||
|FirstName|String||
|CompanyName|String||
|Email|String|Email address|
|Phone|String|Phone number(no formattingapplied bysystem)|
|InviteDate|Date|Date theguest was initiallyinvited to theparty|
|ResponseDate|Date|Date the response to the e-vite wasposted in the system|
|EviteResponse|String|Response to the e-vite as selected by the guest. This response<br>is dictated bywhich link theguest clicks on in their e-vite|
|LastEviteTitle|String|The title of the last evite sent to theguest|
|LastEviteDate|Date|The date the last e-vite was sent|
|EviteCount|integer|The total number of e-vites that have been sent to thisguest|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 222 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormPartyWS.GetPartiesByDate 

Retrieves a list of all parties whose Event Date falls within the specified date range. Specific timestamps may be specified on the Start Date and End Date parameters to further narrow the search window. All parties that fall within this range will be returned by this method regardless of the current Party Status. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|StartDate|Y|The beginning of the date range|DateTime|Any valid datetime<br>value. Ex: 1/1/2018<br>01:30:55 AM|
|EndDate|Y|The end of the date range.|DateTime|Any valid datetime<br>value. Ex: 1/7/2018<br>06:15:00 PM|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

All parties that fall within this range will be returned by this method regardless of the current Party Status. 

You may also specify a timestamp on each of the Start Date and End Date parameters. This will force the method to only return parties where the Event Date falls between the specified time stamps of the starting and ending day. Any party that falls outside of the specified timestamp window will not be returned, even though it was on the day of the cut off. 

For example, if an EndDate of 1/15/2018 01:00:00 PM is specified, a party with an Event Date and time of 1/15/2018 01:30:00 PM would not be returned. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|PartyID|Integer|The unique PartyID as assigned byFirestorm®|
|PartyTypeID|Integer|The unique PartyTypeID as assigned byFirestorm®|
|PartyTypeCode|String|The code assigned to the Party Type as identified by the<br>PartyTypeID. This will be based on the current status of the<br>Partyat the time this method is called.|
|PartyStatusID|Integer|The unique PartyStatusID as assigned byFirestorm®|
|PartyStatusCode|String|The code assigned to the Party Status as identified by the<br>PartyStatusID. This will be based on the current status of the<br>Partyat the time this method is called.|
|PartyHostID|Integer|The unique PartyHostID as assigned byFirestorm®|
|HostFirstName|String|The First Name of the PartyHost|
|HostLastName|String|The Last Name of the PartyHost|
|SponsoringDealerID|Integer|The unique Dealer ID of the sponsor of the Party Host<br>assigned to the Party.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 223 | 317 

Firestorm® Web Services API | Version 2.2.33 

|EventDate|Date|The full Event Date with timestamp of the party. This the date<br>and time that the actual event is scheduled to occur.|
|---|---|---|
|OpenDate|Date|The date that thispartyis open to take orders(mm/dd/yyyy)|
|CloseDate|Date|The date that thispartywill close.(mm/dd/yyyy).|
|LocationAddr1|String|The supplied Address 1 of the physical location of the party, if<br>supplied.|
|LocationAddr2|String|The supplied Address 2 of the physical location of the party, if<br>supplied.|
|LocationCity|String|The supplied City of the physical location of the party, if<br>supplied.|
|LocationState|String|The supplied State of the physical location of the party, if<br>supplied.|
|LocationZip|String|The supplied Zip/Postal Code of the physical location of the<br>party,if supplied.|
|LocationCountry|String|The supplied Country of the physical location of the party, if<br>supplied.|
|LocationPhone|String|The supplied Phone Number of theparty,if supplied.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 224 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormPartyWS.SavePartyOrder 

Allows an external shopping cart to transmit a party order into the Firestorm® system for processing. Typically used by 3<sup>rd</sup> party shopping carts that a company might want to use in lieu of the shopping cart included with the Firestorm® system. Please be aware that if you do this, you will not be able to use all party functionality provided with the system unless your system provides those same features in its shopping cart. 

**PCI/DSS WARNING:** This web service uses sensitive personal and payment information to process an order. It is YOUR responsibility to ensure that you are following all proper PCI/DSS procedures in addition to accessing the web service over a secure (https) link in your production environment!! 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|ShippingCode|Y|The code defined by Firestorm® to identify the<br>shipping method to use for this order|String|Any valid shipper<br>code defined in<br>Firestorm®|
|ShipAddress1|Y|ShippingAddress Line 1|String||
|ShipAddress2|Y|Shipping Address Line 2|String|May be an empty<br>string|
|ShipCity|Y|ShippingCity|String||
|ShipState|Y|Shipping State|String|Any valid state code<br>defined in Firestorm®|
|ShipZip|Y|Shipping postal code|String||
|ShipCountry|Y|Shipping Country|String|Any valid country<br>code defined in<br>Firestorm®|
|Phone|Y|Phone number|String||
|OrderTotalAmount|Y|Total dollar amount of the products on the order.<br>(do not include any other fees) This value is used to<br>validate the calculated amount contained in the<br>order detail XML.<br>OVERRIDE: When you pass -99 in this field, the<br>system will calculate the total amount of the order<br>from the order detail XML passed in and will NOT<br>compare it to this number.||-99 or actual dollar<br>amount|
|SpecialInstructions|Y|Any special instructions for this order. Typically<br>collected from the purchaser. This value will appear<br>on the shippingorder(or shippingexport).|String||
|CatalogueID|Y|The Firestorm® catalog ID from Firestorm®|Integer|Any valid catalog ID<br>defined in Firestorm®|
|BillFirstName|C|BillingFirst Name|String||
|BillLastName|C|BillingLast Name|String||
|BillCompanyName|C|Billing Company Name (must be provided if first and<br>last name are blank)|String||
|BillAddress1|Y|BillingAddress Line 1|String||
|BillAddress2|Y|Billing Address Line 2|String|May be an empty<br>string|
|BillCity|Y|BillingCity|String||
|BillState|Y|BillingState|String||
|BillZip|Y|Billing postal code|String||
|BillCountry|Y|Billing Country|String|Any valid country<br>code defined in<br>Firestorm®|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 225 | 317 

Firestorm® Web Services API | Version 2.2.33 

|TotalOrderDiscount|Y|Total dollar value of the discount applied to this<br>order|Double|Must be >= 0|
|---|---|---|---|---|
|SoldTo|Y|First and Last Name of thepurchaser|String||
|TotalOrderDiscountPercentage|Y|The total discount applied as a percentage of the<br>total order.|Double|Must be a value<br>between 0 and 1|
|AutoshipOrder|Y|Flag to indicate if this order should count as an<br>autoship (recurring order) (generally for qualification<br>purposes).<br>When this flag is set to TRUE (non-zero) the system<br>will populate the value of 88888888 into the<br>RecurringParentOrderID field on the order header.|Boolean|0 = False<br>-1 = True|
|OrderDetail|Y|Complex XML document describing the contents of<br>the order(see details below)|String|See description<br>below|
|AddlPaymentInfo|Y|Any additional payment information you wish to be<br>stored with this order. This data is NOT used by<br>Firestorm® and is stored for historical purposes only.<br>NOTE: This value is only saved when the order<br>successfully processes in the system.|String||
|PaymentTypeCode|Y|Code representing the type of payment to use to pay<br>for this order.<br>**Note: E-Check payment types are not currently**<br>**supported by this web service.**|String|Any valid payment<br>type code defined in<br>Firestorm®|
|CardAccountNumber|C*|Credit card account number|String||
|CVV2Code|C*|Securitycode from the back of the credit card|String||
|CardHolderName|C*|Name as it appears on the credit card|String||
|CardExpirationMonth|C*|Expiration date month expressed as a 2 digit<br>number,zero filled.|String|Must be between 01<br>and 12|
|CardExpirationYear|C*|Expirationyear expressed as a 4 digit number|String|Anyvalidyear|
|Email|Y|Email address where order receipt will be sent|String|A valid email address|
|PartyID|Y|The unique ID assigned to the party by Firestorm®|Integer|Any valid party ID<br>that is currently in an<br>“OPEN” state and its<br>close date has not<br>passed|
|PartyGuestID|Y|The unique ID assigned to the party guest|Integer|Any valid guest ID<br>that is currently<br>assigned to the party<br>specified by<br>“PartyID”|
|ShipToHost|Y|Flagto indicate if this order is shippingto the host|Boolean|TRUE or FALSE|
|ShipToGuest|Y|Flag to indicate if this order is shipping directly to the<br>guest(dropship)|Boolean|TRUE or FALSE|
|ShipToDealer|Y|Flag to indicate if this order is shipping to the dealer<br>(consultant)|Boolean|TRUE or FALSE|
|DoNotSendOrderRecieptEmail|Y|Flag to indicate if this order should send a normal<br>order receipt to thepurchaser.|Boolean|TRUE or FALSE|



* **Note: If the payment type code flagged as a credit card in Firestorm, these conditional fields are required.** 

##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 226 | 317 

Firestorm® Web Services API | Version 2.2.33 

When an order is placed with this method, the order will be credited to the party per normal procedures. The consultant (Dealer) who enrolled the hostess will receive full credit for the order. Any order placed through this web service will also credit towards any host awards that are configured in the system. 

##### <u>Party Guest ID is Required</u> 

When an order is placed, you must supply a party guest ID. This means that the party guest must have an existing record already in the system for the call to succeed. You may retrieve a list of guest IDs for the party with a call to FirestormPartyWS.GetGuestListByParty() 

##### <u>Required Fields You Do Not Have A Value For</u> 

As there are no “optional” arguments in this web service, If a field calls for a string datatype and you do not wish to pass a value or do not need to (i.e.: credit card fields), simply pass an empty (“”) string in place of that argument. If you pass an empty string in an argument where the requirement is not optional, an error will be generated and sent back to you. 

##### <u>Normal Processing Still Occurs</u> 

When an order is passed to this web service, it will be treated exactly like a regular shopping cart order. All autoresponder emails (such as an order receipt) will be sent out per normal system operations. Any other special actions that can be triggered by a shopping cart order will still be triggered normally. It is not possible to suppress this behavior. Be aware of this when transmitting orders in this manner. 

##### <u>Payment</u> 

When an order is submitted to Firestorm® via this web service, the system WILL charge the payment method if the value of the order is greater than $0. Therefore, if your external system is processing the payment PRIOR to submitting the order to Firestorm®, you must specify a non-credit card payment type such as “CASH”. You may set up a custom payment type expressly for this purpose as long as it is not flagged as a credit card type. (See the Firestorm® Use and Operations Manual for details on how to accomplish this) 

If the order amount is greater than $0, and you specified a payment type that is flagged as a credit card in Firestorm®, the credit card engine in the system will process the request normally per the current system configurations. Please note that the credit card will be validated before being submitted. The system will perform basic validation such as mod10, expiration date check and will ensure all required data items are present. Per PCI guidelines, the CVV2 code will not be stored in the system and will only be used to process the current request. 

##### <u>Currency Conversion</u> 

When an order is being processed by the system for this enrollment, the system will look up the country specified in “BillingCountry” to see if a default currency has been defined for that country. If it has, the currency type and the defined conversion ratio for that currency will be saved as part of the order. Normal Firestorm® currency processing will still occur based on system setup and configurations. 

##### <u>Member Orders</u> 

This web service is not intended to be ued to place member orders. If you need to send a member order into Firestorm, you must use the web service FirestormOrderWS.SaveOrderExtendedWithOptions(). 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 227 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### <u>Customer Orders</u> 

This web service is not intended to be ued to place customer orders. If you need to send a customer order into Firestorm, you must use the web service FirestormOrderWS.SaveOrderExtendedWithOptions(). 

Note that when a customer order is sent through this web service, the system will look up the original referring dealer for this customer and will credit this order to that member for commission and qualification purposes. 

##### <u>Order Detail XML</u> 

When calling this web service, this field allows you to build the order on your system, then pass it over to Firestorm® as an XML document as shown below.  You will build an <ORDERDETAIL> element for each line item in your order, then embed them all in a containing <ORDER> element. This payload is not limited to the number of items that may be specified for a single order, allowing you to specify the order contents and pricing in any way necessary to meet your need. 

When building this document, remember that even though you can override pricing for a given product, that product MUST exist in the catalog specified in your call. If a product is missing, the call will fail. 

The <ORDER> element must contain at least 1 <ORDERDETAIL> element. 

If you have passed over a valid value in the “OrderTotalAmount” field, the system will calculate the total price of the products on the order based on this XML document and will then compare the calculated value to the amount you passed over. The amounts must match exactly or the order will be rejected. This facility is intended to be a final “sanity” check to ensure that the XML document contains everything it is supposed to. You may disable this check by passing “-99” in the “OrderTotalAmount” field. 

**_Hint:_** _The passed XML document must be completely valid so that it may be parsed correctly by Firestorm®. Please test your XML document thoroughly to ensure that it can be loaded without error by an XML parser. This will avoid problems with your successful use of this web service._ 

The following is a sample of the XML document required: 

```
' ///////////////////////////
```

```
' Sample order detail XML
```

```
' ///////////////////////////
```

```
<?xml version='1.0' encoding='utf-8' ?>
<ORDER itemcount='1'>
```

```
   <ORDERDETAIL>
```

```
       <PRODUCTNUMBER>string</PRODUCTNUMBER>
```

```
       <PRODUCTQTY>integer</PRODUCTQTY>
       <PRICEEACH>double</PRICEEACH>
       <RETAILPRICEEACH></RETAILPRICEEACH>
```

```
       <WHOLESALEPRICEEACH></WHOLESALEPRICEEACH>
```

```
       <UPLINEVOLUMEEACH></UPLINEVOLUMEEACH>
       <PSVAMOUNTEACH></PSVAMOUNTEACH>
       <ISFREEPRODUCT>boolean</ISFREEPRODUCT>
       <FREESHIPPING>boolean</FREESHIPPING>
```

```
   </ORDERDETAIL>
```

```
</ORDER>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 228 | 317 

Firestorm® Web Services API | Version 2.2.33 

This XML document is constructed by your system and is passed over to Firestorm® in the “OrderDetail” argument. The layout of the XML document is not optional and must be followed exactly to ensure that your order can be read and processed successfully by the Firestorm® system. 

The following table describes in detail the various elements of this document along with definitions and requirements for each section: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|<?xml ……|||Required XML document header(see example above|
|ORDER||Itemcount|Containing envelope for the order.<br>Attribute “itemcount” must be set to the total number of ORDERDETAIL<br>envelopes that arepresent on the order.|
|ORDERDETAIL|||Containing envelope for a single line item on the order<br>Each line item from the order will be contained in a separate ORDERDETAIL<br>envelope. Don’t forget to increment the attributor “itemcount” on the ORDER<br>envelope by1 for each ORDERDETAILpresent in the document.|
|PRODUCTNUMBER|String||Product number that exists in the catalogspecified in the web service call|
|PRODUCTQTY|Integer||Quantityof this item to order|
|PRICEEACH|Double||Actual price paid for EACH item (do not multiply this by PRODUCTQTY. The<br>system will do that for you).<br>**WARNING: Only set this value if you are NOT providing**<br>**Retail/Wholesale/Upline/PSV. If you set this value it will override what is in the**<br>**RETAILPRICEEACH and WHOLESALEPRICEEACH price fields!**<br>**If you are providing explicit pricing using the fields below, set this value to $0**|
|RETAILPRICEEACH|Double||Retail price for each product. Do not multiply by PRODUCTQTY. Setting this value<br>to -1 will cause the system to use theprice configured in the catalog.|
|WHOLESALEPRICEEACH|Double||Wholesale price for each product. Do not multiply by PRODUCTQTY. Setting this<br>value to -1 will cause the system to use theprice configured in the catalog.|
|UPLINEVOLUMEEACH|Double||Upline (commissionable) volume for each product. Do not multiply by<br>PRODUCTQTY. Setting this value to -1 will cause the system to use the price<br>configured in the catalog.|
|PSVAMOUNTEACH|Double||PSV Amount for each product. Do not multiply by PRODUCTQTY. Setting this<br>value to -1 will cause the system to use theprice configured in the catalog.|
|ISFREEPRODUCT|Boolean||Flag to indicate if this is a free product. “True” = is a free product, “False” = not a<br>freeproduct|
|FREESHIPPING|Boolean||Flag to indicate if shipping charges should be suppressed for this product. “True”<br>= no shipping will be calculated, “False” = shipping charges will be calculated<br>normally.|



##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS,this node will contain the new OrderID created bythe system.|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 229 | 317 

Firestorm® Web Services API | Version 2.2.33 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 230 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormPartyWS.SavePartyGuest 

Creates or updates a party guest record in the system. This web service includes a special flag that will allow the caller to create a new guest record and assign it to a party in a single call. 

|Method Definitio<br>|n<br>||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|PartyGuestID||The ID number of the party guest that you wish to<br>edit. Set this value to -1 to create a new record|Numeric|-1 or actual ID|
|PartyHostID|Y|The ID number of the party host. This value must<br>already exist in the system and can be obtained (if<br>necessary)bycallingthe FindParty()web service.|Numeric||
|CompanyName|Y|Companyname toplace on theguest record|String||
|FirstName|Y|First name toplace on theguest record|String||
|LastName|Y|Last name toplace on theguest record|String||
|Address1|Y|Address line 1 toplace on theguest record|String||
|Address2|Y|Address line 2 toplace on theguest record|String||
|City|Y|Cityname toplace on theguest record|String||
|State|Y|2-char State ISO code toplace on theguest record|String||
|Zip|Y|Zip/Postal code toplace on theguest record|String||
|Country|Y|2-Char Country ISO code to place on the guest<br>record|String||
|Email|Y|Email Address toplace on theguest record|String||
|EmailOptOut|Y|Flag to control whether this guest can be emailed<br>(does not affect order receipts)|Boolean|True = opt out<br>False = do not opt<br>out|
|RaceID|Y|FK to tblRace. If you do not want to use this value,<br>create a record in tblRace called “Not Specified” and<br>use the ID value for that record.|Numeric||
|GenderID|Y|FK to tblGender. If you do not want to use this value,<br>create a record in tblGender called “Not Specified”<br>and use the ID value for that record.|Numeric||
|Phone|Y|Phone Number for theguest record|String||
|Birthdate|Y|Birthdate for the guest record|String|Must either be an<br>empty string (“”), or<br>a properly formatted<br>date value (i.e.:<br>MM/DD/YYYY)|
|AssignGuestToParty|Y|Flag to tell the system to assign the newly created<br>guest to the party identified in the argument<br>“PartyID”|Boolean|True = assign the<br>newly created guest<br>to the party<br>False = Do not assign<br>to aparty|
|PartyID|Y|The unique ID number assigned to the party. This ID<br>will be used to assign a newly created guest to this<br>party.|Integer|Any valid party ID<br>that exists in<br>Firestorm®|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 231 | 317 

Firestorm® Web Services API | Version 2.2.33 

This web service will allow a remote system to create or edit a party guest record in the Firestorm® system. 

By using the “Assign Guest to Party” and “PartyID” parameters, the system will create the guest record and will then assign it to the specified party. 

WARNING: If the assign guest to party action fails, the system will still create a party guest record. It will simply not be assigned to the party. This condition can be detected when the “FIRESTORMRESULT” node is set to “FAIL”, but an ID is present in the result envelope. 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS, this node will contain the PartyGuestID created or updated by the<br>system.|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 232 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormPartyWS.GetPartyHostDetail 

Retrieves all information stored in the system for the selected party host. Remember that in the Firestorm® system, a host is treated as a completely separate entity from the sponsoring consultant. 

As the host may or may not be a member themselves, their relationship to the sponsoring consultant must always be honored. The output from this web service will also include the sponsoring consultant’s ID and name. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|PartyHostID|Y|The ID of the host record being retrieved|Numeric|Any valid hostID. For a given<br>party, this value may be<br>obtained by calling<br>FirestormPartyWS.FindParty()|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

Remember that a party host in the Firestorm® system is a different entity than a consultant, customer or party guest. While it is possible for a party host to be any or all of those things, it does not matter in the context of this method. A party host is tracked in a separate table, and this method id to only way to access the host record. A party host does NOT have a DealerID. 

When calling this method, you will need to provide a valid PartyHostID as defined within Firestorm®. This value may be obtained in many different ways, but for a given party it is possible to get the required ID by first calling FirestormPartyWS.FindParty(), as the PartyHostID is returned as part of its results. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|PartyHostID|Integer|ID value of the requested host|
|SponsoringDealerID|Integer|DealerID of the sponsoring consultant that the requested host<br>is assigned to.|
|FirstName|String|First name of host|
|LastName|String|Last name of host|
|CompanyName|String|Companyname of host(if any)|
|Address1|String|Address line 1 of host|
|Address2|String|Address line 2 of host|
|City|String|Cityof host|
|State|String|State code of host|
|Zip|String|Postal code of host (international postal codes can be alpha<br>numeric)|
|Country|String|Countrycode of host|
|Email|String|Email address of host|
|Phone|String|Phone number of host|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 233 | 317 

Firestorm® Web Services API | Version 2.2.33 

|CreateDate|Datetime|Date and time the host record was created in the system|
|---|---|---|
|SponsorFirstName|String|Sponsoringconsultant’s first name|
|SponsorLastName|String|Sponsoringconsultant’s last name|
|SponsorCompanyName|String|Sponsoringconsultant’s companyname(if any)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 234 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormPartyWS.SavePartyHost 

Creates or updates a party host record in the system. Use this web method to create or edit a host record in the Firestorm® system. 

|Method Definitio<br>|n<br>||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|PartyHostID|Y|The ID number of the party host. To create a new<br>host record, simply pass in -1 in this field|Numeric|Existing PartyHostID<br>to perform an edit,<br>or -1 to have<br>Firestorm® create a<br>new host record.|
|SponsoringDealerID|Y|The dealer ID of the consultant who is sponsoring<br>this host.|Numeric|Any existing dealerID<br>in the system that is<br>an actual member<br>with a position in the<br>genealogytree.|
|CompanyName|Y|Companyname toplace on the host record|String||
|FirstName|Y|First name toplace on the host record|String||
|LastName|Y|Last name toplace on the host record|String||
|Address1|Y|Address line 1 toplace on the host record|String||
|Address2|Y|Address line 2 toplace on the host record|String||
|City|Y|Cityname toplace on the host record|String||
|State|Y|2-char State ISO code toplace on the host record|String||
|Zip|Y|Zip/Postal code toplace on the host record|String||
|Country|Y|2-Char CountryISO code toplace on the host record|String||
|Email|Y|Email Address to place on the host record (may be<br>blank)|String||
|Phone|Y|Phone number for the host(maybe blank)|String||
|Birthdate|Y|Birthdate for the host (may be blank)|String|Any valid date,<br>formatted<br>MM/dd/yyyy, or an<br>emptystring.|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This web service will allow a remote system to create or edit a party host record in the Firestorm® system. 

<u>Please note:  Firestorm® will not prevent duplicate host records from being created. Each host record is made</u> unique by its ID value. This is required because in reality, a given host has no affiliation with the sponsoring consultant, other than for a given party. This allows a host to be the hostess for different parties for different consultants at any time. 

##### **<u>Return Values</u>** 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 235 | 317 

Firestorm® Web Services API | Version 2.2.33 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|String||SUCCESS or FAIL|
|ID|Numeric||On SUCCESS, this node will contain the PartyHostID created or updated by the<br>system.|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|String||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 236 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormPartyWS.SaveParty 

Creates or updates a party record in the system. Use this web method to create or edit a party record in the Firestorm® system. 

|Method Definitio|n||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|PartyID|Y|The ID value of the party that you are trying to edit.<br>When creatinga newparty, pass in -1.|Numeric||
|PartyTypeID|Y|The ID value for the type of party this will be. These<br>values are defined in Firestorm® and can be<br>retrieved by calling<br>FirestormPartyWS.GetPartyTypeList()|Numeric|Any defined party<br>type ID|
|ParentID|Y|If this party is a BOOKING, this ID value is the original<br>PartyID that this current party was booked from.|Numeric|-1 if the new party is<br>not a booking. If it is<br>a booking, pass in<br>|
|||||theparent PartyID.|
|PartyStatusID|Y|The ID value for the status of this party. These values<br>are defined in Firestorm® and can be retrieved by<br>calling FirestormPartyWS.GetPartyStatusList().<br>NOTE: You may not send in a ststus of “CLOSED”<br>using this method. To close a party, you must make a<br>call to FirestormPartyWS.CloseParty().|Numeric|Typically, this will be<br>the status that<br>means “OPEN” on<br>your system. The<br>actual code you use<br>will depend on your<br>compensationplan.|
|PartyHostID|Y|The ID value of the party host. This ID must already<br>exist in the Firestorm® system.|Numeric|Any existing<br>PartyHostID|
|SendEmailInvite|Y|This flag will control the default “send e-vite”<br>behavior of Firestorm® whenever a guest is assigned<br>to this party.|Boolean|False = do not send<br>an e-vite<br>true = send an evite|
|CampaignID|Y|The Firestorm EmailCampaignID that contains the e-<br>vite that will be sent to any guest that is assigned to<br>the party when the “SendEmailInvite” flag is set to<br>true.|Numeric|Any existing<br>EmailCampaignID.|
|EventDate|Y|The date and time of the party|Datetime|Any valid date/time.<br>Typically<br>“MM/DD/YYYY<br>hh:mm:ss am/pm”|
|OpenDate|Y|The date thepartyrecord is created|Datetime||
|CloseDate|Y|The date the party was closed. When this date is in<br>the past, the system will stop taking orders for the<br>party.|Datetime||
|||Do not attempt to close a party with this field. Use<br>the FirestormPartyWS.CloseParty()method instead.|||
|LocationAddr1|Y|Address line 1 where thepartywill be held|String||
|LocationAddr2|Y|Address line 2 where thepartywill be held|String||
|LocationCity|Y|Cityname where thepartywill be held|String||
|LocationState|Y|State name where thepartywill be held|String||
|LocationZip|Y|Zip/Postal code where thepartywill be held|String||
|LocationCountry|Y|Countryname where thepartywill be held|String||
|LocationPhone|Y|Phone number of the host of theparty|String||
|EmailPersonalization|Y|If your company allows it and has the email template<br>set up for it, this parameter allows the host to<br>submit a personal message that will be included in<br>the e-vite|String||



##### **<u>Additional Restrictions Supported</u>** 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 237 | 317 

Firestorm® Web Services API | Version 2.2.33 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This method will allow you to create or edit a party record in the Firestorm® system. To successfully create a party, you must ensure you understand the flags this method to supports and how they relat to your compensation plan. 

WARNING: When performing a create or edit, **all** values must be supplied. Whatever you send in for each parameter WILL be written to the party record! If you do not want to supply a given parameter, simply pass in an empty string (“”). 

If you are trying to preserve data that is already on the party record, you will need to make a call to FirestormPartyWS.FindParty() to retrieve the existing record. You would then send the values you wish to keep back into this method. 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS,this node will contain the PartyID created or updated bythe system.|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 238 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormPartyWS.GetPartyTypeList 

Returns a dataset of all defined party types in the system. The PartyTypeIDs returned by this method will be used by other calls in this API. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|ShowActiveOnly|Y|Flag controlling whether or not the returned data<br>will contain only active party types|Boolean|false = Show all<br>records<br>true = Only show<br>active|
|UseDateFiltering|Y|Party types can be set up to only be active during a<br>given date range. When you use this flag, only those<br>party types that are active at the time of this call will<br>be returned.|Boolean|false = No date<br>filtering<br>true = Only show<br>party types that are<br>active now.|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This method will return all defined party type records in the system. This data can be used as parameters to other methods in this API. The data could also be used to display choices to the user if your interface requires it. 

##### <u>Date Filtering</u> 

The Firestorm® system allows party types to be set up in advance with a begin and end date so that a given party type will only be available between those dates. When using date filtering, it is possible for a party type that falls outside of the active period to not appear in the output of this web service. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|PartyTypeID|Integer|ID value of thepartytype.|
|Code|String|Short name for thepartytype|
|Description|String|Description of thepartytype|
|Active|Boolean|Flag indicating if this record is active and available for use.<br>TRUE = Active<br>FALSE = Inactivepartytype. Do not use.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 239 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormPartyWS.GetPartyStatusList 

Returns a dataset of all defined party statuses in the system. The PartyStatusIDs returned by this method will be used by other calls in this API. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|ShowActiveOnly|Y|Flag controlling whether or not the returned data<br>will contain only active party types|Boolean|false = Show all<br>records<br>true = Only show<br>active|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This method will return all defined party status records in the system. This data can be used as parameters to other methods in this API. The data could also be used to display choices to the user if your interface requires it. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|PartyStatusID|Integer|ID value of thepartytype.|
|Code|String|Short name for thepartytype|
|Description|String|Description of thepartytype|
|Active|Boolean|Flag indicating if this record is active and available for use.<br>TRUE = Active<br>FALSE = Inactivepartytype. Do not use.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 240 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormPartyWS.CloseParty 

Closes an open party in the system. This action will take the actions required to actually close the party in the Firestorm® system.  Once a party is closed, no further orders may be processed against the party and the party replicating website will no longer be available (if one was created). 

This method is the only valid way to close a party. Do not attempt to merely update the party status as this action is not allowed and will trigger an error. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|PartyID|Y|The ID value of the party that you are trying to close|Numeric|Any existing open<br>partyID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

Once a party is ready to be closed, a call to this method will close the party and remove it from availability to have orders placed against it. Once a party is closed, administrative processing will take over for order fulfillment or any other actions that are required to finalize the party. 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS,this node will contain the PartyID created or updated bythe system.|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 241 | 317 

Firestorm® Web Services API | Version 2.2.33 

### FirestormRecurringOrderWS 

|General Info|rmation|
|---|---|
|Name|FirestormRecurringOrderWS.asmx|
|WSDL||
|Description|Provides access into specific areas of the Firestorm® recurringorder subsystem.|



|Method Summary<br>||
|---|---|
|Method Name|Return Type|
|DeactivateRecurringOrder|Boolean|
|GetRecurringOrdersForDealer|Datatable|
|SaveRecurringOrder|String|
|SaveRecurringOrderPayment|String|
|GetRecurringOrdersByDealer|Datatable|
|GetRecurringOrderProductList|Datatable|
|GetRecurringOrderHistory|Datatable|
|GetRecurringOrderDetail|Datatable|
|GetRecurringOrder|Datatable|
|DeleteRecurringOrderPayment|String|
|DeleteRecurringOrderDetail|String|
|DeleteRecurringOrder|String|
|DeleteItemFromRecurringOrder|String|
|AddItemToRecurringOrder|String|
|ActivateTemplate|String|
|GetRecurringOrderPayment|DataTable|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 242 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### Recurring Order Status Codes 

The following codes are generated by the system whenever it attempts to process a template. Status codes can indicate error conditions that need to be addressed in order for the template to generate correctly. 

|Status Code|Meaning|
|---|---|
|BO|One or more products on the template would need to be backordered, and the product does not allow<br>backorders. Check “LastStatusMessage” for details.|
|CAT|No CatalogueID in on the header of the template.|
|CC|Credit card issue. Check “LastStatusMessage” for details.|
|COMPL|The order that would be generated by the template is not compliant with law. This code will only appear when<br>the system is configured to use ShipCompliant.(Typicallyleagallyrestrictedproducts like alcohol)|
|DFT|E-Check issue. Check “LastStatusMessage” for details.|
|FMT|Noproduct has been selected for the template|
|INV|Internal error has occurred. Check “LastStatusMessage” for details|
|NP|Nopayment information exists for the template|
|NSD|Next shipdate is not set on the template|
|OK|Template is readytogenerate a live order. No errors.|
|PTP|Payment type on the template is not configured in Firestorm® to be accepted for recurringorders|
|PTR|Payment type on the template is configured as a restrictedpayment type. Check “LastStatusMessage” for details|
|SD|The template was deactivated by the system. Typically this is caused by the retry count being exceeded. Check<br>“LastStatusMessage” for details|
|SEQ01|Sequentialproduct error. Check “LastStatusMessage” for details|
|SEQ02|Sequentialproduct error. Check “LastStatusMessage” for details|
|SEQCMP|For a sequentialproduct,the sequence is completed and no further shipments will occur|
|SS|Shippingzone error. Check “LastStatusMessage” for details|
|SYS|Generic code for an action taken bythe system. Check “LastStatusMessage” for details|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 243 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormRecurringOrderWS.DeactivateRecurringOrder 

Allows a remote system to deactivate a specific recurring order template (autoship) for a given Dealer. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The DealerID of the person that owns this recurring<br>order|Integer|Any valid DealerID|
|RecurringOrderID|Y|The unique ID assigned to the recurring order when<br>it was created|Integer|Any valid<br>RecurringOrderID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The Recurring Order must be assigned to the DealerID that was passed in through the web service. If it is not, the call will fail and the system will do nothing. 

If the recurring order ID is valid and it is owned by the Dealer, the system will deactivate the template and the order will no longer ship. The template will be set to the following values: 

Active = false 

Last Status Code = “UD” (User Deactivated) Last Status Message = “Order Deactivated” 

##### **<u>Return Values</u>** 

##### BOOLEAN 

True – The recurring order was deactivated successfully False – The system was not able to deactivate the autoship. Check the system logs to determine the problem. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 244 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormRecurringOrderWS.GetRecurringOrdersForDealer 

Returns a list of all recurring order templates (autoships) for a given dealer in the system. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|DealerID topull recurringorders for|Integer|Anyvalid DealerID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes – The shipping country from the recurring order must be in one<br>of the authorized countries.|
|Fields|yes|
|Max Records|yes|



##### **<u>Additional Information</u>** 

This web service will return a COMPLETE list of all recurring order template headers that are defined in the system for the requested DealerID. This includes all active and inactive templates. It is the responsibility of the caller to filter the list as required for their application. 

Please note that this web service will only return header information for a recurring order template and not the product details. In order to see product details use GetRecurringOrderDetail() on this web service. 

##### **<u>Return Values</u>** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|RecurringOrderID|Integer|The unique ID assigned to this template bythe system|
|ShipperID|Integer|The unique ID of the shipper(tblShipper.ShipperID)|
|DealerID|Integer|If this is a member recurring order, this is the DealerID of the<br>person who owns it. (If this is a customer recurring order, you<br>need to look at CustomerDealerID)|
|DealershipID|Integer|If this is a member recurring order, this is the Dealership that<br>will receive credit for this order when itgenerates|
|ShipCompany|String||
|ShipFirstName|String||
|ShipLastName|String||
|ShipAddress1|String||
|ShipAddress2|String||
|ShipCity|String||
|ShipState|String|Valid state code as defined in Firestorm®(tblState)|
|ShipPostalCode|String||
|ShipCountry|String|Valid countrycode as defined in Firestorm®(tblCountry)|
|Phone|String|Phone number on the template. No formatting is applied by<br>the system.|
|CreateDate|Date|The actual date that this template was created in the system|
|CreateBy|String|The user ID of theperson who created the template. If this<br>template was created in the administrative interface, this will<br>be the login ID of the user. If this template was created on the|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 245 | 317 

Firestorm® Web Services API | Version 2.2.33 

|||web,  this will be formatted as “WEB:XXXX” where XXXX is the<br>dealerID of theperson who created it|
|---|---|---|
|MaintDate|Date|.<br>The date that this record was last updated|
|MaintBy|String|The user ID of theperson who updated the template. If this<br>template was updated in the administrative interface, this will<br>be the login ID of the user. If this template was updated on<br>the web,  this will be formatted as “WEB:XXXX” where XXXX is<br>the dealerID of theperson who created it.|
|RecurringDay|Integer|The dayof the month that this order willgenerate(1-31)|
|RecurringFreq|Integer|“Months”, “Days” or “Weeks”. Used in conjunction with<br>RecurringUnit to calculate the next shipment date.|
|RecurringUnit|String|The number of RecurringFreq to use when calculating the<br>next shipment date|
|RecurringLastGeneratedDate|Date|The date that this template last generated a live order<br>successfully.|
|RecurringLastAttemptedDate|Date|The date that this template attempted to generate but failed<br>to do so. Used in conjunction with RetryCount to determine if<br>this order has exceed the maximum number of retries.|
|Pending|Boolean|When this flag is set to True, this template will not be<br>processed by the system, nor will it show up on the web site<br>in the member’s web office. As far as the user is concerned,<br>this recurring order no longer exists, because they can no<br>longer access it. This flag may only be “unset” by the<br>administrative interface.<br>0 = False|
|||Non-Zero - True|
|SpecialInstructions|String|Any special instructions that were applied to the template.<br>This value is copied to the special instructions field of any live<br>order that isgenerate from this order.|
|ReferringDealerID|Integer|If this is a customer recurring order, this is the DealerID of<br>that customer’s sponsor|
|ReferringDealershipID|Integer|If this is a customer recurring order, this is the DealershipID of<br>that customer’s sponsor. This is the dealership that will<br>receive credit for anylive ordergenerated from this template.|
|CatalogueID|Integer|The Firestorm® catalogthat this recurringorder is based on.|
|LastStatusCode|String|The last status code that was set when this template was last<br>processed.<br>The following values are possible:<br>NSD = Next Ship date not set<br>SD = System Deactivated<br>OK = Template is ready to process<br>SEQXX = Sequential autoship where XX in the sequence failed<br>NP =No payment information on record<br>DFT = Draft payment type error. Check status message for<br>actual error<br>CC = Credit card payment type error. Check status message<br>for actual error. (Credit card declines will show as this error)<br>PTR = Payment type is restricted (not allowed for recurring<br>orders)<br>PTP = Payment type is not accepted for recurring orders<br>CAT = No catalog number on record<br>SEQCMP = This is a sequential autoship that has completed its<br>sequence and was deactivated normally.<br>INV = Invalid format. Check status message for actual error<br>FMT = The template does not have any products selected<br>BO = Back order error. The autoship has products on it that<br>are out of stock and do not allow backorder.<br>SS = Unable to calculate shipping. See status message for<br>actual error<br>SYS = The recurring order could not be generated due to a<br>system error. Check status message for error|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 246 | 317 

Firestorm® Web Services API | Version 2.2.33 

|LastStatusMessage|String|Used in conjunction with “LastStatusCode”. This field will<br>contain the details to explain the code.|
|---|---|---|
|Active|Boolean|Flag to indicate whether or not this template is to be<br>processed. The dealer has control over this field through the<br>web tool (Recurring Order Portal).<br>0 = Not active<br>Non-Zero = Active|
|NextShipDate|Date|This is the date that this template will next be processed to<br>create a live order in the system.|
|RetryCount|Integer|The number of successive times this template has failed to<br>regenerate. This number is reset to 0 when the template<br>generates successfully. (When a template exceeds the<br>maximum number of retries allowed, the system will<br>deactivate the template and will no longerprocess it.)|
|CustomerDealerID|Integer|If this is a customer recurring order template, this is the<br>DealerID associated with that customer.|
|DisableWebEdits|Boolean|Flag to indicate if the owner of this template should be<br>allowed to edit it with the recurring order portal tool.<br>0 = Edits are allowed<br>Non-Zero = No edits are allowed on the web|
|ReinvestCommissions|Integer|Flag to indicate if the system should capture commissions to<br>pay for part or all of this recurring order.<br>O = Do not use commission<br>Non-Zero = Use commissions for payment when possible.<br>Otherwise,use the definedpayment type.|
|CommonName|String|A friendly name for this template. (i.e.: “My Monthly<br>Autoship”) This value is displayed in the Recurring Order<br>Portal tool.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 247 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormRecurringOrderWS.SaveRecurringOrder 

Saves or updates a recurring order template in the system. 

|Method Definiti|on|||
|---|---|---|---|
|Argument|Required<br>Description|Datatype|Valid Values|
|Token|Y<br>SecurityToken assigned toyou bysupport|String||
|Context|Y<br>Context value assigned toyou bysupport|String||
|RecurringOrderID|Y<br>The ID value of the recurring order template that<br>you are trying to update.|Numeric|-1 or a valid ID value<br>Passing -1 will create<br>a NEW template for<br>the dealer.|
|ShipperID|Y<br>Shipper ID from Firestorm|Numeric|Anyvalid ShipperID|
|DealerID|Y<br>DealerID of the person this template is for|Numeric|Any Valid member’s<br>DealerID|
|DealershipID|Y<br>The structure position (Dealership) that this<br>template will be created for|Numeric|If this is a member<br>recurring order, pass<br>in the dealershipID of<br>the structure<br>position that this<br>template will be<br>created for.<br>If this is a CUSTOMER<br>recurring order, pass<br>in -1.|
|ShipCompany|Y<br>ShippingAddress Element|String||
|ShipFirstName|Y<br>ShippingAddress Element|String||
|ShipLastName|Y<br>ShippingAddress Element|String||
|ShipAddress1|Y<br>ShippingAddress Element|String||
|ShipAddress2|Y<br>ShippingAddress Element|String||
|ShipCity|Y<br>ShippingAddress Element|String||
|ShipState|Y<br>ShippingAddress Element|String||
|ShipPostalCode|Y<br>ShippingAddress Element|String||
|ShipCountry|Y<br>ShippingAddress Element|String||
|Phone|Y<br>Phone number stored on the template|String||
|RecurringDay|Y<br>The day this order will generate|Numeric|1-31 depending on<br>the month. The<br>system will<br>automatically<br>account for months<br>with less than 31<br>days by adjusting the<br>date on the fly.|
|RecurringFreq|Y<br>The number per RecurringUnit this template will<br>ship.<br>_If a shipment will occur once per month, then you_<br>_would pass in:_<br>_RecurringFreq = 1_<br>_RecurringUnit = “M”_<br>WARNING: Please be aware that certain Frequency /<br>Unit combinations may be suppressed through<br>configurations in Firestorm. Make sure that what<br>you are passing in will be compatiable with the<br>client’s compensation plan.|Numeric||
|RecurringUnit|Y<br>The timeperiod a shipment will occur in|String|“D” – Days|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 248 | 317 

Firestorm® Web Services API | Version 2.2.33 

|||||”W” – Weeks<br>”M” - Months|
|---|---|---|---|---|
|Pending|Y||Numeric||
|SpecialInstructions|Y||String||
|ReferringDealerID|Y||Numeric||
|ReferringDealershipID|Y||Numeric||
|CatalogueID|Y||Numeric||
|Active|Y|-1 to cause the system to process this template<br>normally.<br>0 will prevent the recurring order from being<br>processed.|Boolean||
|NextShipDate|Y|This is the date that the recurring order template will<br>generate a live order|Date|Must be at least 1<br>dayin the future|
|CustomerDealerID|Y||Numeric||
|DisableWebEdits|Y|-1 to disallow edits from occurring in the members<br>web backoffice.<br>0 will allow edits in the web backoffice.|Numeric||
|ReinvestCommissions|Y|A flag to tell the system to use unpaid commissions<br>from the dealer’s commission account to pay for this<br>order.<br>NOTE: The system will use whatever commissions<br>are available and will charge the balance (if there is<br>one)to thepayment on file.|Numeric|-1 = Use commissions<br>0 = Do not use<br>commissions|
|CommonName|Y|Short name for this template. This is used by the<br>dealer in their web backoffice to help them identify<br>the specific recurring order (when there are multiple<br>orders defined)|String|Can be an empty<br>string (“”)|
|MinCyclesLeft|Y|The minimum number of times this recurring order<br>will generate. This number is decremented each<br>time an order is generated, until the count reaches<br>zero. Once at zero the template will be disabled and<br>will no longergenerate.|Numeric|-1 = Generate<br>forever<br>> 0, limit number of<br>generations to this<br>number.|
|MinRetailValue|Y|Minimum RETAIL value ofproducts on the template|Double||
|MinWholesaleValue|Y|Minimum WHOLESALE value of products on the<br>template|Double||
|MinUplineValue|Y|Minimum UPLINE value ofproducts on the template|Double||
|MinPSVValue|Y|Minimum PSV value ofproducts on the template|Double||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This function will create the header portion of a recurring order template. 

Be aware that in order for a recurring order to be created correctly and put into a state where it will actually generate a live order, the following steps must occur: 

##### 1. Call SaveRecurringOrder() 

##### 2. Call SaveRecurringOrderPayment() 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 249 | 317 

Firestorm® Web Services API | Version 2.2.33 

3. Call AddItemToRecurringOrder() for each product to be shipped 

4. Call ActivateTemplate() 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS, this node will contain the RecurringOrderID created or updated by the<br>system.|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 250 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormRecurringOrderWS.SaveRecurringOrderPayment 

Saves or updates a recurring order payment in the system. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|RecurringOrderID|Y|The ID value of the recurring order template that<br>you are trying to update.|Numeric|A valid<br>RecurringOrderID|
|RecurringOrderPaymentID|Y|The ID values of the recurring order payment that<br>you are trying to update|Numeric|-1 = Create a new<br>payment record<br>>0 = Update the<br>record represented<br>bythe ID|
|PaymentTypeID|Y|Payment Type ID from Firestorm|Numeric|Any valid<br>PaymentTypeID|
|DealerID|Y|DealerID of the person this template is for|Numeric|Any Valid member’s<br>DealerID|
|CCAcctNumber|Y|Credit card account number|String||
|CCExpiration|Y|Expiration date of the credit card|String|Use format<br>“MM/YYYY”|
|CCNameOnCard|Y|First and Last name of the cardholder|String||
|CVV2|Y|Deprecated. Any value passed in this argument<br>will NOT be saved.|String|Pass in an empty<br>string (“”)|
|BankRoutingNumber|Y|For e-check payments only. This is the routing<br>number of the bank|String||
|BankAccountNumber|Y|For e-checkpayments only. Bank account number|String||
|BankNameOnAccount|Y|For e-check payments only. The account style<br>(Name,etc)|String||
|BillCompany|Y|BillingAddress|String||
|BillFirstName|Y|BillingAddress|String||
|BillLastName|Y|BillingAddress|String||
|BillAddress1|Y|BillingAddress|String||
|BillAddress2|Y|BillingAddress|String||
|BillCity|Y|BillingAddress|String||
|BillState|Y|BillingAddress|String||
|BillPostalCode|Y|BillingAddress|String||
|BillCountry|y|BillingAddress|String||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This function will create the payment portion of a recurring order template. 

WARNING: Since you will be sending over payment information utilizing this web service, it is imperative that you use a secure connection when utilizing this web service. Make sure you adhere to all applicable PCI Compliance standards when handling credit card information. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 251 | 317 

Firestorm® Web Services API | Version 2.2.33 

SPECIAL NOTE: Firestorm® Payment types that have additional custom fields defined for them ARE NOT supported by this web service. 

Be aware that in order for a recurring order to be created correctly and put into a state where it will actually generate a live order, the following steps must occur: 

1. Call SaveRecurringOrder() 

2. Call SaveRecurringOrderPayment() 

3. Call AddItemToRecurringOrder() for each product to be shipped 

4. Call ActivateTemplate() 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ID|numeric||On SUCCESS, this node will contain the RecurringOrderID created or updated by the<br>system.|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 252 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormRecurringOrderWS.GetRecurringOrdersByDealer 

Retrieves all recurring order templates for a given DealerID. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|A member’s DealerID<br>You should pass a -1 in this field if you are<br>searching for a customer’s recurring orders, and<br>place the CustomerDealerID into the<br>“CustomerDealerID” field below.|Numeric|Any valid member<br>DealerID.|
|ShowActiveOnly|Y|Flag to suppress inactive templates|Boolean|-1 = show active<br>templates only<br>0 = Do not suppress<br>inactive templates|
|ShowPending|Y|Flag to allow you to retrieve recurring orders that<br>are in a pending status.<br>A recurring order can be in pending status if the<br>setup is not complete for the given template, OR if<br>the user chose to “delete” the template from the<br>web backoffice.|boolean|-1 = show pending<br>templates<br>0 = suppress pending<br>templates|
|CustomerDealerID|Y|A customer’s DealerID<br>Should only be used when searching for customer<br>recurring orders. If this field is used, the DealerID<br>field should contain a “-1”|Numeric|Any valid<br>CustomerDealerID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

This function will return a listing of all recurring order templates for a given DealerID. 

##### **<u>Return Values</u>** 

This function will return a set of data to the caller, with each row containing the following fields: 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|RecurringOrderID|Integer|The RecurringOrderID for the template|
|DisplayOrderID|Integer|Used for display in the web backoffice. You should have no<br>reason to use this value.|
|Shipper|String|The code representing the shipper used on this template (i.e.:<br>UPS,FEDEX,etc)|
|ShipperDescription|String|The description for the shipper as entered into Firestorm®|
|DealershipNumber|Integer|The number of the dealership this recurring order is assigned<br>ot.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 253 | 317 

Firestorm® Web Services API | Version 2.2.33 

|||Note: This is NOT the DealershipID. This is a sequential<br>number starting with “1” and continuing up (“2”, “3”, etc) for<br>the number ofpositions in the structure the dealer has.|
|---|---|---|
|RecurringDay|Integer|The day of the month that this template will generate an<br>order on.<br>Note: This day will be adjusted automatically if the recurring<br>day falls outside of a valid range for a given month. (i.e.:<br>RecurringDay is set to 31, but in Feburary there are only 29<br>days (or 28). In this scenario, the system will change the day<br>to the 29th)|
|CreateDate|DateTime|Timestampfor creation of the template|
|Active|Boolean|Flagto indicate if this template is active or not.<br>-1 = Active<br>0 = Not Active|
|LastStatusCode|String|A status code representing the result of processing the last<br>time this template was used to create a live order.<br>The following codes will be seen:<br>“OK” – Template is valid and ready to generate an order<br>“SD” – The system deactivated this template (see<br>LastStatusMessage for actual reason)<br>“NSD” – The next shipdate was not set up|
|LastStatusMessage|String|An English description of the reason the last status code was<br>generated|
|NextShipDate|DateTime|The next time this template willgenerate a live order|
|RecurringLastGeneratedDate|DateTime|The last time this templategenerated a live order|
|DisableWebEdits|Boolean|Flag to indicate if the user is allowed to edit this template in<br>their web backoffice.<br>-1 = No edits allowed<br>0 = Edits allowed|
|Upline|Double|The value of upline (CV) that this template will create when it<br>generates|
|Wholesale|Double|The Wholesale value that this template will create when it<br>generates|
|Retail|Double|The Retail value that this template will create when it<br>generates|
|PSV|Double|The value of PSV (QV) that this template will create when it<br>generates|
|ComboDisplay|String|A string to display in a combo box as a selection mechanism<br>for this template. Formatted as follows:<br>RecurringOrderID – Common Name – Status – Next Ship Date<br>This is the same string displayed in the members web<br>backoffice in the RecurringOrder Manager tool.|
|CommonName|String|A user entered short name for this template. Helps the<br>member differentiate between templates when they have<br>multiple templates set up.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 254 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormRecurringOrderWS.GetRecurringOrderProductList 

Retrieves all products from the specified catalog that are eligible to be placed onto a recurring order template. You can use the output of this web service to present a list of eligible products to the user that may be placed on autoship. 

|Method Definition|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|CatalogueID|Y|The catalogue ID from Firestorm® to search for<br>eligibleproducts|Numeric|Any valid<br>CatalogueID|
|TruncateDescription|Y|Flag to truncate product descriptions in the returm<br>datatable|Boolean|True = truncate<br>descriptions to the<br>number of<br>characters specified<br>in “TruncateLength”|
|TruncateLength|y|The number of characters to include in the<br>product description.<br>This argument is used in conjunction with the<br>“TruncateDescription” flag.|||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

This function will return a listing of all recurring order templates for a given DealerID. 

In order for a product to be included in this listing, the catalog must be flagged as “Eligible for Recurring Order” and each product must also be flagged as “Eligible for Recurring Order”. Failure to perform these steps will exclude that catalog / product from the listing output. 

##### **<u>Return Values</u>** 

This function will return a set of data to the caller, with each row containing the following fields: 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ProductID|Integer|ProductID from Firestorm®|
|ProductNumber|String|Product number as defined in Firestorm®|
|Name|String|Product Name(subject to truncation)|
|Description|String|Product Description(subject to truncation)|
|OutOfStock|Boolean|Flag to indicate if this product is out of stock in the inventory<br>system|
|Retail|Double|Retailprice of theproduct|
|Wholesale|Double|Wholesaleprice of theproduct|
|UplineAmount|Double|Upline value assigned to thisproduct(CV)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 255 | 317 

Firestorm® Web Services API | Version 2.2.33 

|PSVAmount|Double|PSV value assigned to thisproduct(QV)|
|---|---|---|
|SponsorBonus|Double|The amount of the configured sponsor bonus commission|
|CountsAsXUnits|Integer|The number of units purchasing this product counts as (This is<br>comp plan specific and should only be used after consulting<br>with our support department)|
|SponsorBonusProcedureName|String|Stored procedure to pay a sponsor bonus when this product is<br>purchased.|
|SponsorBonusClassName|String|Class name to use topaythe sponsor bonus|
|ProductCategoryID|Integer|ProductCategoryID as defined in Firestom®|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 256 | 317 

Firestorm® Web Services API | Version 2.2.33 

FirestormRecurringOrderWS.GetRecurringOrderHistory 

Retrieves all history records for the specified recurring order. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|RecurringOrderID|Y|The ID of the recurring order|Numeric|Any valid<br>RecurringOrderID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

This function will return a listing of all history records for the specified recurring order template. These are the same history records that are visible in the administrative client of Firestorm®. 

All history records will be returned in DESCENDING date order. This means the newest history record will be the first in the list. 

##### **<u>Return Values</u>** 

This function will return a set of data to the caller, with each row containing the following fields: 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|RecurringOrderHistoryID|Integer|Identityvalue of the historyrecord|
|Code|String|The short name of the type of history record. This will vary<br>widely by application and can change in the future as new<br>functionalities are introduced causing ned codes to be<br>introduced.|
|CreateDate|Datetime|The date and time the historyrecord was created|
|Comments|String|The actual comment for the action recorded by the history<br>record. Again, this comment can vary widely anddoes not<br>follow a standard format.|
|CreateBy|String|The user ID of the user or process that created the history<br>record.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 257 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormRecurringOrderWS.GetRecurringOrderDetail 

Returns full item detail for the selected recurring order. (This function will only return limited header information.) 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|RecurringOrderID|Y|The ID of the recurring order being requested|Numeric|Any valid<br>RecurringOrderID|
|ExcludeKitSelections|Y|Flag to exclude dynamic kit selections from the<br>output. The kit product WILL be included but not<br>the selections the user made to fill the kit.|Boolean|True = exclude kit<br>selections from<br>output<br>False – Kit selections<br>will be included.|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

This function will return a recordset containing all of the item detail (products) for the selected recurring order template. 

Remember that the actual products on a template can change based on user selections in their web backoffice. You should always pull the detail with this function every time you will be creating a live order from this template (if you do so). 

##### **<u>Return Values</u>** 

This function will return a set of data to the caller, with each row containing the following fields: 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|RecurringOrderDetailID|Integer|ID of the recurringorder template|
|ProductID|Integer|Product ID of theproduct|
|Qty|Integer|The number ofproducts desired|
|ProductNumber|String|Theproduct number from Firestorm® for thisproduct|
|Name|String|Theproduct name for thisproduct from Firestorm®|
|Discount|Double|The discount applied to theproduct|
|RetailPrice|Double|The retail price for the product from the catalog specified in<br>the header|
|WholesalePrice|Double|The wholesale price for the product from the catalog specified<br>in the header|
|UplineAmount|Double|The Upline amount (CV) for the product from the catalog<br>specified in the header|
|PSVAmount|Double|The PSV amount (QV) for the product from the catalog<br>specified in the header|
|SponsorBonus|Double|The amount of a sponsor bonus topay (if configured)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 258 | 317 

Firestorm® Web Services API | Version 2.2.33 

|CountsAsXUnits|Integer|The number of units that purchase of this product will count<br>as.<br>Note: This is comp plan specific. Make sure you consult with<br>approiatepersonnelprior to usingthis value.|
|---|---|---|
|SponsorBonusProcedureName|String|Storedprocedure topaythe sponsor bonus(if configured)|
|SponsorBonusClassName|String|Class name topaythe sponsor bonus(if configured)|
|ProductCategoryID|Integer|ID of the product category this product is assigned to in the<br>catalogspecified in the header|
|PointValue|Double|In the Firesotrm® points and rewards system, this is the<br>number of points that will be awarded when this product is<br>purchased.|
|SkipNextShipment|Boolean|Flag to indicate that the user does not want this product<br>shipped on the next live order generated from this template.<br>-1 = skip next shipment<br>0 = do not skip|
|Active|Boolean|Flagto indicate that this product is active and should ship<br>normally.|
|IsSequentialProduct|Boolean|Flag to indicate that this product is a sequential product.<br>Please refer to the Firestorm Use and Operation Manual for a<br>complete description of sequentialproducts.|
|MinRetailValue|Double|The sum of the products on this template must meet this<br>minimum retail value before it will create a live order. If<br>product selections fall below this value, the order will not<br>ship.|
|MinWholesaleValue|Double|The sum of the products on this template must meet this<br>minimum wholesale value before it will create a live order. If<br>product selections fall below this value, the order will not<br>ship.|
|MinUplineValue|Double|The sum of the products on this template must meet this<br>minimum upline (CV) value before it will create a live order. If<br>product selections fall below this value, the order will not<br>ship.|
|MinPSVValue|Double|The sum of the products on this template must meet this<br>minimum PSV (QV) value before it will create a live order. If<br>product selections fall below this value, the order will not<br>ship.|
|ParentRecurringOrderDetailID|Integer|When the product is a kit selection, this is the<br>RecurringOrderDetailID that contains theparent kit.|
|KitSelection|Boolean|Flagto indicate that thisproduct is a kit selection|
|PictureURL|String|URL to theproduct image<br>Note: This may be a fully qualified URL or a relative URL<br>dependingon companyrequirements.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 259 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormRecurringOrderWS.GetRecurringOrder 

Returns all header detail for the selected recurring order. This function will not return item detail information. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|RecurringOrderID|Y|The ID of the recurring order being requested|Numeric|Any valid<br>RecurringOrderID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

This function will return a recordset containing all of the header detail for the selected recurring order template. 

##### **<u>Return Values</u>** 

This function will return a set of data to the caller, with each row containing the following fields: 

|Returned Data|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|RecurringOrderID|Integer|ID of the template|
|ShipperID|Integer|ID of the shipper assigned to this template|
|DealerID|Integer|ID of the member who owns this template. If this is a<br>customer template,this value will be -1|
|DealershipID|Integer|ID of the structure position (dealership) that will receive credit<br>when this templategenerates a live order.|
|ShipCompany|String|ShippingAddress element|
|ShipFirstName|String|ShippingAddress element|
|ShipLastName|String|ShippingAddress element|
|ShipAddress1|String|ShippingAddress element|
|ShipAddress2|String|ShippingAddress element|
|ShipCity|String|ShippingAddress element|
|ShipState|String|ShippingAddress element|
|ShipPostalCode|String|ShippingAddress element|
|ShipCountry|String|ShippingAddress element|
|Phone|String|Phone number for this order. Willprint on shippingorder.|
|CreateDate|Datetime|Date and time the template was created|
|CreateBy|String|Login ID of theperson orprocess that created this template|
|MaintDate|Datetime|Date and time this template was last changed|
|MaintBy|String|Login ID of the person or process that last changes this<br>template|
|RecurringDay|Integer|The day of the month that this template will generate alive<br>order on|
|RecurringFreq|Integer|The number of times or “RecurringUnit” that this template<br>will create an order.<br>(i.e.: To ship an order once per month, “RecurringFreq” would<br>be set to 1,and “RecurringUnit” would be set to “M”)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 260 | 317 

Firestorm® Web Services API | Version 2.2.33 

|RecurringUnit|String|The unit of time that will control generation of live orders.<br>The following values are valid:<br>“M” – Months<br>“W” – Weeks<br>“D” – Days|
|---|---|---|
|RecurringLastGeneratedDate|Datetime|Date and time this template last successfully generated a live<br>order|
|RecurringLastAttemptedDate|Datetime|Date and time the system attempted togenerate a live order|
|Pending|Boolean|Flag to indicate that this template is currently being built by<br>the system. If this flag is set, DO NOT USE THIS TEMPLATE.|
|||-1 = Pending<br>0 = Notpending|
|SpecialInstructions|String|Special instructions as entered by the template owner. These<br>instructions will appear on the shippingorder.|
|ReferringDealerID|Integer|When this is a customer template, this is the DealerID of that<br>customers sponsor|
|ReferringDealershipID|Integer|When this is a customer template, this is the ID of the<br>structure position owned by the ReferingDealerID that will<br>receive credit when this templategenerates a live order.|
|CatalogueID|Integer|ID of the catalogfor this template|
|LastStatusCode|String|A status code that results from thelast attempt to create a live<br>order.|
|||See “Recurring Order Status Codes” in this document for a<br>current listingof codes.|
|LastStatusMessage|String|The message generated by the system for the code contained<br>in “LastStatusCode”. This message will have additional<br>information in it for troubleshooting purposes.|
|Active|Boolean|Flag to indicate if this template is active and recady to<br>generate<br>-1 = Active<br>0 = Not active|
|||Note: If a template is not active it should not be used!|
|NextShipDate|Datetime|System calculated date that this template will next generate a<br>live order.|
|RetryCount|Integer|If the event of a failure to generate (i.e.: Credit card decline)<br>the counter is incremented by one for each failure. When the<br>order generates successfully, this count is reset to 0.|
|||When the RetryCount exceeds the configured number<br>(default is 3) of maximum consecutive retries, the system will<br>deactivate this template and no further attempts will be<br>made.|
|CustomerDealerID|Integer|If this is a customer template, this will contain the DealerID of<br>the customer.|
|DisableWebEdits|Boolean|Flag to indicate whether or not this template may be edited in<br>the web backoffice.<br>-1 = All edits are DISABLED<br>0 = Edits are allowed|
|||WARNING: The web tool to perform edits on a template can<br>be configured to allow edits on only parts of a template.<br>Check with support to determine how your system is<br>confiured|
|ReinvestCommissions|Boolean|g.<br>Flag to indicate that the owner of this template wishes to use<br>unpaid commission (when available) to pay for this order<br>when it generates.|
|||Note: Partial payments are possible. The system will use<br>whatever commission are available. Once the commission is<br>exhausted, the balance will be charged to the payment<br>method on file with the template.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 261 | 317 

Firestorm® Web Services API | Version 2.2.33 

|CommonName|String|The short name that the owner of the template has assigned<br>to help them know which template this is. This is valuable<br>when a single person has multiple templates for different<br>purposes. (i.e.: “My Qualification Autoship”). The user will see<br>this value in the web backoffice.|
|---|---|---|
|MinRetailValue|Double|The sum of the products on this template must meet this<br>minimum retail value before it will create a live order. If<br>product selections fall below this value, the order will not<br>ship.|
|MinWholesaleValue|Double|The sum of the products on this template must meet this<br>minimum wholesale value before it will create a live order. If<br>product selections fall below this value, the order will not<br>ship.|
|MinUplineValue|Double|The sum of the products on this template must meet this<br>minimum upline (CV) value before it will create a live order. If<br>product selections fall below this value, the order will not<br>ship.|
|MinPSVValue|Double|The sum of the products on this template must meet this<br>minimum PSV (QV) value before it will create a live order. If<br>product selections fall below this value, the order will not<br>ship.|
|MinCyclesLeft|Integer|This number indicates the minimum number of times this<br>template must generate a live order before the owner may<br>disable it in their web office.|
|TempOrder|Boolean|Flag to indicate that this template NOT to be used. If this flag<br>is set, DO NOT USE.<br>-1 = This is a temp order. Do not use.<br>0 = Not a temporder.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 262 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormRecurringOrderWS.DeleteRecurringOrderPayment 

Deletes a recurring order payment from the selected template in the system. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|RecurringOrderPaymentID|Y|The ID values of the recurring order payment that<br>you are trying to update|Numeric|Any valid<br>RecurringOrderPaymentID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This function will delete a payment information record from the system. 

To obtain the proper RecurringOrderPaymentID, use the web service GetRecurringOrderPayment() and pass in the RecurringOrderID. That call will return a list of all payment records assigned to the template. 

Be aware that if you leave a template in the system with no payment information, the template will fail with an error the next time it attempts to generate a live order. 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 263 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormRecurringOrderWS.DeleteRecurringOrderDetail 

Deletes all product selections from the selected template in the system. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|RecurringOrderID|Y|The ID value of the recurring whose details you are<br>trying to delete.|Numeric|Any valid<br>RecurringOrderID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This function will delete all product selections from the specified template. 

Be aware that if you leave a template in the system with no product selection information, the template will fail with an error the next time it attempts to generate a live order. 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 264 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormRecurringOrderWS.DeleteRecurringOrder 

Deletes the selected template from the system. All associated records will also be deleted (Payment, History, Detail and Question/Answers) 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|RecurringOrderID|Y|The ID value of the recurring whose details you are<br>trying to delete.|Numeric|Any valid<br>RecurringOrderID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This function will delete the specified template from the system as well as all associated records. This action is permanent and may not be undone. 

NOTE: If you are only attempting to deactivate a template so it will no longer generate live orders, you should make a call to DeactivateTemplate() instead. 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 265 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormRecurringOrderWS.DeleteItemFromRecurringOrder 

Deletes the selected template from the system. All associated records will also be deleted (Payment, History, Detail and Question/Answers) 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|RecurringOrderDetailID|Y|The ID of the detail to be deleted|Numeric|Any valid<br>RecurringOrderDetailID|
|RecurringOrderID|Y|The ID value of the recurring order whose details<br>you are trying to delete.|Numeric|Any valid<br>RecurringOrderID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This function will delete a single product detail record from a template. 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 266 | 317 

Firestorm® Web Services API | Version 2.2.33 

FirestormRecurringOrderWS.AddItemToRecurringOrder 

Adds a single product detail record to a template. 

|Method Definition|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|RecurringOrderID|Y|The ID value of the recurring order you are<br>trying to add an item to.|Numeric|Any valid<br>RecurringOrderID|
|ProductID|Y|ID from Firestorm® for the product you wish to<br>add|Numeric|Any valid ProductID<br>from Firestorm®|
|Qty|Y|The quantity of the requested product to add to<br>the template|Numeric|Any number > 0<br>Note: Other<br>configurations in the<br>system can affect the<br>actual quantity of a<br>given product (see<br>notes below)|
|Discount|Y|The amount of discount to apply to the product|Double|Entered as a<br>percentage. 0 - .1|
|ProductCategoryID|y|The ID from Firestorm® of the product category<br>assigned to thisproduct||Any valid<br>ProductCategoryID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This function will add a single product detail record to a template. 

Quantity may be limited by other configurations in the system. You will need to check with the system administrator to see if MaxQty has been set for a given product is you encounter any errors. 

A recurring order template may only have ONE sequential product on it at a time. If you attempt to add an additional sequential product, you will receive an error and the call will fail. 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred duringthe call,which will coorelate directlyto the number of|
||C o p y r|i g h t 2 0|1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c .P a g e267 | 317|



Firestorm® Web Services API | Version 2.2.33 

|||<ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|---|---|---|
|ERRORMSG|string|For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 268 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormRecurringOrderWS.ActivateTemplate 

Activates the selected template in the system and flags it as ready for processing. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|RecurringOrderID|Y|The ID value of the recurring order you are<br>trying to activate.|Numeric|Any valid<br>RecurringOrderID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This function will activate (sets the “Active” flag) the selected recurring order template and make it ready to be processed on the next run by the system. 

If a template is not activated, it will never be picked up for processing. 

Users have the ability control the active flag through their web backoffice if the system is configured to allow it. 

##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will coorelate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 269 | 317 

Firestorm® Web Services API | Version 2.2.33 

FirestormRecurringOrderWS.GetRecurringOrderPayment 

Retrieves all history records for the specified recurring order. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|RecurringOrder|||||
|RecurringOrderID|Y|The ID of the recurring order|Numeric|Any valid<br>RecurringOrderID|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes|
|Fields|Yes|
|Max Records|Yes|



##### **<u>Additional Information</u>** 

This function will return a listing of the payment record for the requested recurring order template. 

There will never be more than a single payment record for a template. 

NOTE: All sensitive payment fields (i.e.: account numbers, etc) have been removed from the output of this web service for PCI Compliance reasons. 

If a recurring order fails to generate due to inability to collect payment (i.e.: credit card decline), the system will attempt to collect “MaxRetry” times (a configuration parameter). If it still cannot collect, the system will deactivate the template and will no longer attempt to process the template. 

##### **<u>Return Values</u>** 

This function will return a set of data to the caller, with each row containing the following fields: 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|RecurringOrderPaymentID|Integer|The ID value of thepayment record|
|RecurringOrderID|Integer|The ID value of the recurring order template this payment<br>belongs to|
|PaymentTypeID|Integer|The ID of thepayment type as defined in Firestorm®|
|CCExpiration|String|Expiration date of the credit card|
|CCNameOnCard|String|Name on the credit card|
|CVV2|String|This field will always be blank. PCI Compliance rules do not<br>allow the storage of CVV2|
|BankNameOnAccount|String|The account as styled with the bank. Typically this will contain<br>either the company name or the First and Last name of the<br>account holder.|
|BillCompany|String|BillingAddress Element|
|BillFirstName|String|BillingAddress Element|
|BillLastName|String|BillingAddress Element|
|BillAddress1|String|BillingAddress Element|
|BillAddress2|String|BillingAddress Element|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 270 | 317 

Firestorm® Web Services API | Version 2.2.33 

|BillCity|String|BillingAddress Element|
|---|---|---|
|BillState|String|BillingAddress Element|
|BillPostalCode|String|BillingAddress Element|
|BillCountry|String|BillingAddress Element|
|CreateDate|Datetime|Date and time thispayment record was created|
|CreateBy|String|Login ID of the person or process that created the payment<br>record|
|MaintDate|Datetime|Date and time thispayment record was last modified|
|MaintBy|String|Login ID of the person or process that last modified the<br>payment record|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 271 | 317 

Firestorm® Web Services API | Version 2.2.33 

### FirestormShoppingCartWS 

|General Info|rmation|
|---|---|
|Name|FirestormShoppingCartWS.asmx|
|WSDL|https://www.firestormwebservices.com/FirestormWebServices/FirestormShoppingCartWS.asm<br>x|
|Description|Provides external systems with the abilityto manage basic shoppingcart configurations.|



|Method Summary||
|---|---|
|Method Name|Return Type|
|AssignShoppingCartGrouping|Complex XML Document|
|UnAssignShoppingCartGrouping|Complex XML Document|
|GetShoppingCartMasterGroupCodes|DataTable|
|GetShoppingCartLevel1GroupCodes|DataTable|
|GetShoppingCartLevel2GroupCodes|DataTable|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 272 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.AssignShoppingCartGrouping 

This method will allow a remote caller to add or update a catalogue specific shopping cart grouping for a product. This will allow the product to be visible in the shopping cart in the specified grouping. A product may have multiple grouping configurations in a single catalogue so that it can be seen in more than one area of the shopping cart. However, each grouping must be unique. 

|Method Definition|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|CatalogueID|Y|The ID of the catalogue to apply the configuration to|Integer|Any valid<br>CatalogueID|
|ProductID|Y|The ID of theproduct to applythe configuration to|Integer|Anyvalid ProductID|
|ShoppingCartMasterGroupCode|Y|The code of the Master Group to assign this product<br>to.|String|Any valid Master<br>Group Code that is<br>assigned to the<br>specified Catalogue<br>ID|
|ShoppingCartGroupCode_Level1|Y|The code of the Level 1 Group to assign this product<br>to.|String|Any valid Level 1<br>Shopping Cart Group<br>Code|
|ShoppingCartGroupCode_Level2|Y|The code of the Level 2 Group to assign this product<br>to.|String|Any Valid Level 2<br>Shopping Cart Group<br>Code|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The combination of ShoppingCartMasterGroupCode, ShoppingCartGroupCode_Level1, and ShoppingCartGroupCode_Level 2 will dictate exactly where in the shopping cart a product will be visible. A product can have multiple grouping assignments in a single catalogue to allow for the product to be visible in multiple parts of the shopping cart. However, the combination of the 3 group codes must be unique within each catalogue. 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 273 | 317 

Firestorm® Web Services API | Version 2.2.33 

Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 274 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormInventoryWS.UnAssignShoppingCartGrouping 

This method will allow a remote caller to remove a catalogue specific shopping cart grouping for a product. This will cause the product to no longer be visible in the shopping cart in the specified grouping. 

|Method Definition|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|CatalogueID|Y|The ID of the catalogue to apply the configuration to|Integer|Any valid<br>CatalogueID|
|ProductID|Y|The ID of theproduct to applythe configuration to|Integer|Anyvalid ProductID|
|ShoppingCartMasterGroupCode|Y|The code of the Master Group to remove this<br>product from.|String|Any valid Master<br>Group Code that is<br>assigned to the<br>specified Catalogue<br>ID|
|ShoppingCartGroupCode_Level1|Y|The code of the Level 1 Group to remove this<br>product from.|String|Any valid Level 1<br>Shopping Cart Group<br>Code|
|ShoppingCartGroupCode_Level2|Y|The code of the Level 2 Group to remove this<br>product from.|String|Any Valid Level 2<br>Shopping Cart Group<br>Code|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

##### Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 275 | 317 

Firestorm® Web Services API | Version 2.2.33 

|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|---|---|---|---|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 276 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormShoppingCartWS.GetShoppingCartMasterGroupCodes 

Returns a datatable containing all Shopping Cart Master Group Codes in the system. 

|Method Definition<br>Argument|Required|Description|Datatype|Valid Values|
|---|---|---|---|---|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Return Values</u>** 

|Returned Data - Default<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ShoppingCartMasterGroupID|Integer|The ID value of the mastergroupcode.|
|CatalogueID|Integer|The Catalogue ID assigned to this mastergroupcode.|
|Code|String|The displayed code of the mastergroupin the shoppingcart.|
|Description|String|The description of the shoppingcart mastergroup.|
|Active|Integer|A flag indicating whether or not the master group is active. 0 =<br>False,Non-Zero = True.|
|DisplayOrder|Integer|A numeric value indicating the order in which the master<br>groupis to be displayed in the shoppingcart.|
|IsMegaMenu|Integer|A flag indicating whether or not the master group is<br>configured as a mega menu. 0 = False,Non-Zero = True.|
|IsHomeMenu|Integer|A flag indicating whether or not the master group is<br>configured as the home menu. 0 = False,Non-Zero = True.|
|IsContentMenu|Integer|A flag indicating whether or not the master group is<br>configured as a content menu. 0 = False,Non-Zero = True.|
|LanguageCode|String|The code of the language assigned to this mastergroup.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 277 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormShoppingCartWS.GetShoppingCartLevel1GroupCodes 

Returns a datatable containing all Shopping Cart Level 1 Group Codes in the system. 

|Method Definition<br>Argument|Required|Description|Datatype|Valid Values|
|---|---|---|---|---|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Return Values</u>** 

|Returned Data - Default<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ShoppingCartGroupCodeID|Integer|The ID value of the shoppingcartgroupcode.|
|Code|String|The displayed code of thegroupcode in the shoppingcart.|
|Description|String|The description of the shoppingcartgroupcode.|
|Level|Integer|The defined level of the shopping cart group code. Will always<br>be “1”.|
|DisplayOrder|Integer|A numeric value indicating the order in which the master<br>groupis to be displayed in the shoppingcart.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 278 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormShoppingCartWS.GetShoppingCartLevel2GroupCodes 

Returns a datatable containing all Shopping Cart Level 2 Group Codes in the system. 

|Method Definition<br>Argument|Required|Description|Datatype|Valid Values|
|---|---|---|---|---|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Return Values</u>** 

|Returned Data - Default<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ShoppingCartGroupCodeID|Integer|The ID value of the shoppingcartgroupcode.|
|Code|String|The displayed code of thegroupcode in the shoppingcart.|
|Description|String|The description of the shoppingcartgroupcode.|
|Level|Integer|The defined level of the shopping cart group code. Will always<br>be “2”.|
|DisplayOrder|Integer|A numeric value indicating the order in which the master<br>groupis to be displayed in the shoppingcart.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 279 | 317 

Firestorm® Web Services API | Version 2.2.33 

### FirestormWebWS 

|General Infor|mation<br>|
|---|---|
|Name|FirestormWebWS.asmx|
|WSDL|https://www.firestormwebservices.com/FirestormWebServices/FirestormWebWS.asmx|
|Description|Provides external systems with the ability to manage and authenticate access to the Firestorm®<br>system.|



|Method Summary<br>||
|---|---|
|Method Name|Return Type|
|UpdateWebPassword|Boolean|
|UpdateDealerURL|Boolean|
|AuthenticateLogin|Boolean|
|AuthenticateSession|Boolean|
|UpdateDealerWebGreeting|Boolean|
|UpdateDealerWebAccess|Complex XML Document|
|AssignDealerWebOption|Complex XML Document|
|UnAssignDealerWebOption|Complex XML Document|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 280 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormWeb.UpdateWebPassword 

Allows a remote system to update the password on the dealer’s account. 

WARNING: This web service should only be used over a secure connection (https) when in production, as you will be sending the password in clear text. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The dealerID of the person whose password is being<br>updated|Integer|Any valid DealerID|
|CurrentPassword|Y|Thepassword as it currentlyexists|String||
|NewPassword|Y|The newpassword|String||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The system will validate the current password on the account before performing any update. If the current password is valid, the system will perform the update as requested. The new password is effective immediately. 

Please note that password complexity requirements as configured in Firestorm® will be enforced on the new password. If complexity requirements are not met, the call will fail with a FALSE return, but the error will be logged internally. 

##### **<u>Return Values</u>** 

##### BOOLEAN 

True – The password as updated successfully and is immediately active for the account. False – The validation failed or a system error occurred. Check the logs for details on the failure. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 281 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormWebWS.UpdateDealerURL 

Allows the replicated website URL to be updated. This value is also commonly used as a “user name” for login purposes in the members virtual web back office. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The dealerID of the person whose URL is being<br>updated|String|Any valid DealerID|
|DealerURL|Y|The NEW url desired|String|Any string. Special<br>characters and<br>spaces are not<br>allowed.|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The term “URL” is not completely accurate, and stems from the fact that this value is used as part of the overall system URL to make up the unique dealer specific URL for accessing a dealer’s replicated website. Depending on how the DNS record is set up for your particular system, either of the following two forms will work: 

http://www.mycompany.com/steve -OR - http://steve.mycompany.com 

In both cases, the value “steve” would be stored in the DealerURL field in the database. As this value is unique in the system, it may be used to map directly to an actual DealerID. Once you have the DealerID, you can access any information required about that person. 

The DealerURL parameter must be unique in the system. When passed in, the system will perform a search to see if the requested URL is already in use. If it is, the update will be disallowed. 

_Note: Simply assigning a DealerURL to a dealer’s record will not activate a replicated website. Please refer to the Firestorm® Use and Operations manual for all the steps required to completely set up a replicated website._ 

##### **<u>Return Values</u>** 

BOOLEAN 

True – The dealer record was updated successfully. The new DealerURL is active immediately. False – The dealer record could not be updated. The old DealerURL is still active. Check system logs for failure 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 282 | 317 

Firestorm® Web Services API | Version 2.2.33 

reason. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 283 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormWebWS.AuthenticateLogin 

Allows an external system to authenticate a login/password combination against the Firestorm® database. If your external system has a login capability and Firestorm is the system of record, then you should be using this call to perform all validations against the Firestorm database. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|C|The ID of the dealer logging into the system. If you<br>want to log in with the DealerURL, pass a -1 in this<br>field.|||
|DealerURL|C|The value from the DealerURL (aka user name) on<br>the dealer’s record. If this parameter is not supplied,<br>DealerID is required.|||
|Password|Y||||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

The system will search for the dealer record first by DealerID, or if that is not supplied, by DealerURL. Both of these values are unique in the system. If the record is found, the provided password is checked against the password on file in the system. If they match, the call will return a TRUE value. If they do not match, or an error occurred, the call will return a FALSE value. 

This web service will fail silently (FALSE) even if an error occurs. This is by design and is for security purposes. 

Be aware that the dealer has the capability to change their password or DealerURL at any time in their virtual web office. You should never store these values on your own system, as in almost all cases, Firestorm® is considered the system of record. 

##### **<u>Return Values</u>** 

BOOLEAN 

True – Password was authenticated successfully. False – The password did not match or an error occurred. Check the system logs for details. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 284 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormWebWS.AuthenticateSession 

This call is used as a callback into the Firestorm® system to authenticate an outbound seamless login request that is originating from Firestorm to the external system. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The dealer ID that initiated the session|Integer|Anyvalid DealerID|
|SessionIDToValidate|Y|The SessionID sent to your system from Firestorm®|String|This value is passed<br>to your system on<br>the querystring as<br>parameter “s”|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

When a user is logged into the Firestorm web virtual office, and initiates a connection to your external website, your site will be opened in a special I-FRAME that will pass several parameters to your system. Once of these is the current session ID that is active on our server. This web service will allow you to pass that session ID back to our system to validate that it is real, and is currently active. 

A session will be considered active for a period of 1 hour from the time it was last accessed by the user. 

This facility is also available to users of the shopping cart. Please refer to the “Implementing Seamless Login” documentation for complete details on using this capability. 

##### **<u>Return Values</u>** 

##### BOOLEAN 

##### True – The session is valid and active 

False – The session could not be validated. Errors are suppressed. Check the system logs to see details as to the reason for failure. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 285 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormWebWS.UpdateDealerWebGreeting 

This method will allow a remote caller to update the personal greeting of a member. This greeting is shown on the replicated website of the member (if the company allows) 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The dealer ID that initiated the session|Integer|Anyvalid DealerID|
|WebGreetingtext|Y|The text that the member wants displayed on their<br>replicated website|String||



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Dealer’s MailCountry must be in an authorized country for the<br>caller)|
|Fields|Yes|
|Max Records|No|



##### **<u>Additional Information</u>** 

The system allows a member to stare a personal greeting (or testimonial) in the database for use on their replicated website. When this call is used, the passed in text is used to replace the greeting currently stored in the system for this dealer. 

This field supports Unicode, and you may embed HTML elements in the text as long as the tags <HTML> and <BODY> are not used. 

##### **<u>Return Values</u>** 

BOOLEAN 

True – The greeting was updated successfully. 

False – The update failed. All errors are suppressed. Check the system logs for details on the failure. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 286 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormWebWS.UpdateDealerWebAccess 

This method will allow a remote caller to enable or disable to web login access of a specified dealer. This is used to control whether or not a dealer can log in to the system. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The dealer ID that initiated the session|Integer|Anyvalid DealerID|
|AllowWebAccess|Y|A boolean value indicating whether or not the<br>specified dealer mayloginto the system|Boolean|True/False|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Dealer’s MailCountry must be in an authorized country for the<br>caller)|
|Fields|Yes|
|Max Records|No|



##### **<u>Additional Information</u>** 

If a value of False is passed for the AllowWebAccess parameter, the dealer specified in the DealerID parameter will no longer be able to log in to the system. This includes both the Firestorm Backoffice as well as the Firestorm Shopping Cart. 

This method should be used with caution, as it will completely restrict the specified dealer from being able to log in to the system. 

If a value of True is passed for the AllowWebAccess parameter, the dealer will have their login access restored and will once again be able to log in to the Firestorm Backoffice as well as the Firestorm Shopping Cart. 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
</FIRESTORMRESULT>
```

The definition of each element is listed in the table below: 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 287 | 317 

Firestorm® Web Services API | Version 2.2.33 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 288 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormWebWS.AssignDealerWebOption 

This method will allow a remote caller to assign a known Firestorm web option to a specified dealer. Assigning a web option to a dealer will enable the functionality that corresponds with the web option code that is passed to this method. For a complete list of available web option codes and their corresponding functionality, please contact Firestorm Support. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The dealer ID that initiated the session|Integer|Anyvalid DealerID|
|WebOptionCode|Y|A Web Option Code value that exists in Firestorm|String|Any valid Web<br>Option Code<br>configured in<br>Firestorm|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Dealer’s MailCountry must be in an authorized country for the<br>caller)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This method will assign the specified Web Option Code to the specified dealer, if the Web Option Code exists in the Firestorm system. This can be used to control a dealer’s access to replicated website functionality as well as email communication functionality. 

For a complete list of available web option codes and their corresponding functionality, please contact Firestorm Support. 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

##### Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
```

```
</FIRESTORMRESULT>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 289 | 317 

Firestorm® Web Services API | Version 2.2.33 

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 290 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormWebWS.UnAssignDealerWebOption 

This method will allow a remote caller to remove a known Firestorm web option to a specified dealer. Removing a web option from a dealer will disable the functionality that corresponds with the web option code that is passed to this method. For a complete list of available web option codes and their corresponding functionality, please contact Firestorm Support. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The dealer ID that initiated the session|Integer|Anyvalid DealerID|
|WebOptionCode|Y|A Web Option Code value that exists in Firestorm|String|Any valid Web<br>Option Code<br>configured in<br>Firestorm|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|Yes (Dealer’s MailCountry must be in an authorized country for the<br>caller)|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This method will remove the specified Web Option Code to the specified dealer, if the Web Option Code exists in the Firestorm system and it is assigned to the specified dealer. This can be used to control a dealer’s access to replicated website functionality as well as email communication functionality. 

For a complete list of available web option codes and their corresponding functionality, please contact Firestorm Support. 

##### **<u>Return Values</u>** 

This web service returns a complex XML document that will describe the result of the call.  The XML document is described below, along with an example. 

##### Return XML: 

```
'/////////////////////
'// Return XML
'/////////////////////
<?xml version='1.0' encoding='utf-8' ?>
<FIRESTORMRESULT>
<STATUS>string</STATUS>
<ERRORS errorcount='0'>
<ERRORMSG>String</ERRORMSG>
</ERRORS>
```

```
</FIRESTORMRESULT>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 291 | 317 

Firestorm® Web Services API | Version 2.2.33 

The definition of each element is listed in the table below: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|FIRESTORMRESULT|n/a||Containingenvelope for the result document|
|STATUS|string||SUCCESS or FAIL|
|ERRORS|n/a|Errorcount|Containing envelope for errors. The attribute “errorcount” will be set to the number<br>of errors that occurred during the call, which will correlate directly to the number of<br><ERRORMSG> elements that will be present. All argument validation errors will be<br>returned in this manner|
|ERRORMSG|string||For each failure that occurred,a stringdescribingthe error.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 292 | 317 

Firestorm® Web Services API | Version 2.2.33 

### External Order Gateway 

WARNING: This service is only supported on the v3 shopping cart! 

While not a true web service, the Firestorm® External Order gateway allows an external system to handle the browsing of products, and when the shopper is ready, the external system will pass the order over to Firestorm® which will handle the actual checkout process and recording the order into the Firestorm® database. 

The shopping cart supports a special POST interface that will allow a remote system to post the requested contents of a new order to the shopping cart via a defined XML document that will describe the order to be created, along with recurring order interval information, if desired. The XML document will also allow the remote system to specify additional client specific pricing data for each individual product on the order. When the remote system utilizes this capability, the system will accept and parse the XML document and use it to build an active shopping cart order.  In addition, if the proper parameters are set in the XML document, individual products may be flagged for inclusion in a recurring order that will be set up separately from the primary order. (Note: when a product is flagged to be placed onto a recurring order, it will still ship with the primary order) 

If the passed XML document contains any errors and cannot be parsed properly, then the shopping cart will present a special troubleshooting error page to the caller, indicating what the problem is, and what needs to be done to resolve any issues. This page is intended as a troubleshooting aid for the developer. 

##### <u>Linked Products Support</u> 

The gateway supports the concept of linking products together as a group. This is used when a group of products must be ordered together in order to receive them. On the view cart contents page, if a linked product is removed from the cart, all of the products that are linked to it will also be removed. In other words, buy them all or buy none of them. 

_NOTE: Linked products do NOT apply to recurring orders (autoships)! If a user orders a linked set of products and puts them on autoship,_ **_<u>they will be able to remove a single item</u>_** _<u>! Linking ONLY applies to the current order that</u> would be shipped immediately!_ 

##### <u>Recurring Order (Autoship) Setup</u> 

When the order XML is transmitted to the gateway, it is possible to denote one or more items on the order to be shipped on a regular schedule in the form of an autoship. 

When using this facility, the system will set up a separate recurring order for each UNIQUE combination of interval and frequency. For example, if the order XML contained 4 products that were flagged as recurring (autoship) products, and two of them were set up to ship every 30 days, and 2 were set up to ship every 90 days, the system would create 2 separate recurring orders, one that ships every 30 days and one that ship every 90 days.  Each recurring order would contain the products that denoted the same interval. (i.e.: Both 30 day products would be on the same recurring order and both 90 day products would be on a different recurring 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 293 | 317 

~~a~~ 



<!-- Start of picture text -->
en © Herel oeeben —_<br>[|. ~~ 808<br>eeegfH [ern<br>Shopping Cart r n Featured nems<br>=) AF [veep AT<br>ro ee ee<br>&<br>= RRS ——<br>* [s07436]<br>w<br>WBZE, Firestorm makes creating a = Use this area to feature .<br><!-- End of picture text -->

Firestorm® Web Services API | Version 2.2.33 

GetOpenPartiesByDealer () to obtain a list if currently open parties and only use PartyIDs returned from that web service to feed into this gateway. 

If an optional PartyGuestID IS provided, the gateway will credit the order to that party guest. If the PartyGuestID is NOT provided, the system will create a new party guest record and assign it to the party. 

##### <u>Product Questions</u> 

Product questions are fully supported through the gateway. The actual question text as well as the answer is transmitted through the XML document, so it is not necessary for the questions to be pre-defined in Firestorm®. 

When sending product question data, the main thing to be aware of the issue of multiple quantities of a single product. Each individual product must have the same set of questions answered. IN other words, if widget A has a series of three questions for a single product, and the customer orders a quantity of 3, you must send in the questions and answers for all three products. See the sample XML document and the node definition table below for the proper formatting of this data. 

##### <u>Different Response when passing in a ShoppingCartID</u> 

If you are passing in a ShoppingCartID, the system will respond with a special XML document formatted as follows: 

```
<?xml version='1.0' encoding='utf-8' ?>
<RESULT>
  <STATUS>FAIL</STATUS>
  <ERRORS count="1">
     <ERROR>Error Message Here</ERROR>
  </ERRORS>
</RESULT>
```

Where the following node definitions will apply: 

|Node|Attributes|Data Type|Description|
|---|---|---|---|
|RESULT|||Containingenvelope|
|STATUS||Boolean|“SUCCESS” or “FAIL”|
|ERRORS|Count – will contain the total<br>number of errors that occurred.|Numeric|When the status is “FAIL”, this containing envelope will be present.<br>This envelope will NOT be present if the order was successfully<br>processed.(STATUS=SUCCESS)|
|ERROR|||For each error that occurs, there will be an ERROR node containing<br>the text of the error.|



<u>When An Error is Detected or TEST MODE</u> 

When the XML document contains errors, a special “test mode” page will be displayed showing the results of the XML parsing. If any errors occurred, they will be listed on the form or in the XML return specifically detailing the error and which node contained the problem. 

When using TEST mode (even if you supplied a ShoppingCartID) The form will also display the raw XML as well as the orders contained in the document, so you can see what was successfully parsed and what was not. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 295 | 317 

Firestorm® Web Services API | Version 2.2.33 

This same form may be displayed for your integration testing by setting the node “TestMode” to TRUE. When this form is displayed either because of an error OR because you are using test mode, no order will be created in the shopping cart. 

##### <u>Sample XML Document</u> 

The external system will be responsible for building this document to the specification detailed below, Base64 encoding the result, then URL encoding and then POSTing it to the Firestorm® system. The following document is a sample of a valid XML document that can be successfully parsed by this page. 

```
<?xml version='1.0' encoding='utf-8' ?>
```

```
<Order>
   <TestMode>TRUE</TestMode>
<ShoppingCartID>-1</ShoppingCartID>
<CatalogueID>32</CatalogueID>
<Country>32</Country>
<PartyID>32</PartyID>
<PartyGuestID>-1</PartyGuestID>
<DealerID>-1</DealerID>
<CustomerDealerID>86559</CustomerDealerID>
<SponsoringDealerID>96558</SponsoringDealerID>
<RecurringHeader>
<ContainsRecurringItems>TRUE</ContainsRecurringItems>
<RecurringUnit>DAYS</RecurringUnit>
<RecurringFrequency>45</RecurringFrequency>
</RecurringHeader>
<ProductList totalProducts="2">
<Product>
<ExternalProductID>1</ExternalProductID>
<LinkedToExternalProductID>-1</LinkedToExternalProductID>
<IsRecurring>TRUE</IsRecurring>
<RecurringUnit>DAYS</RecurringUnit>
<RecurringFrequency>45</RecurringFrequency>
<ProductNumber>P-2334</ProductNumber>
<Quantity>1</Quantity>
<RetailPrice>-1</RetailPrice>
<WholesalePrice>-1</WholesalePrice>
<UplineVolume>-1</UplineVolume>
<PSVAmount>-1</PSVAmount>
<FreeShipping>TRUE</FreeShipping>
<QuestionList numQuestions=”1”>
<Item itemNo="1">
    <Question questionNo="1">
    <QuestionText>What Is Your Ring Size?</QuestionText>
    <Answer>12</Answer>
    </Question>
</Item>
</QuestionList>
</Product>
<Product>
<ExternalProductID>2</ExternalProductID>
<LinkedToExternalProductID>1</LinkedToExternalProductID>
<IsRecurring>FALSE</IsRecurring>
<RecurringUnit></RecurringUnit>
<RecurringFrequency></RecurringFrequency>
<ProductNumber>P-1785</ProductNumber>
<Quantity>3</Quantity>
<RetailPrice>-1</RetailPrice>
<WholesalePrice>-1</WholesalePrice>
<UplineVolume>-1</UplineVolume>
<PSVAmount>-1</PSVAmount>
<FreeShipping>FALSE</FreeShipping>
<QuestionList numQuestions=”3”>
<Item itemNo="1">
    <Question questionNo="1">
    <QuestionText>What is the meaning of life?</QuestionText>
    <Answer>42</Answer>
    </Question>
    <Question questionNo="2">
    <QuestionText>What color would you like?</QuestionText>
    <Answer>red</Answer>
    </Question>
    <Question questionNo="3">
    <QuestionText>What size?</QuestionText>
    <Answer>11</Answer>
    </Question>
</Item>
<Item itemNo="2">
    <Question questionNo="1">
    <QuestionText>What is the meaning of life?</QuestionText>
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 296 | 317 

Firestorm® Web Services API | Version 2.2.33 

```
    <Answer>42</Answer>
    </Question>
    <Question questionNo="2">
    <QuestionText>What color would you like?</QuestionText>
    <Answer>blue</Answer>
    </Question>
    <Question questionNo="3">
    <QuestionText>What size?</QuestionText>
    <Answer>11</Answer>
    </Question>
</Item>
<Item itemNo="3">
    <Question questionNo="1">
    <QuestionText>What is the meaning of life?</QuestionText>
    <Answer>42</Answer>
    </Question>
    <Question questionNo="2">
    <QuestionText>What color would you like?</QuestionText>
    <Answer>green</Answer>
    </Question>
    <Question questionNo="3">
    <QuestionText>What size?</QuestionText>
    <Answer>11</Answer>
    </Question>
</Item>
</QuestionList>
</Product>
</ProductList>
</Order>
```

* Note: In the example XML above, the second product is linked to the first product in the list. If you are not using linked products, the value for “LinkedToExternalProductID” would be set to -1. 

##### <u>Preparing the XML Document</u> 

Before the XML document may be posted to the Firestorm® system, it must first be encoded properly. The following steps must be taken in the proper order to ensure that the XML can be decoded and parsed correctly in Firestorm®: 

1. Build XML document per specification above 

2. Base 64 encode the resulting document 

3. URL encode the Base 64 encoded string 

4. Store the result in a hidden field on your page called “OrderXML” 

5. POST the page to the proper URL 

Sample Visual Basic Code: 

```
' /// Step 1. Create Straight up XML doc
```

```
WorkXML = "<?xml version='1.0' encoding='utf-8' ?><Order><TestMode>FALSE</TestMode><ShoppingCartID>-
```

```
1</ShoppingCartID><CatalogueID>210</CatalogueID><Country>USA</Country><PartyID>10</PartyID><PartyGuestID>-1</PartyGuestID><DealerID>-
1</DealerID><CustomerDealerID>-
1</CustomerDealerID><SponsoringDealerID>43096</SponsoringDealerID><RecurringHeader><ContainsRecurringItems>TRUE</ContainsRecurringItems><RecurringUnit>DAY
S</RecurringUnit><RecurringFrequency>45</RecurringFrequency></RecurringHeader><ProductList
```

```
totalProducts=’2’><Product><ExternalProductID>1</ExternalProductID><LinkedToExternalProductID>-
```

```
1</LinkedToExternalProductID><IsRecurring>TRUE</IsRecurring><RecurringUnit>DAYS</RecurringUnit><RecurringFrequency>45</RecurringFrequency><ProductNumber>S
1020</ProductNumber><Quantity>1</Quantity><RetailPrice></RetailPrice><WholesalePrice></WholesalePrice><UplineVolume></UplineVolume><PSVAmount></PSVAmount>
<FreeShipping>FALSE</FreeShipping><QuestionList numQuestions=’1’><Item itemNo=’1’><Question questionNo=’1’><QuestionText>What is your
age?</QuestionText><Answer>3265</Answer></Question></Item></QuestionList></Product><Product><ExternalProductID>2</ExternalProductID><LinkedToExternalProdu
ctID>1</LinkedToExternalProductID><IsRecurring>FALSE</IsRecurring><RecurringUnit></RecurringUnit><RecurringFrequency></RecurringFrequency><ProductNumber>S
1020</ProductNumber><Quantity>3</Quantity><RetailPrice></RetailPrice><WholesalePrice></WholesalePrice><UplineVolume></UplineVolume><PSVAmount></PSVAmount>
<FreeShipping></FreeShipping><QuestionList numQuestions=’3’><Item itemNo=’1’><Question questionNo=’1’><QuestionText>What is your
age?</QuestionText><Answer>33</Answer></Question><Question questionNo=’2’><QuestionText>What is your
age?</QuestionText><Answer>44</Answer></Question><Question questionNo=’3’><QuestionText>What is your
```

```
age?</QuestionText><Answer>55</Answer></Question></Item><Item itemNo=’2’><Question questionNo=’1’><QuestionText>What is your
age?</QuestionText><Answer>66</Answer></Question><Question questionNo=’2’><QuestionText>What is your
age?</QuestionText><Answer>77</Answer></Question><Question questionNo=’3’><QuestionText>What is your
```

```
age?</QuestionText><Answer>88</Answer></Question></Item><Item itemNo=’3’><Question questionNo=’1’><QuestionText>What is your
age?</QuestionText><Answer>99</Answer></Question><Question questionNo=’2’><QuestionText>What is your
```

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 297 | 317 

Firestorm® Web Services API | Version 2.2.33 

```
age?</QuestionText><Answer>100</Answer></Question><Question questionNo=’3’><QuestionText>What is your
age?</QuestionText><Answer>110</Answer></Question></Item></QuestionList></Product></ProductList></Order>”
```

```
‘ /// Step 2. Base 64 encode the XML document (this is a custom function. You will need to write your own)
 WorkXML = oUtil.base64_encode(WorkXML)
```

```
‘ /// Step 3. Url encode the base64 string
WorkXML = Server.UrlEncode(WorkXML)
```

##### Sample Web Page: 

<mark>`<!DOCTYPE html> <html xmlns=”http://www.w3.org/1999/xhtml”> <head> <title></title> <link href=’../Styles.css’ type=”text/css” rel=”stylesheet” /> </head> <body> <form action=”https://www.YOURURLHERE.com/MemberToolsDotNet/ShoppingCartNew/ExternalOrder.aspx” method=”post”> <!—Note: Order XML must first be converted to Base 64, then the resulting string must be url encoded` </mark> <mark>`<input type=”hidden” id=”OrderXML” name=”OrderXML” value=”PD94bWwgdmVyc2lvbj0nMS4wJyBlbmNvZGluZz0ndXRmLTgnID8%2bPE9yZGVyPjxUZXN0TW9kZT5GQUxTRTwvVGVzdE1vZGU%2bPENhdGFsb2d1ZulEPjIxMDwvQ2F0YwxvZ3VlSUQ%2bPENvd W50cnk%2bVVNBPC9Db3VudHJ5PjxQYXJ0eUlEPjEwPC9QYXJ0eUlEPjxQYXJ0eUd1ZXN0SUQ%2bLTE8L1BhcnR5R3Vlc3RJRD48RGVhbGVySUQ%2bLTE8L0RlYWxlcklEPjxDdXN0b21lckRlYWxlcklEP i0xPC9DdXN0b21lckRlYWxlcklEPjxTcG9uc29yaW5nRGVhbGVySUQ%2bNDMwOTY8L1Nwb25zb3JpbmdEZWFsZXJJRD48UmVjdXJyaW5nSGVhZGVyPjxDb250Ywluc1JlY3VycmluZ0l0ZW1zPlRSVUU8L 0NvbnRhaW5zUmVjdXJyaW5nSXRlbXM%2bPFJlY3VycmluZ1VuaXQ%2bREFZUzwvUmVjdXJyaW5nVW5pdD48UmVjdXJyaW5nRnJlcXVlbmN5PjQ1PC9SZWN1cnJpbmdGcmVxdWVuY3k%2bPC9SZWN1cnJpb mdIZWFkZXI%2bPFByb2R1Y3RmaXN0IHRvdGFsUHJvZHVjdHM9JzInPjxQcm9kdWN0PjxJc1JlY3VycmluZz5UUlVFPC9Jc1JlY3VycmluZz48UmVjdXJyaW5nVW5pdD5EQVlTPC9SZWN1cnJpbmdVbml0P jxSZWN1cnJpbmdGcmVxdWVuY3k%2bNDU8L1JlY3VycmluZ0ZyZXF1ZW5jeT48UHJvZHVjdE51bWJlcj5TMTAyMDwvUHJvZHVjdE51bWJlcj48UXVhbnRpdHk%2bMTwvUXVhbnRpdHk%2bPFJldGFpbFBya WNlPjwvUmV0YWlsUHJpY2U%2bPFdob2xlc2FsZVByaWNlPjwvV2hvbGVzYWxlUHJpY2U%2bPFVwbGluZVZvbHVtZT48L1VwbGluZVZvbHVtZT48UFNWQW1vdW50PjwvUFNWQW1vdW50PjxGcmVlU2hpcHB pbmc%2bRkFMU0U8L0ZyZWVTaGlwcGluZz48UXVlc3Rpb25MaXN0IG51bVF1ZXN0aW9ucz0nMSc%2bPEl0ZW0gaXRlbU5vPScxJz48UXVlc3Rpb24gcXVlc3Rpb25Obz0nMSc%2bPFF1ZXN0aW9uVGV4dD5 QZXQgUHJvZmlsZSBJRDwvUXVlc3Rpb25UZXh0PjxBbnN3ZXI%2bMzI2NTwvQW5zd2VyPjwvUXVlc3Rpb24%2bPC9JdGVtPjwvUXVlc3Rpb25MaXN0PjwvUHJvZHVjdD48UHJvZHVjdD48SXNSZWN1cnJpb mc%2bRkFMU0U8L0lzUmVjdXJyaW5nPjxSZWN1cnJpbmdVbml0PjwvUmVjdXJyaW5nVW5pdD48UmVjdXJyaW5nRnJlcXVlbmN5PjwvUmVjdXJyaW5nRnJlcXVlbmN5PjxQcm9kdWN0TnVtYmVyPlMxMDIwP C9Qcm9kdWN0TnVtYmVyPjxRdWFudGl0eT4zPC9RdWFudGl0eT48UmV0YWlsUHJpY2U%2bPC9SZXRhaWxQcmljZT48V2hvbGVzYWxlUHJpY2U%2bPC9XaG9sZXNhbGVQcmljZT48VXBsaW5lVm9sdW1lPjw vVXBsaW5lVm9sdW1lPjxQU1ZBbW91bnQ%2bPC9QU1ZBbW91bnQ%2bPEZyZWVTaGlwcGluZz48L0ZyZWVTaGlwcGluZz48UXVlc3Rpb25MaXN0IG51bVF1ZXN0aW9ucz0nMyc%2bPEl0ZW0gaXRlbU5vPSc xJz48UXVlc3Rpb24gcXVlc3Rpb25Obz0nMSc%2bPFF1ZXN0aW9uVGV4dD5QZXQgUHJvZmlsZSBJRDwvUXVlc3Rpb25UZXh0PjxBbnN3ZXI%2bMzM8L0Fuc3dlcj48L1F1ZXN0aW9uPjxRdWVzdGlvbiBxd WVzdGlvbk5vPScyJz48UXVlc3Rpb25UZXh0PlBldCBQcm9maWxlIElEPC9RdWVzdGlvblRleHQ%2bPEFuc3dlcj40NDwvQW5zd2VyPjwvUXVlc3Rpb24%2bPFF1ZXN0aW9uIHF1ZXN0aW9uTm89JzMnPjx RdWVzdGlvblRleHQ%2bUGV0IFByb2ZpbGUgSUQ8L1F1ZXN0aW9uVGV4dD48QW5zd2VyPjU1PC9BbnN3ZXI%2bPC9RdWVzdGlvbj48L0l0ZW0%2bPEl0ZW0gaXRlbU5vPScyJz48UXVlc3Rpb24gcXVlc3R pb25Obz0nMSc%2bPFF1ZXN0aW9uVGV4dD5QZXQgUHJvZmlsZSBJRDwvUXVlc3Rpb25UZXh0PjxBbnN3ZXI%2bNjY8L0Fuc3dlcj48L1F1ZXN0aW9uPjxRdWVzdGlvbiBxdWVzdGlvbk5vPScyJz48UXVlc 3Rpb25UZXh0PlBldCBQcm9maWxlIElEPC9RdWVzdGlvblRleHQ%2bPEFuc3dlcj43NzwvQW5zd2VyPjwvUXVlc3Rpb24%2bPFF1ZXN0aW9uIHF1ZXN0aW9uTm89JzMnPjxRdWVzdGlvblRleHQ%2bUGV0I FByb2ZpbGUgSUQ8L1F1ZXN0aW9uVGV4dD48QW5zd2VyPjg4PC9BbnN3ZXI%2bPC9RdWVzdGlvbj48L0l0ZW0%2bPEl0ZW0gaXRlbU5vPSczJz48UXVlc3Rpb24gcXVlc3Rpb25Obz0nMSc%2bPFF1ZXN0a W9uVGV4dD5QZXQgUHJvZmlsZSBJRDwvUXVlc3Rpb25UZXh0PjxBbnN3ZXI%2bOTk8L0Fuc3dlcj48L1F1ZXN0aW9uPjxRdWVzdGlvbiBxdWVzdGlvbk5vPScyJz48UXVlc3Rpb25UZXh0PlBldCBQcm9ma WxlIElEPC9RdWVzdGlvblRleHQ%2bPEFuc3dlcj4xMDA8L0Fuc3dlcj48L1F1ZXN0aW9uPjxRdWVzdGlvbiBxdWVzdGlvbk5vPSczJz48UXVlc3Rpb25UZXh0PlBldCBQcm9maWxlIElEPC9RdWVzdGlvb lRleHQ%2bPEFuc3dlcj4xMTA8L0Fuc3dlcj48L1F1ZXN0aW9uPjwvSXRlbT48L1F1ZXN0aW9uTGlzdD48L1Byb2R1Y3Q%2bPC9Qcm9kdWN0TGlzdD48L09yZGVyPg” /> <input type=”submit” name=”btnSend” value=”Send the Order” /> </form> </body> </html>`</mark> 

##### <u>POST URL</u> 

The sample XML document below will be posted to: 

https://www.YOURURLHERE.com/MemberToolsDotNet/ShoppingCartNew/ExternalOrder.aspx 

on your website where Firestorm® resides. Firestorm will then parse it out to create an actual shopping cart. 

##### <u>XML Node Definition</u> 

Each node in the XML document is defined in the table below: 

|Node|Attributes|Data Type|Description|
|---|---|---|---|
|Order|||Containingenvelope|
|TestMode||Boolean|TRUE will place the gateway into test mode, where a special<br>diagnostic page will appear instead of creating a shopping cart<br>FALSE willplace thegatewayintoproduction mode|
|ShoppingCartID||Numeric|IF USING THE GATEWAY AS PART OF AN “ADDTOCART()” WIDGET:<br>This is the existing ShoppingCartID that the products on this order<br>will be ADDED to. When this value is provided, the gateway will NOT<br>redirect to the view cart contentspage afterprocessing. It will simply|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 298 | 317 

Firestorm® Web Services API | Version 2.2.33 

||||return an XML document with a single node called “RESULT” which<br>will contain “SUCCESS” if the products were added successfully.<br>Please note that if you use this feature, any data item that is on the<br>Shopping Cart header (i.e.: PartyID) will NOT be updated with the<br>values in the XML. This mode of operation is for adding products to<br>an existingorder only.|
|---|---|---|---|
|CatalogueID||Numeric|The catalogue ID from Firestorm. This must be a valid CatalogueID<br>that exists in Firestorm. (Note: All products being ordered MUST also<br>exist within this catalog!)|
||||Note: If a valid PartyID is passed in, this catalog must be flagged as a<br>“Party” catalog,or the order will be refused.|
|Country||String|ISO Country code as defined in Firestorm. Used when calculating VAT<br>taxes.|
|PartyID||Numeric|Existing partyID from Firestorm|
|PartyGuestID||Numeric|The ID number assigned by Firestorm to this guest. If this number is<br>not provided (send in -1), Firestorm will create a new guest record<br>and assign it to the party referenced by PartyID.|
||||**Note: If this order contains a recurring order, please be aware that**<br>**the recurring order will be set up to ship to the BILLING address of**<br>**the guest. This is necessary due to the fact that some party orders**<br>**can be shipped to the host instead of the guest for delivery. The**<br>**billing address is guaranteed to belong to the guest, so it is used.**|
|DealerID||Numeric|If this is an existing members order, this is the unique ID number<br>assigned to them bythe Firestorm system.|
|CustomerDealerID||Numeric|Dealer ID for the customer, obtained from Firestorm. If this is a new<br>customer,this node should bepopulated with -1|
|Note: If DealerID and CustomerDeale<br>SponsoringDealerID|rID are both set to -1,th|en the order will b<br>Numeric|e treated like a brand new customer order<br>The dealer ID of the sponsor of the customer, obtained from<br>Firestorm (if the profile is being accessed from a replicating website,<br>this value should be stored in a session variable that can be used by<br>thisprocess). This value should never be blank or less than 1.|
|RecurringHeader|||Container for recurringorder info|
|ContainsRecurringItems||Boolean|If the order has 1 or more items that should be added to an autoship<br>order, this value should be set to “TRUE”. If this is just a regular order<br>with no items for autoship,set the value to “FALSE”.|
|RecurringUnit||String|The unit value to use when calculating the next ship date. Valid<br>values are “DAYS”,“WEEKS” or “MONTHS”|
|RecurringFrequency||Numeric|The number of RecurringUnits to use when calculating the next<br>shipment date. (i.e.: If RecurringUnit is set to DAYS and<br>RecurringFrequencyis set to 30,the autoshipwill shipevery30 days)|
|ProductList|totalProducts<br>should be set<br>to the total<br>number of<br>product<br>structures in<br>the list||Envelope used to contain a list of Product structures (Product,<br>ProductNumber, Quantity, Questions). One product structure should<br>be sent for each item on the order.|
|Product|||Container for aproduct on the order|
|ExternalProductID||Numeric|When using linked products, this is a unique number that you will<br>generate to identify this top level product thatotherproducts will<br>link to. This value is used in the “LinkedToExternalProductID” field on<br>those child products.<br>Best practice would be to assign a unique ExternalProductID to all<br>items on the order. However, if you follow this guideline, remember<br>that all items in the order must have their own**unique**<br>ExternalProductID. No two items in the order willeverhave the same<br>number.<br>The format of the ExternalProductID does not matter except that it|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 299 | 317 

Firestorm® Web Services API | Version 2.2.33 

||||must be numeric, and its value must fit into an 32 bit integer. Valid<br>values are 0 thru 2,147,483,647<br>**_WARNING_**_: EACH VALUE YOU GENERATE SHOULD ONLY BE USED FOR_<br>_1 ITEM IN YOUR ORDER! EVERY PRODUCT SHOULD HAVE ITS OWN_<br>_ExternalProductID._<br>Even If the user orders the same product again, you would still need<br>to generate a different unique number for that item. This number is<br>only used in the linking functionality and will not affect anything else.<br>_NOTE: Linked products to NOT apply to recurring orders! If a user_<br>_orders a linked set of products and puts them on autoship, then will_<br>_be able to remove a single item! Linking ONLY applies to the current_<br>_order that would be shipped immediately!_<br>Consider this as a “Kit Serial Number”. It will be used to link a group<br>of products together in the cart so that if the user deletes one of the<br>group then the entire group will be removed.|
|---|---|---|---|
|LinkedToExternalProductID||Numeric|The ExternalProductID of thetop levelproduct that this product is<br>linked to.<br>_NOTE: Linked products do NOT apply to recurring orders (autoships)!_<br>_If you pass in an order that has a linked set of products and put them_<br>_on autoship,_**_they will be able to remove a single item_**_! Linking ONLY_<br>_applies to the current order!_<br>**When not using linked productsor this is the top level productof a**<br>**group of linkedproducts, this node should bepopulated with “-1”**|
|IsRecurring||Boolean|Set this value to “TRUE” if this item should be flagged to be included<br>on a recurring order. If the value is set to “FALSE”, the item will<br>appear in the shoppingcart as a one-timepurchase item.|
|RecurringUnit||String|The unit value to use when calculating the next ship date. Valid<br>values are “DAYS”, “WEEKS” or “MONTHS”. This value will OVERRIDE<br>the valuepassed in the header for thisproduct only.|
|RecurringFrequency||Numeric|The number of RecurringUnits to use when calculating the next<br>shipment date. (i.e.: If RecurringUnit is set to DAYS and<br>RecurringFrequency is set to 30, the autoship will ship every 30 days).<br>This value will OVERRIDE what is passed in the header for this<br>product only.|
|ProductNumber||String|Product number as defined in Firestorm|
|Quantity||Numeric|Quantity|
|RetailPrice||Numeric|Retail price of item. No currency symbols allowed. If you wish to use<br>the defined catalog pricing, you mustpass -1 in this field.|
|WholesalePrice||Numeric|Wholesale price of item. No currency symbols allowed. If you wish to<br>use the defined catalog pricing, you mustpass -1 in this field.|
|UplineVolume||Numeric|Commissionable value of item. No currency symbols allowed. If you<br>wish to use the defined catalog pricing, you mustpass -1 in this field.|
|PSVAmount||Numeric|PSV value of item. No currency symbols allowed. If you wish to use<br>the defined catalog pricing, you mustpass -1 in this field.|
|FreeShipping||Boolean|TRUE for free shipping on the current order. FALSE will cause the<br>system to charge configured shipping rates. NOTE: This flag WILL<br>NOT APPLY TO RECURRING ORDERS.|
|QuestionList|numQuestions||Container forproductquestions|
|Item|itemNo||Container for each item in a given quantity. (i.e.: if a line item on the<br>order has a quantity of 3, then then should be 3 ITEM elements that<br>contain the question details) itemNo should increment starting with<br>the number 1,andgo upby1 for each item.|
|QuestionText||String|Text of thequestion|
|Answer||String|Answer to thequestions|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 300 | 317 

Firestorm® Web Services API | Version 2.2.33 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 301 | 317 

Firestorm® Web Services API | Version 2.2.33 

### FirestormMobileWS 

|General Infor|mation|
|---|---|
|Name|FirestormMobileWS.asmx|
|WSDL|https://www.firestormwebservices.com/FirestormWebServices/FirestormMobileWS.asmx|
|Description|Provides external systems with the ability to pull specific data from a client system.  The web<br>service is command based, with supported commands being client dictated.<br>WARNING: All supported commands are implemented on a client by client basis, so for this<br>service to function properly, it will require some custom development by Firestorm® staff in<br>order to respond to commandsproperly.|



|Method Summary||
|---|---|
|Method Name|Return Type|
|RunCommand|XML Document|





C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 302 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormMobileWS.RunCommand 

This method will allow a remote system to issue commands to the Firestorm® system in order to retrieve data, or make specific actions occur on the Firestorm® system. 

NOTE: There are no “standard” commands. If a remote system wishes to utilize this service, it must coordinate the deployment and use of this service with Firestorm® support. Our team will work with you to decide which commands will be supported and what the appropriate responses will be, within the standardized framework of this web service. In order to receive a response to a command, procedures will have to be created that will correspond to each command. 

|Method Definition<br>|||||
|---|---|---|---|---|
|Argument|Required|Description|Datatype|Valid Values|
|Token|Y|SecurityToken assigned toyou bysupport|String||
|Context|Y|Context value assigned toyou bysupport|String||
|DealerID|Y|The dealer ID that initiated the session|Integer|Any valid DealerID.<br>All reports will be run<br>against this DealerID|
|CommandRequest|Y|The xml document constructed as specified below<br>that contains a list of commands that will be run by<br>this service.|XML Document|See below|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

##### <u>Custom Programming Required</u> 

When implementing a command for a client, custom programming will be required on the Firestorm® system in order to provide the appropriate responses to the requests that are sent over. 

##### <u>Number of simultaneous commands</u> 

While the web service is constructed in a way to allow the requestor to send multiple commands at the same, it is important to understand the processing load introduced on the Firestorm® system for each command. Use good judgement when deciding on how many commands to send! 

In order to maintain a good user experience in the mobile world, you should strive for the minimum amount of latency as possible. Remember that more commands = more processing time. 

##### <u>NO BULK DATA RETRIEVALS</u> 

The use of a web service to pull inordinate amounts of data is inappropriate and will not be allowed. If you are trying to implement a command that could potentially pull hundreds of records as a response, our design team 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 303 | 317 

Firestorm® Web Services API | Version 2.2.33 

will not allow this. This type of response could be bandwidth consuming and cause performance issues with the web service. 

Appropriate commands to implement are those that will contain a restricted result set of data. As it is, the data will be restricted to a single DealerID. 

##### <u>Command Request XML</u> 

When calling this web service, this field allows you to construct an XML document, containing all of the commands (along with arguments) that you wish to run, then pass it over to Firestorm® as an XML document as shown below. 

Make sure you wrap your XML in <CDATA> tags to prevent any parser errors! You must begin your document with “<![CDATA[“ then append your XML document and then append “]]>”. This will prevent the Firestorm® XML parser from getting an error. 

**Uppercase and lowercase matter in XML** . Opening and closing tags must match exactly. For example, `<ROOT>` , `<Root>` , and `<root>` are three different tags 

You will build a <COMMANDREQUEST> <COMMANDS numcommands=”#”> envelope ( _remember numcommands must equal the number of <COMMAND> envelopes to follow_ ), then for each command in your request you will add a <COMMMAND> envelope that will contain all the information required to execute the command on Firestorm®. 

When building this document, remember that any command specified in your call must have already been implemented in Firestorm®. If an unknown command is received, the call will fail. 

The <COMMANDS> element must contain at least 1 <COMMAND> element. 

**_Hint:_** _The passed XML document must be completely valid so that it may be parsed correctly by Firestorm®. Please test your XML document thoroughly to ensure that it can be loaded without error by an XML parser. This will avoid problems with your successful use of this web service._ 

The following is a definition of the XML document required (CDATA tags were added to remind you!): 

<![CDATA[ 

<?xml version='1.0' encoding='utf-8' ?> 

<COMMANDREQUEST> 

<COMMANDS numcommands="number of command nodes"> 

<COMMAND> 

<COMMANDNAME>Defined by client</COMMANDNAME> 

<LANGUAGECODE>Defined by Firestorm</LANGUAGECODE> 

<CURRENCYCODE>Defined by Firestorm</CURRENCYCODE> 

<ARGUMENTS numargs="number of argument nodes"> 

<ARGUMENT> 

<ARGUMENTNAME></ARGUMENTNAME> 

<ARGUMENTVALUE></ARGUMENTVALUE> </ARGUMENT> 

</ARGUMENTS> 

</COMMAND> 

</COMMANDS> 

</COMMANDREQUEST> 

]]> 

This XML document is constructed by your system and is passed over to Firestorm® in the “CommandRequest” argument. The layout of the XML document is not optional and must be followed exactly to ensure that your 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 304 | 317 

Firestorm® Web Services API | Version 2.2.33 

order can be read and processed successfully by the Firestorm® system. If you are not using a given node, it must still be present in your document. Just leave it unpopulated. 

The following table describes in detail the various elements of this document along with definitions and requirements for each section: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|<?xml…..|||Required XML document header(see example above)|
|<![CDATA[|||OpeningCDATA tag|
|COMMANDREQUEST|||Containingenvelope for the request|
|COMMANDS||numcommands<br>_(defines the number of_<br>_COMMAND nodes to_<br>_follow)_|Containing envelope for all commands to be processed.<br>While there is no limit to the number of commands that can be passed<br>to the web service, you must use good judgement when deciding how<br>manycommands topass at once.|
|COMMAND|||Containingenvelope for a single command|
|COMMANDNAME|String||The code representing the command to run. This value must be<br>predefined in Firestorm® before using it. Coordinate with Firestorm®<br>support to ensure this has been done.|
|LANGUAGECODE|String||The code defined in Firestorm that will represent the language that<br>you want all text responses to be returned as. (Note:  translations for<br>each possible response must be provided by the Firestorm® client<br>using standard Firestorm® functionality)<br>This node may be left blank, but must exist. If a code is not specified,<br>then all responses will be in the default language set upin Firestorm®|
|CURRENCYCODE|String||The code defined in Firestorm that will represent the currency that you<br>want all responses to be returned as. (Note:  currency conversion<br>ratios for each possible response must be provided by the Firestorm®<br>client)<br>This node may be left blank, but must exist. If a code is not specified,<br>then all responses will be in the default currencyset upin Firestorm®|
|ARGUMENTS||numargs<br>_(defines the number of_<br>_ARGUMENT nodes to_<br>_follow)_|Containing envelope for arguments to the current command|
|ARGUMENT|||Containingenvelope for a single argument|
|ARGUMENTNAME|String||The name of this argument.(i.e.: STARTDATE)|
|ARGUMENTVALUE|String||The actual value that will be used by the command for this argument.<br>**Please note**that datatype validation will NOT be performed by the<br>web service! You must ensure that the value you present in this node<br>will be accepted as valid bythe command,or the command will fail!|
|]]>|||ClosingCDATA tag|



##### **<u>Return Values</u>** 

This web service will return a complex XML document containing the results of the call. The contents of this document will vary, based on the type of command that was requested. 

##### <u>CommandResponse XML</u> 

The following XML document contains all of the possible types of responses that you may receive, depending on the processing status (i.e.: system errors) and the command your requested with the possible responses from each command. 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 305 | 317 

Firestorm® Web Services API | Version 2.2.33 

<?xml version='1.0' encoding='utf-8' ?> 

<RESPONSE systemerrorcount="number of system error response nodes" commandresponsecount="number of command response nodes"> <SYSTEMERRORRESPONSE> 

|<ERRORCODE></ERRORCODE>|
|---|
|<ERRORMESSAGE></ERRORMESSAGE>|
|</SYSTEMERRORRESPONSE>|
|<COMMANDRESPONSE>|
|<COMMANDNAME>Defined by client</COMMANDNAME>|
|<COMMANDRESULT>see list below</COMMANDRESULT><br><COMMANDRESPONSEDATA type="see list below"><br><SUCCESSRESPONSE format="see list for values"><br><VALUE></VALUE>|
|-or-|
|<REPORT numrows="number of rows in the report"><br><ROW></ROW>|
|</REPORT>|
|</SUCCESSRESPONSE>|
|-or -|
|<FAILURERESPONSE>|
|<FAILURECODE>client specific failure code</FAILURECODE><br><FAILUREMESSAGE>client specific failure message</FAILUREMESSAGE>|
|</FAILURERESPONSE>|
|- or -|
|<ERRORRESPONSE numerrors="number of error nodes">|
|<ERROR>|
|<CODE></CODE>|
|<MESSAGE></MESSAGE>|
|<ADDLINFO></ADDLINFO>|
|</ERROR>|
|</ERRORRESPONSE>|



</COMMANDRESPONSEDATA> 

</COMMANDRESPONSE> 

</RESPONSE> 

The table below describes this document along with definitions of each node: 

|**Element**|**DataType**|**Attribute**|**Definition**|
|---|---|---|---|
|<?xml…..|||Required XML document header(see example above|
|RESPONSE||systemerrorcount<br>_(Contains the total_<br>_number of_<br>_SYSTEMERRORRESPONSE_<br>_nodes to follow)_<br>commandresponsecount<br>_(contains the total_<br>_number of_<br>_COMMANDRESPONSE_<br>_nodes to follow)_|Containing envelope for the response<br>**NOTE:**If systemerrorcount > 0, then a true system error occurred<br>and no commands could be processed. If this count is greater<br>than zero, then there is no need to attempt to parse and<br>COMMANDRESPONSE nodes. There won’t be any!|
|SYSTEMERRORRESPONSE|||Containing envelope for a single system error<br>Errors at this level are true system level errors that have<br>prevented the entire COMMANDREQUEST from being processed.<br>Individual errors that may have been generated by a single<br>command will be contained in the ERRORRESPONSE node for that<br>individual command.|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 306 | 317 

Firestorm® Web Services API | Version 2.2.33 

|ERRORCODE|String||The code associated with the error that occurred.<br>Please note that the web service will NOT return an actual system<br>error that may contain information that could be used by<br>someone to derive the underlying structure of the system. All<br>error codes will be sanitized.<br>To get the actual system error that occurred it will be necessary to<br>contact Firestorm® support so that our internal logs can be<br>checked foryou.|
|---|---|---|---|
|ERRORMESSAGE|String||A message describing the error that occurred.<br>Please note that the web service will NOT return an actual system<br>error message that may contain information that could be used by<br>someone to derive the underlying structure of the system. All<br>error messages will be sanitized.<br>To get the actual system error that occurred it will be necessary to<br>contact Firestorm® support so that our internal logs can be<br>checked foryou.|
|COMMANDRESPONSE|||Containingenvelope for a single command response|
|COMMANDNAME|String||The code representing the command that was run. This is the<br>same code that was passed in the COMMAND node in the original<br>COMMANDREQUEST.|
|COMMANDRESULT|String||Indicates whether or not the client procedure was able to be<br>executed by the system. Tis does not indicate if the procedure<br>returned a valid result or not. It is simply an indication that the<br>system was able to execute the procedure.<br>Will contain one of two possible values:<br>**TRUE**<br>Client procedure executed successfully.<br>**FALSE**<br>The client procedure could not be executed. If this value is false,<br>the COMMANDRESPONSEDATA type attribute will be set to<br>“error” and will contain an ERRORRESPONSE envelope to<br>document the error.|
|COMMANDRESPONSEDATA||type<br>Valid values<br>success<br>failure<br>error|Containing envelope for responses from a specific command.<br>Please note that the contents of this envelope willdependon the<br>value contained in COMMANDRESULT.<br>When loading this node, check the “type” attribute to determine<br>what to look for in this envelope. The list below will guide you in<br>determining which nodes to scan for:<br>**success** <br>The client process returned a "success" status. The<br>COMMANDRESPONSEDATA node will contain a<br>SUCCESSRESPONSE node with the results in the appropriate<br>format.<br>**failure**<br>This is not an error!This is when the client process returns a "fail"<br>status. This can happen if the command is a test of some sort  (i.e:<br>command=PSV>100 response="You only have 75 PSV in this<br>period"). The COMMANDRESPONSEDATA node will contain a<br>FAILURERESPONSE node<br>**error**|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 307 | 317 

Firestorm® Web Services API | Version 2.2.33 

||||A true system error occurred when the web service tried to<br>execute the command. COMMANDRESPONSEDATA node will<br>contain an ERRORRESPONSE node containing the errors that<br>occurred.<br>Please note that the web service will NOT return an actual system<br>error message that may contain information that could be used by<br>someone to derive the underlying structure of the system. All<br>error messages will be sanitized.<br>To get the actual system error that occurred it will be necessary to<br>contact Firestorm® support so that our internal logs can be<br>checked foryou|
|---|---|---|---|
|SUCCESSRESPONSE||format<br>Valid Values<br>singlevalue<br>report|.<br>Containing envelope for the successful response from a<br>command.<br>The “format” attribute is used to determine the appropriate<br>nodes to parse. These nodes will change based on the type of<br>response being delivered.<br>If format is set to “singlevalue” then the SUCCESSRESPONSE node<br>will contain a VALUE node.|
||||If format is set to “report” the SUCCESSRESPONSE node will<br>contain a REPORT node|
|VALUE|string||Node that contains a single value that is the result of the<br>command.|
|REPORT||numrows<br>Total number of ROW<br>nodes to follow|Containing envelope for a result of a command that is a set of<br>rows (a report).<br>When encountering this node, you must check the “numrows”<br>attribute to determine the total number of ROW nodes to follow.|
|ROW|String||Containing envelope for a single row of data from a report.<br>The actual format of the row data will be determined by the<br>command procedure that was run. Example formats would be CSV<br>data, Pipe delimited data, XML, etc. You must know the incoming<br>format so that you may parse the row successfully.<br>_Be aware that if you use XML format as row data, you must_<br>_enclose the XML data in CDATA tags!_|
|FAILURERESPONSE|||Containing envelope for a failure response from a command<br>_REMEMBER: This is not an error! It is a fail status from the_|
||||_command that was executed._|
|FAILURECODE|String||Client specified code for the type of failure|
|FAILUREMESSAGE|String||Client specified message to describe failure|
|ERRORRESPONSE||numerrors|Containing envelope for an error response.|
|||The total number of<br>ERROR nodes to follow|The “numerrors” attribute should be checked to determine how<br>many ERROR nodes exist.|
||||_REMEMBER: This is an actual error that occurred  when the_<br>_command was executed_|
|CODE|String||Code for the error that occurred<br>_Please note that the web service will NOT return an actual system_<br>_error code that may contain information that could be used by_<br>_someone to derive the underlying structure of the system. All error_<br>_messages will be sanitized._<br>_To get the actual system error that occurred it will be necessary to_<br>_contact Firestorm® support so that our internal logs can be_<br>_hkdf _|
|MESSAGE|String||_ceceoryou._<br>A message describingthe error|



|C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c .P a g e308 | 317|
|---|



Firestorm® Web Services API | Version 2.2.33 

|||_Please note that the web service will NOT return an actual system_<br>_error message that may contain information that could be used by_<br>_someone to derive the underlying structure of the system. All error_<br>_messages will be sanitized._<br>_To get the actual system error that occurred it will be necessary to_<br>_contact Firestorm® support so that our internal logs can be_<br>_checkedforyou._|
|---|---|---|
|ADDLINFO|String|Additional information about the error. May contain information<br>that will aid our support team in determining the cause of the<br>error.<br>This data will also be sanitized, and would be useful only to our<br>support team! It is important that you capture this information in<br>case our team needs it.|



##### **<u>Sample XML Documents</u>** 

_Please note that the values in each node are here for demonstration purposes only! Any command and arguments must be pre-defined in Firestorm® in order to get a response._ 

For the purposes of these examples, the following commands will be used: 

PSVCURRENTPERIOD is a valid command that will take two arguments (STARTDATE and ENDDATE). When this command is requested, it will calculate the amount of PSV between the start and end dates and will return that value as a single number. 

PERSONALLYSPONSOREDCOUNT is a valid command with no arguments. When this command is executed, the system will total the number of personally sponsored all-time, and will return that value as a single number 

PERSONALLYSPONSOREDLIST is a valid command with no arguments. When this command is executed, the system will retrieve a list of personally sponsored members, and will return that list as a set of rows where each ROW node will contain the Last name, First name and Enroll date data columns for each personally sponsored member.  Each value in the row will be separated by a “|” (pipe) character. (Remember that the **_<u>actual</u>_** format is specified by the client command procedure! This is just an example) 

EXAMPLECOMMANDFAILURE is being included here to show you what a process that fails (not an error) will return 

EXAMPLECOMMANDERROR in being included here to show you what a command that experiences an actual error will return. 

##### <u>Sample Command Request XML</u> 

<![CDATA[ 

> <?xml version='1.0' encoding='utf-8' ?> 

> <COMMANDREQUEST> 

> <COMMANDS numcommands="3"> 

> <COMMAND> <COMMANDNAME>PSVCURRENTPERIOD</COMMANDNAME> <LANGUAGECODE>1</LANGUAGECODE> <CURRENCYCODE>1</CURRENCYCODE> <ARGUMENTS numargs="2"> 

<ARGUMENT> 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 309 | 317 

Firestorm® Web Services API | Version 2.2.33 

<ARGUMENTNAME>STARTDATE</ARGUMENTNAME> <ARGUMENTVALUE>1/1/2016 00:00:00AM</ARGUMENTVALUE> </ARGUMENT> <ARGUMENT> <ARGUMENTNAME>ENDDATE</ARGUMENTNAME> 

<ARGUMENTVALUE>1/31/2016 11:59:59PM</ARGUMENTVALUE> 

</ARGUMENT> 

</ARGUMENTS> 

</COMMAND> 

<COMMAND> <COMMANDNAME>PERSONALLYSPONSOREDCOUNT</COMMANDNAME> <LANGUAGECODE>1</LANGUAGECODE> <CURRENCYCODE>1</CURRENCYCODE> <ARGUMENTS numargs="0"> </ARGUMENTS> </COMMAND> <COMMAND> <COMMANDNAME>PERSONALLYSPONSOREDLIST</COMMANDNAME> <LANGUAGECODE>1</LANGUAGECODE> <CURRENCYCODE>1</CURRENCYCODE> <ARGUMENTS numargs="0"> </ARGUMENTS> </COMMAND> <COMMAND> <COMMANDNAME>EXAMPLECOMMANDFAILURE</COMMANDNAME> <LANGUAGECODE>1</LANGUAGECODE> <CURRENCYCODE>1</CURRENCYCODE> <ARGUMENTS numargs="0"> </ARGUMENTS> </COMMAND> 

<COMMAND> <COMMANDNAME>EXAMPLECOMMANDERROR</COMMANDNAME> <LANGUAGECODE>1</LANGUAGECODE> <CURRENCYCODE>1</CURRENCYCODE> <ARGUMENTS numargs="0"> </ARGUMENTS> 

</COMMAND> 

</COMMANDS> 

</COMMANDREQUEST> 

]]> 

##### <u>Sample Command Response XML</u> 

<?xml version='1.0' encoding='utf-8' ?> 

<RESPONSE systemerrorcount="0" commandresponsecount="3"> 

<COMMANDRESPONSE> 

<COMMANDNAME> PSVCURRENTPERIOD </COMMANDNAME> 

<COMMANDRESULT>TRUE</COMMANDRESULT> 

<COMMANDRESPONSEDATA type="success"> 

<SUCCESSRESPONSE format="singlevalue"> 

<VALUE>2435.89</VALUE> 

</SUCCESSRESPONSE> 

</COMMANDRESPONSEDATA> 

</COMMANDRESPONSE> 

<COMMANDRESPONSE> 

<COMMANDNAME> PERSONALLYSPONSOREDCOUNT </COMMANDNAME> 

<COMMANDRESULT>TRUE</COMMANDRESULT> 

<COMMANDRESPONSEDATA type="success"> 

<SUCCESSRESPONSE format="singlevalue"> 

<VALUE>11</VALUE> 

</SUCCESSRESPONSE> 

</COMMANDRESPONSEDATA> 

</COMMANDRESPONSE> 

<COMMANDRESPONSE> 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 310 | 317 

Firestorm® Web Services API | Version 2.2.33 

<COMMANDNAME> PERSONALLYSPONSOREDLIST </COMMANDNAME> <COMMANDRESULT>TRUE</COMMANDRESULT> <COMMANDRESPONSEDATA type="success"> <SUCCESSRESPONSE format="report"> <REPORT numrows=”3”> <ROW>Smith|John|3/3/2016</ROW> <ROW>Ramjet|Roger|3/15/2016</ROW> <ROW>Willow|Mary|1/4/2016</ROW> </REPORT> </SUCCESSRESPONSE> </COMMANDRESPONSEDATA> </COMMANDRESPONSE> <COMMANDRESPONSE> <COMMANDNAME> EXAMPLECOMMANDFAILURE </COMMANDNAME> <COMMANDRESULT>TRUE</COMMANDRESULT> <COMMANDRESPONSEDATA type="failure"> <FAILURERESPONSE> <FAILURECODE>TESTFAIL</FAILURECODE> <FAILUREMESSAGE>You are not qualified for GOLD status</FAILUREMESSAGE> </FAILURERESPONSE> </COMMANDRESPONSEDATA> </COMMANDRESPONSE> <COMMANDRESPONSE> <COMMANDNAME> EXAMPLECOMMANDERROR </COMMANDNAME> <COMMANDRESULT>FALSE</COMMANDRESULT> <COMMANDRESPONSEDATA type="error"> <ERRORRESPONSE numerrors=”1”> <ERROR> <CODE>LF327</CODE> <MESSAGE>An error occurred processing the request</MESSAGE> <ADDLINFO>LOGTIMESTAMP: 1/3/2016 12:37:15 PM</ADDLINFO> </ERROR> </ ERRORRESPONSE > </COMMANDRESPONSEDATA> 

</COMMANDRESPONSE> 

</RESPONSE> 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 311 | 317 

Firestorm® Web Services API | Version 2.2.33 

### Firestorm Lookups Web Service 

|General Inform<br>|ation<br>|
|---|---|
|Name|FirestormLookupsWS.asmx|
|WSDL|https://www.firestormwebservices.com/FirestormWebServices/FirestormLookupsWS.asmx|
|Description|This web service will contain methods necessary to retrieve lookup table information for<br>various system entities. Use the codes listed below to obtain the information for lookup<br>values needed by your application.|



|Method Summary||
|---|---|
|Method Name|Return Type|
|GetLookupTableData|DataTable|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 312 | 317 

Firestorm® Web Services API | Version 2.2.33 

#### FirestormLookupsWS.GetLookupTableData 

Returns data from various lookup tables used in the Firestorm system. If the lookup information you need is not included in the list below, please contact opur customer service department and request that the additional information be added. 

|Method Definition<br><br>||||
|---|---|---|---|
|Argument<br>Required|Description|Datatype|Valid Values|
|Token<br>Y|SecurityToken assigned toyou bysupport|String||
|Context<br>Y|Context value assigned toyou bysupport|String||
|Code<br>Y|If provided, the system will look for this specific<br>Dealership Type.|String|CUSTOMERTYPE<br>COUNTRY<br>STATES<br>SHIPPERS<br>CATALOGS or<br>CATALOGUES<br>PAYMENTTYPES|
|Code2<br>N|Depending on the code requested, an additional<br>value may be required to properly search|String|When using code<br>STATES, a valid<br>COUNTRYID must be<br>supplied<br>When using code<br>SHIPPERS, if you<br>want only shippers<br>assigned to a specific<br>catalog, then a valid<br>CATALOGUEID must<br>be supplied in Code2|



##### **<u>Additional Restrictions Supported</u>** 

|Restriction Type|Supported|
|---|---|
|Country|No|
|Fields|No|
|Max Records|No|



##### **<u>Additional Information</u>** 

This web service is provided as a method to retrieve lookup table values for other web service functions. Please note that these records can be edited at any time by administrative personnel and as such could change at any time. These records are not static and should not be treated as such. 

**NOTE** : This web service will only return records marked as ACTIVE in Firestorm. Inactive records will automatically be excluded from the return. 

##### **<u>Return Values</u>** 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 313 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### Code: CUSTOMERTYPE 

|Returned Data<br>Field Name|SQL Datatype|Comments|
|---|---|---|
|CustomerTypeID|Integer|The unique ID assigned byFirestorm® to this customer type|
|Code|String|Code representing the type of customer that corresponds to this<br>customer type ID. This code will displayin all areas of the system.|



##### Code: COUNTRY 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|CountryID|String|The 2 or 3 char code currently used by Firestorm to identify this<br>country. Note: If this value is a 2 char code, then Firestorm is<br>configured to use 2 character country codes everywhere. If this is a<br>3 char code, then the system uses 3 char codes everywhere.<br>You MUST use this value for all other web service calls!|
|Name|String|Descriptive name for the country (i.e: USA = United States of<br>America)|
|2CharCountryCode|String|The ISO 2-character code for this country|
|3CharCountryCode|String|The ISO 3-character code for this country|



##### Code: STATES **(Requires a valid COUNTRYID in Code2)** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|StateID|String|The 2 or 3 char code currently used by Firestorm to identify this<br>state. Note: If this value is a 2 char code, then Firestorm is<br>configured to use 2 character state codes everywhere. If this is a 3<br>char code, then the system uses 3 char codes everywhere.<br>You MUST use this value for all other web service calls!<br>This web service will only return those states that have been<br>assigned to the requested countryas specified in Code2|
|Name|String|Descriptive name for the country (i.e: USA = United States of<br>America)|
|2CharStateCode|String|The ISO 2-character code for this state|
|3CharStateCode|String|The ISO 3-character code for this state|



##### Code: SHIPPER **(Optionally place a valid CATALOGUEID in Code2)** 

|Returned Data<br>|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|ShipperID|integer|The unique ID assigned by Firestorm® to this shipper.|
|||If**Code2**is populated with a CatalogueID, then this web service will<br>only return those shippers that have been assigned to the catalogue<br>in the admin console.|
|Code|String|Short code used by admin for this shipper. Most reports also use<br>this short code to save space.|
|Description|String|Full description of a shipper.(i.e.: United Parcel Service vs. UPS)|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 314 | 317 

Firestorm® Web Services API | Version 2.2.33 

##### Code: CATALOGS or CATALOGUES 

|Returned Data|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|CatalogueID|integer|The unique ID assigned by Firestorm® to this shipper.<br>If**Code2**is populated with a CatalogueID, then this web service will<br>only return those shippers that have been assigned to the catalogue<br>in the admin console.|
|Name|String|Short code used by admin for this shipper. Most reports also use<br>this short code to save space.|
|WebCatalogueName|String|Full description of a shipper.(i.e.: United Parcel Service vs. UPS)|
|IsPublic|Boolean|Flag to indicate if this is a public catalog.<br>0 = false<br>-1 = true|
|IsEnrollment|Boolean|Flag to indicate if this is an enrollment catalog.<br>0 = false<br>-1 = true|
|IsAutoship|Boolean|Flag to indicate if this is an Autoship catalog.<br>0 = false<br>-1 = true|
|EligibleForRecurringOrder|Boolean|Flag to indicate if this is a catalog can be used for recurring orders.<br>0 = false<br>-1 = true|
|IsParty|Boolean|Flag to indicate if this is a party catalog.<br>0 = false<br>-1 = true|
|UseDateFiltering|Boolean|Flag to indicate if this catalog should only be used between the start<br>date and end date. This this value is -1, then you must check the<br>date ranges before attempting to use it.<br>0 = false<br>-1 = true|
|StartDate|Date|Startingdate/time that this catalogmaybe used|
|EndDate|Date|Endingdate/time that this catalogmaybe used|



##### Code: PAYMENTTYPE 

|Returned Data|||
|---|---|---|
|Field Name|SQL Datatype|Comments|
|PaymentTypeID|integer|The unique ID assigned by Firestorm® to this shipper.<br>If**Code2**is populated with a CatalogueID, then this web service will<br>only return those shippers that have been assigned to the catalogue<br>in the admin console.|
|Code|String|Short code used by admin for this shipper. Most reports also use<br>this short code to save space.|
|Description|String|Full description of a shipper.(i.e.: United Parcel Service vs. UPS)|
|IsCreditCard|Boolean|Flag to indicate if this payment type is a credit card<br>0 = false<br>-1 = true|
|Unfunded|Boolean|Flag to indicate if this payment type is unfunded. Typically used for a<br>placeholder. Our Implementation team will tell you when to use this<br>payment type.<br>0 = false<br>-1 = true|
|IsCheck|Boolean|Flag to indicate if this payment type is a check. Checks require<br>specialconfiguration and additional processing in Firestorm. Before<br>using this payment type, please coordinate with your Firestorm<br>implementation team.<br>0 = false<br>-1 = true|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 315 | 317 

Firestorm® Web Services API | Version 2.2.33 

|AcceptedForRecurringOrders|Boolean|Flag to indicate if this payment type may be used on a recurring<br>order (Autoship)<br>0 = false<br>-1 = true|
|---|---|---|



C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 316 | 317 

Firestorm® Web Services API | Version 2.2.33 

C o p y r i g h t 2 0 1 4 - 2 0 2 6 T r i n i t y S o f t w a r e I n c . P a g e 317 | 317 

