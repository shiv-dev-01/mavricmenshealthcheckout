November 12, 2025 **[USING CREDENTIAL-LESS SEAMLESS LOGIN WITH FIRESTORM]** 

Using Credential-less Inbound Seamless Login with the Firestorm System 

Using Credential-Less Seamless Login with Firestorm – Copyright 2025 Trinity Software Incorporated Page 1 

November 12, 2025 **[USING CREDENTIAL-LESS SEAMLESS LOGIN WITH FIRESTORM]** 

# **1. Introduction** 

With many external integration scenarios, it is often desirable to be able to allow users to log into their Firestorm web back office without having to re-enter their login credentials from an external 3<sup>rd</sup> party system, or even directly from your corporate website. This is known as a seamless login request, sometimes also referred to as Single Sign On. 

In today’s high security world, it is very common to be unable to retrieve or share a user’s login credentials. This is a normal security practice and is implement to help prevent account compromise and data theft. For systems where this is not possible, a common alternative is to have the user link their two accounts through a manual process, but this can often times be confusing or fragile in execution. 

For systems where that implementation method is not possible due to technical limitations or is not appropriate for the user base, the only remaining option for implementing a seamless login capability is to implement one that does not rely on traditional login credentials or user authorization tokens. This is known as credential-less seamless login. This method of seamless login relies on a set of private data that is held by both the external system and Firestorm, along with identifying and linking information that the external system can pass to Firestorm to be independently verified by Firestorm to determine the authenticity of the request before allowing access to a user’s Firestorm backoffice. 

This document describes the proper procedures for implementing a credential-less login in to a Firestorm user’s backoffice. 

Obviously, security is a primary concern when allowing this type of access to your Firestorm system. It is imperative that when performing this type of integration that you carefully consider all of the possible security ramifications when implementing the procedures described in this document.  Due to the nature of how a credential-less login system works, it is of utmost importance that you do not allow any third-party systems to integrate with your Firestorm system using this option unless you have a high level of trust in them. It is your responsibility to ensure that you properly vet any thirdparty system that you wish to integrate with your Firestorm system to help make sure that your Firestorm system remains secure. 

To successfully implement the procedures described here, you (or your developer) must have a working knowledge of RSA Encryption, familiarity with a programming language of their choice (C#, VB.NET, PHP, etc..), JSON, base64 and UTF8 encoding, and how to properly handle internet routing requests. 

Using Credential-Less Seamless Login with Firestorm – Copyright 2025 Trinity Software Incorporated Page 2 

November 12, 2025 **[USING CREDENTIAL-LESS SEAMLESS LOGIN WITH FIRESTORM]** 

# **2. Endpoint URL** 

When attempting a credential-less seamless login, all requests must be sent to the following URL. Replace the <YOURDOMAIN> token with the appropriate domain name of your system: 

https://<YOURDOMAIN>/MemberToolsDotNet/Login/FirestormSSO.aspx 

# **3. Credential-Less Seamless Inbound Login Requests** 

# **a. Getting Started** 

Before you can attempt to process a credential-less login request, you will need to acquire some additional information from Firestorm support personnel. Please send an email to <u>support@trinitysoft.net with your company name, the name of the third-party service you</u> wish to integrate with, and a description of what this third-party service does. Please note, if you are not a Firestorm client directly, please coordinate with our mutual client to have them send this request on your behalf. Due to our security policies, any request received without prior authorization from our client will be ignored. 

Once your request has been authorized, you will be issued the following pieces of information: 

- **Secret Key** – This is a special secret key that will identify the third-party system and must be sent with all credential-less login request. This information should be treated with the same level of security that a password would, and should be securely stored in the third-party system, and not shared with anyone else. _WARNING: Should this secret key every be compromised in any way, it is_ **_<u>imperative</u>_** _that you notify Firestorm support personnel immediately, so that the compromised key can be invalidated and a new one issued. Failure to notify Firestorm support personnel in a timely manner of a secret key compromise can lead to account compromise and data theft. You can notify Firestorm support personnel of a secret key compromise by calling the Firestorm Emergency Support hotline. Please refer to your new client documentation for this phone number._ 

- **Public RSA Key** – This public RSA key will be used to encrypt all credential-less login requests to prevent account compromise. This value should also be stored in the third-party system for ease of access, but it is not considered a secure piece of data and can be stored however works best for the third-party system. 

In addition to the above items, you will also need to know the Firestorm Dealer ID of the account you are generating the credential-less login request for. How you obtain this value 

Using Credential-Less Seamless Login with Firestorm – Copyright 2025 Trinity Software Incorporated Page 3 

November 12, 2025 **[USING CREDENTIAL-LESS SEAMLESS LOGIN WITH FIRESTORM]** 

is dependent on the overall system integration that is established with the third-party system. There are multiple ways that this can be accomplished (Firestorm Web Services, FEPS, etc.) and is outside the scope of this document. 

The last piece of information you will need to have available is a unique identifier from the third-party system. This can be a true ID number, and email address, or any other uniquely identifiable piece of information. Whatever value is chosen for this value must also exist in Firestorm and be linked to the appropriate Firestorm Dealer ID. As with the acquisition of the Firestorm Dealer ID, how this information is properly linked in Firestorm is completely dependent on the overall system integration with the third-party system and is outside the scope of this document. 

Once you have the above information, you can move on to preparing the credential-less seamless login request payload that will be sent to Firestorm to log the user in. 

# **b. Prepare the Credential-Less Seamless Login Request Payload** 

Each credential-less login request that you submit will require a special JSON payload to be created that contains the authorization information. This payload will then be encrypted and encoded in preparation for transmission to Firestorm. The format of the request payload is below: 

{ "fsDealerID": 813132, 

"externalSystemID": "3333948407913", "createdAt": "2025-10-21T08:45:00-05:00", "secretKey": "aFDA$^%w34qagREFGVSFDhg" 

} 

|**Field Name**|**Description**|
|---|---|
|fsDealerID|The Firestorm Dealer ID of the account you<br>want to seamlesslyloga user in to.|
|externalSystemID|The Unique ID of the user in the third-party<br>system. This ID must also exist in Firestorm<br>and be properly linked to the DealerID<br>specified in the fsDealerID field.|
|createdAt|The date and time (including seconds) that<br>this credential-less login request payload was<br>generated. The date format that is required<br>is ISO 8601. Failure to adhere to this format<br>may result in failed login requests.**Note:**<br>**once created, a request payload must be**<br>**used within 15 seconds, or it expires.**|
|secretKey|Your Firestorm issued Secret Key.|



Using Credential-Less Seamless Login with Firestorm – Copyright 2025 Trinity Software Incorporated Page 4 

November 12, 2025 **[USING CREDENTIAL-LESS SEAMLESS LOGIN WITH FIRESTORM]** 

Once you have prepared your payload, you must then encrypt it with the Pubic RSA Key you were issued. How you handle encrypting this value is up to your specific implementation, but you must take care to use UTF-8 encoding when handling the encryption. A sample RSA encryption class is included later in this document that you can use for reference if need. 

**WARNING** : When encrypting the payload, you must take cure to use the proper form of padding. Firestorm expects OAEP SHA-1 padding. Use of PKCS#1 v1.5 or any other form of incompatible padding will result in a failed request. 

Once you have encrypted the payload, you must convert it to a Base64 encoded string. Lastly, you must URL Encode the resulting Base64 encoded string. 

You are now ready to send the credential-less login request to Firestorm. 

# **c. Send the Credential-Less Login Request to Firestorm** 

Once you have successfully prepared the credential-less login request payload, you will need to redirect the user from the third-party system directly to the Firestorm SSO endpoint, along with credential-less request payload. 

To do this, you will add the final URL Encoded request payload to the query string of the Firestorm SSO endpoint using the query string parameter “tok”, then redirect the user to the final URL. 

## Example: 

```
https://<YOURDOMAIN>/MemberToolsDotNet/Login/FirestormSSO.aspx?tok=LwbtzBpVb2a1Qhsog%2fiYEZOxX
miAI54hqvkb1NQqFuTdi%2bDV5tjsYNsQ%2fnx2y62gpimuMP8kqCD9%2fPqmQ5VUnDe7IxYEaYKDfZvcl6yoMtBPJa5rQ
jp6chfISo35pG4d0tMb7baxK9GutAz0mB0Gbm%2fIEJ1iV9qgs60DaUdGZUslSGG5CyBjZLB6Bf9Hxnas8I4fDHMEMkUpA
xtRN3gHCL5hd7vGi%2b4hFVGDKykBbT3r%2fZELW%2bkJjZfCqFlUeRV3klza6n%2bf3IuZ4ejidSPkRO9uEF4gelixuDM
OeLsqYyJAST5JeFTzzpMfT2Oo7HuVmZRvDfkds9U%2fi%2fv3zu7%2f7w%3d%3d
```

Once the user arrives at the Firestorm SSO endpoint, Firestorm will extract the request payload and attempt to authenticate the request. If the request can be properly decoded and authenticated, the user will be logged in to their Firestorm account and routed to the Firestorm Backoffice Dashboard. 

If the request payload cannot be decoded or authenticated for any reason, the seamless login request will fail, and the user will be redirected to the standard Firestorm login page, where they will be required to manually login by entering the account credentials. No error message will be displayed to the user. 

Using Credential-Less Seamless Login with Firestorm – Copyright 2025 Trinity Software Incorporated Page 5 

November 12, 2025 **[USING CREDENTIAL-LESS SEAMLESS LOGIN WITH FIRESTORM]** 

If you encounter difficulties troubleshooting your failed seamless login requests, please reach out to Firestorm support team and we can give you more detailed log information regarding why a seamless login request failed. 

# **d. Route the User to a Specific Location in Firestorm** 

Instead of routing the user to their Firestorm Backoffice Dashboard, you can also specify a destination they should be routed to upon a successful seamless login attempt. 

To do this, you can add an additional query string parameter called “Destination” to the final redirect URL you created in the previous step. The value for this parameter should be a URL Encoded string representing a local path to a resource in the Firestorm backoffice. 

For example, if you wanted to route a user to the Firestorm Tree View report once they were logged in, you would add the following query string parameter and value to your redirect url: 

```
Destination=%2fReports%2fFirestormTreeViewAdvanced.aspx
```

## Complete Example With Override Destination: 

```
https://localhost:49543/Login/FirestormSSO.aspx?tok=PXZ1oOOW%2brhNIW0WTXxGl8TkyTHCAjuBjQxlcXCa
ebHlqrHzUWmo0lAkz7uS9aJFGUPmMZ2UlKuixYRgnS3rj2Zhe2KEF7EK9ScF2s%2fkU28246gOBIUwe9SD3U3rs7%2fsXk
cYTjeuP3xm6nfLInJ004fVRi6w3Jis4FxGi%2fBJ9XjvLXWWFn5vaJZqHjRULzcZfHCqJOkcsVlmBtT9QmQXqIJc1pSYi4
N%2bb%2fbqo0fvRNUubp4JRNN15BNavE1vmJe0Jk8Ypg0GZsYG7Gzeszsz%2bhqRuGvx6jvvXDbeID%2fZgSUpohZJG%2f
204%2bs0yHt4VcPD%2fBGdiH%2fM4OR3gJqnlVDs1Q%3d%3d&Destination=%2fReports%2fFirestormTreeViewAdv
anced.aspx
```

Please note that if the seamless login request fails, the user will be redirected to the standard Firestorm login page, where they will be required to manually login by entering the account credentials. No error message will be displayed to the user and the provided Destination parameter will be ignored. 

# **e. Route the User Back to the Third-Party System on Login Failure** 

If you would rather route the user back to a specific location on the third-party in the event of a seamless login failure, you may optionally supply a Failure Redirect URL that the user will be redirected to in the event their seamless login attempt fails. Utilizing this capability will allow you properly communicate with your users in the event of seamless login failures, as well as allowing them to try again. This also will prevent them from being directed to the main Firestorm login page, which they may be unfamiliar with. 

Using Credential-Less Seamless Login with Firestorm – Copyright 2025 Trinity Software Incorporated Page 6 

November 12, 2025 **[USING CREDENTIAL-LESS SEAMLESS LOGIN WITH FIRESTORM]** 

To do this, you can add an additional query string parameter called “fURL” to the final redirect URL you created in the earlier step. The value for this parameter should be a URL Encoded string representing a fully qualified and secure URL back to a specific location in the third-party system. You may also include any query string parameters on this URL that you may need to properly handle the redirect. These will be returned to the third-party system unmodified. 

For example, if you wanted to route a user back to the third party system hosted at “https://www.mycompany.com” and include a query string parameter “ssofail” with a value of “1”, you would add the following query string parameter and value to your seamless login request redirect url: 

```
fURL=https%3a%2f%2fwww.mycompany.com%3fssofail%3d1
```

## Complete Example With a Failure Redirect URL: 

```
https://localhost:49543/Login/FirestormSSO.aspx?tok=j3G8NR%2fuLih2Tgfh%2bSGqadyE9JAOdjiHzxyPpK
FksN7HnMjrr%2bRq3Es8NdSHTpvQxuQYb%2b0GFnQan6wHNMdcmWrbboHMMHthFuFr1SKZmv%2fEBkUMgXK4RqVwlMST2l
16L7mWcrfutfaWEkycm4Ic0vPcWBb002rVLGMTWs69z86gvLpN2U5vypOb6q34snRGC%2bbVYG8p%2bEQwxOtveQ2KxyVD
xjKOKHxCfSy8gWny2BbBfjJEIs1rZKhsAXChpfXqNFC0AWJzU0fEwM9M3c%2fynT1diMiA%2b6QsmRNcSDw8Kv4bM9m3aG
XhCoSjjNUqsloseXxA8BvLSVe0Vlw8XfiG5g%3d%3d&fURL=https%3a%2f%2fwww.mycompany.com%3fssofail%3d1
```

Please note that the Failure Redirect URL you provide must be a fully qualified and secure URL (it must begin with HTTPS://). Any URL that is received that is not fully qualified and secure will be ignored, and the user will be redirected to the standard Firestorm login page in the event of a seamless login failure. 

# **f. Full Seamless Login Request Redirect URL Parameter List** 

A full breakdown of all possible query string parameters that can be sent with a Seamless Login Request are listed in the table below. 

|**Parameter Name**|**Required**|**Description**|
|---|---|---|
|tok|Yes|The RSA Encrypted, Base64 and URL Encoded<br>Seamless Login Request payload as described in<br>section 3.b.|
|Destination|No|A URL encoded relative path URL to a resource in the<br>Firestorm backoffice that a successfully logged in user<br>will be redirected to once the login process is<br>completed. Described in section 3.d.|
|fURL|No|A URL encoded, fully qualified and secure URL that a<br>user will be redirected to in the event that the<br>seamless login attempt fails. Described in section 3.e.|



Using Credential-Less Seamless Login with Firestorm – Copyright 2025 Trinity Software Incorporated Page 7 

November 12, 2025 **[USING CREDENTIAL-LESS SEAMLESS LOGIN WITH FIRESTORM]** 

# **4. Example RSA Encryption Class** 

Included below is a simple RSA Encryption class coded in VB.Net that you can use to help you implement your own RSA Encryption functions. The function RSAEncrypt() expects the plain text value to encrypt as the first argument, and an RSA Public Key (in XML format) for the second argument. The function will return a Base64 encoded string representing the encrypted value. _This function is meant for illustration only and is provided as-is, without warranty. Proper implementation of the RSA encryption required for Credential-Less Seamless Login functionality is the sole responsibility of the integrating party._ 

```
Imports System
Imports System.IO
Imports System.Security.Cryptography
Imports System.Text
```

```
PublicClassRSACryptoHelper
```

```
Private m_ClassName AsString = "RSACryptoHelper"
```

```
PublicFunction RSAEncrypt(ByVal PlainText AsString, ByVal RSAXMLKey As
String) AsString
```

```
Dim FunctionName AsString = m_ClassName & "." & "RSAEncrypt"
```

```
' // WARNING //
' If you will be passing the encrypted base-64 encoded string
between pages, you MUST URL encode
' the string before passing it on the query string! Base64 encoding
can introduce characters in the
' string that will be interpreted by the browser and will yield
erroneous results on the decrypt!
' // WARNING //
```

```
Dim oRSA AsRSACryptoServiceProvider
```

```
Try
'' initialize the rsa crypto provider and assign our key to use
            oRSA = NewRSACryptoServiceProvider()
            oRSA.FromXmlString(RSAXMLKey)
'' convert the plain text to a byte array
Dim PTBytes AsByte() = Encoding.UTF8.GetBytes(PlainText)
```

```
'' encrypt our plain text - note: the second parameter must be
true to avoid using older PKCS#1 v1.5 padding
Dim EncryptedBytes AsByte() = oRSA.Encrypt(PTBytes, True)
```

```
'' convert the encrypted bytes to a base 64 string
Dim B64EncryptedText AsString
            B64EncryptedText = Convert.ToBase64String(EncryptedBytes)
```

```
'' return the encrypted string
Return B64EncryptedText
```

Using Credential-Less Seamless Login with Firestorm – Copyright 2025 Trinity Software Incorporated Page 8 

November 12, 2025 **[USING CREDENTIAL-LESS SEAMLESS LOGIN WITH FIRESTORM]** 

```
Catch ex AsException
```

```
ThrowNew System.Exception(m_ClassName & "." & FunctionName & ":
" & ex.Message)
```

```
Finally
EndTry
EndFunction
```

```
EndClass
```

Using Credential-Less Seamless Login with Firestorm – Copyright 2025 Trinity Software Incorporated Page 9 

