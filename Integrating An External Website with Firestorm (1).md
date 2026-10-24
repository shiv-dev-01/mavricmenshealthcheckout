Jan 11, 2016

Integrating External Websites with Firestorm®

All code samples provided in this document use Visual Basic in an ASP.NET environment and are

provided as‐is, with no warranty of any kind.

If you have made the decision to host your corporate website on your own servers (ie: NOT in our hosting facility), you will need to follow the steps outlined here in order to successfully integrate your website with the following processes:

- The proper display of Replicating websites

- Linking to the enrollment process

- Shopping cart

- Logging into the members web office

When integrating your website with the Firestorm® system, a few basic steps are required for a successful integration. Following the instructions presented here will allow you to complete your integration and deployment with a minimum of issues.

- 1. Register a domain that will be used to access the back office

Using a service such as Register.com or Network Solutions or GoDaddy.com, select a domain name that will be used in all references to the website that will be parked on the Firestorm® servers. Even though you are hosting the corporate website on your own server, all of the Firestorm® web pages and Backoffice functionality will still reside on our servers in our hosting facility.

While not required for a deployment, this step will make getting a secure server certificate (SSL)

much easier and will save aggravation later.

When registering the domain, make sure you point the DNS “A” record to the IP address that

was provided to you by our office. THIS STEP IS CRITICAL TO THE PROPER FUNCTIONING OF YOUR WEBSITE!

2. Obtain a Secure Server Certificate (SSL) from an issuing authority

Once your domain is registered and pointing to our servers, you will need to obtain an SSL

certificate from a proper issuing authority. You can use any service you like to get this item. Common providers are GoDaddy.com (cheapest) to Network Solutions (most expensive).

In order to begin this process, you will need to contact our office and request us to issue a request for an SSL certificate. We do this by generating a request file from our web servers and then send this file to you. YOU MUST HAVE THIS FILE IN ORDER TO COMPLETE YOUR PURCHASE

OF AN SSL CERTIFICATE!


- 3. Obtaining Replicating Website Data

Replicating websites are created from data that is stored in the Firestorm® database and then displayed on your web pages in the manner in which you desire. The following items are

available for you to display:

- ID#

- First Name

- Last Name

- Company Name

- Home Phone

- Work Phone

- Primary Email

- Web Greeting

And

- Member’s picture

This data is obtained from the Firestorm® system by performing an XML HTTPPost to a special URL that will return these items in a delimited string format. (This pertains to all items listed above except for the Member’s picture… that is obtained with another call which we will discuss

later).

When a request is made to pull up a member’s replicated website, the following style of URL is entered into a browser:

[http://www.yourcompany.com/billsmith](http://www.yourcompany.com/billsmith)

Since the page “billsmith” does not physically exist on your web server, this will generate a 404 “page not found” error. Replicating websites work by intercepting this error. This is done by creating and assigning a custom error handler web page in IIS to your website for error number 404. (Note: you must have access to the IIS control panel in Windows to be able to do this!)

When a 404 error is detected, you should perform the following steps inside your custom 404

error handler page:

- a) Parse out the URL to obtain the value “billsmith”


b) Send the value to the Firestorm® servers using an XML HTTPPost to the following

URL:

https://www.yourbackofficedomain.com/MemberToolsDotNet/Utils/GetReplicated Details.aspx?DealerURL=billsmith [URL 🔗](https://www.yourbackofficedomain.com/MemberToolsDotNet/Utils/GetReplicatedDetails.aspx?DealerURL=billsmith)

Tip: Don’t forget to URLEncode the “billsmith” value!

The response from this URL will be a pipe “|” delimited string containing the following information:

STATUS|DEALERID|FIRSTNAME|LASTNAME|COMPANY|HPHONE|WPHONE|EMAIL| WEBGREETING

You will need to parse out this string and store each field in a separate variable. After the parse is completed, you must check the “status” field to determine if a lookup was successful or not. The following values are valid for the “status” field:

Success

Good lookup. Proceed

Not Found

The requested replicated page name (DealerURL) could not be locate dinthe database. In this scenario you cannot display the replicated information. You should display a standard “404 Page Not Found” error.

No DealerURL Provided

The page was called without the proper arguments. No other data is provided. In this scenario you cannot display the replicated information. You should display a standard “404 Page Not Found” error.

Error Occurred: <error text> Some type of system error occurred. The actual error text will be provided

after the “:” character. In this scenario you cannot display the replicated information. You should display a standard “404 Page Not Found” error.

- c) Upon success, you will need to assign the values to local variables and then populate session variables for each of the values provided to you in the return string. Session variables can be named anything you wish.

You can store these values in the session as follows:


- a. Session(“ReferringDealerID”) = DealerID

- b. Session(“FirstName”) = FirstName

- c. Session(“LastName”) = LastName

- d. Session(“CompanyName”) = Companyname

- e. Etc….

Tip: Set a value in the session to indicate that you are in a “Replicated” website.

This will make the code in your other pages easier to understand!

Session(“IsReplicated”) = 1

- d) Once the session is populated, your will then need to redirect the user’s browser to the main page of your website as follows:

```
a. Response.redirect(“YourMainPage.aspx”)
```

## 4. Displaying Textual Replicated Website Data

Once you have successfully obtained the information for the replicated website from the Firestorm® system as described in step 3, you are ready to add code to your web page to actually display it.

To display the value contained in a session variable (populated in step 3), simply add the following code to your HTML in the appropriate places:

```
<table>
<tr>
<td>
Hello! My name is <%=session(“FirstName”)%> Welcome to my website!
</td>
</tr>
</table>
```

You can reference any session variable you created in step 3 in this manner. Use your imagination and creative abilities to display the information any way you wish.

## Tip:

Be aware that users can and will add their own HTML code to the “WebGreeting” value returned by the Firestorm® system. In your design, you must allow for this so errors will not be caused if a


user does this. Any HTML is allowed in this field with the exception of the “<HTML>” and

“<BODY>” tags.

- 5. Displaying a Members picture

To display a member’s picture in your web page, a special URL is provided for you that can be imbedded in an “<IMG>” tag as follows:

<img src=”http://www.yourbackofficedomain.com/MemberToolsDotNet/Utils/ReturnDealerImage.as px?DealerID=<%=session(“ReferringDealerID)%>” height=100 width=100> [URL 🔗](http://www.yourbackofficedomain.com/MemberToolsDotNet/Utils/ReturnDealerImage.aspx?DealerID=%3c%25=session()

This page will return a binary stream that will look like a .jpg image to the browser. It is strongly suggested that you place height and width attributes in the image tag to prevent formatting problems. Firestorm® allows configuration of a maximum image size (in bytes) so if you don’t do this, your formatting could be blown.

- 6. Other links you will need for replicated websites

It is important to ensure that the referring member gets proper credit for any enrollment or order that comes through a replicating website. Using the links below will make sure that everything is credited properly.

Depending on the needs of your company, here are the other links that may or may not be required in your integration:

Public Shopping (retail only):

<a href=’ http://www.yourbackofficedomain.com/MemberToolsDotNet/ShoppingCartV4/StartPublicShop ping.aspx?ReferringDealerID=<%session(“ReferringDealerID”)%>’>Click Here To Shop</a>

Enrollment:

<a href=’ http://www.yourbackofficedomain.com/MemberToolsDotNet/Enrollmentv4/StartPublicEnrollm ent.aspx/EnrollmentCode=DEALER&ReferringDealerID=<%session(“ReferringDealerID”)%>’>Click Here To Enroll</a>


Logging Into the Members Web Office:

<a

href=’http://www.yourbackofficedomain.com/membertoolsdotnet/Login/FirestormLogin.aspx>

## SAMPLE CODE

The following page is provided as an example of how to make the proper system calls to retrieve information from the Firestorm® system.

```
<%@ Page Language="VB"%>
<%
'' *******************************************************************
'' The code provided in this example is provided as-is with no warranty
'' of any kind and is not intended for use in a production system.
'' This is only an example of how to make the calls required to pull
'' replicated website information from Firestorm(r) for display on your
'' web pages.
'' Copyright 2016 Trinity Software Incorporated
'' All Rights Reserved
'' *******************************************************************
''///////////////////////////////////////////////////////////////
'' REPLACE THIS URL WITH YOUR OWN DOMAIN NAME, NO TRAILING SLASH!
''///////////////////////////////////////////////////////////////
Const WORKURL As String = "http://www.yourbackofficedomain.com"
'' declare variables for later use
Dim IsReplicated As Boolean
Dim ExtractedDealerURL As String
Dim oXMLHTTP As Object
Dim ResponseString As String
Dim ResultStatus As String
Dim DealerID As Long
Dim FirstName As String
Dim LastName As String
Dim CompanyName As String
Dim HomePhone As String Dim
WorkPhone As String
Dim EmailPrimary As String
Dim WebGreeting As String
Dim ReferrerName As String
'' the first thing we need to do is get the dealer's url
ExtractedDealerURL = vbNullString
ExtractedDealerURL = Request.QueryString("DealerURL")
'' NOTE: depending on the format of the url you wish to use,
'' you will need to parse out the dealer url before passing
'' it into this example.
```


```
'' now that we have extracted the dealer url,
'' we need to use it to get the dealer info
If (ExtractedDealerURL = vbNullString) Then
Response.Write("No Dealer URL Supplied!")
End If
'' get the dealer info
If (ExtractedDealerURL <> vbNullString) Then
'' create the object (this is the object
'' that will post to the desired page and return us our value)
oXMLHTTP = CreateObject("Microsoft.XMLHTTP")
'' post to the detail page and capture the info
Try
oXMLHTTP.Open("GET", WORKURL &
"/MemberToolsDotNet/Utils/GetReplicatedDetails.aspx?DealerURL=" &
ExtractedDealerURL.ToString, False)
oXMLHTTP.Send()
ResponseString = vbNullString
ResponseString = oXMLHTTP.responseText
If (Len(ResponseString) > 0) Then
'' now that we have a response, we can
'' parse it out and populate our variables
'' *****************************
'' PARSE RESPONSE
'' *****************************
'' This is a pipe delimited string.
ResultStatus = Left(ResponseString, InStr(ResponseString,
"|") - 1) & vbNullString
'' trim the string
ResponseString = Right(ResponseString, (Len(ResponseString) -
Len(ResultStatus) - 1))
'' get the rest of the info
DealerID = Left(ResponseString, InStr(ResponseString, "|") -
1) & vbNullString
ResponseString = Right(ResponseString, (Len(ResponseString) -
Len(DealerID.ToString) - 1))
FirstName = Left(ResponseString, InStr(ResponseString, "|") -
1) & vbNullString
ResponseString = Right(ResponseString, (Len(ResponseString) -
Len(FirstName) - 1))
```


```
LastName = Left(ResponseString, InStr(ResponseString, "|") -
1) & vbNullString
ResponseString = Right(ResponseString, (Len(ResponseString) -
Len(LastName) - 1))
CompanyName = Left(ResponseString, InStr(ResponseString, "|")
- 1) & vbNullString
ResponseString = Right(ResponseString, (Len(ResponseString) -
Len(CompanyName) - 1))
HomePhone = Left(ResponseString, InStr(ResponseString, "|") -
1) & vbNullString
ResponseString = Right(ResponseString, (Len(ResponseString) -
Len(HomePhone) - 1))
WorkPhone = Left(ResponseString, InStr(ResponseString, "|") -
1) & vbNullString
ResponseString = Right(ResponseString, (Len(ResponseString) -
Len(WorkPhone) - 1))
EmailPrimary = Left(ResponseString, InStr(ResponseString, "|")
- 1) & vbNullString
ResponseString = Right(ResponseString, (Len(ResponseString) -
Len(EmailPrimary) - 1))
WebGreeting = Left(ResponseString, InStr(ResponseString, "|")
- 1) & vbNullString
'' *****************************
'' END PARSE RESPONSE
'' *****************************
'' now we need to format the ReferrerName field so that is
'' displays according to Firestorm Standard.
'' ie: the Company Name always takes priority over
'' the First Name and Last Name fields
If (CompanyName <> vbNullString) Then
ReferrerName = CompanyName
Else
ReferrerName = FirstName & " " & LastName
End If
'' now we need to populate the session information
'' with what we have gathered
'' *****************************
'' POPULATE SESSION
'' *****************************
Session("ReferringDealerID") = DealerID
Session("ReferrerName") = ReferrerName
Session("ReferrerGreeting") = WebGreeting
```


```
Session("ReferrerEmail") = EmailPrimary
Session("ReferrerPhone") = WorkPhone '' this can be whichever
phone number you wish
Session("ReferrerPhoneSecondary") = HomePhone '' this can be
whichever phone number you wish
'' *****************************
'' END POPULATE SESSION
'' *****************************
'' now that we have the session info stored, we can use it
later in the page!
Else
Response.Write("Could not Retrieve Dealer Info! (No Data
Returned)")
End If
Catch ex As Exception
Response.Write("Could not Retrieve Dealer Info! (Communication
Error)")
End Try
'' clean up!
oXMLHTTP = Nothing
End If
%>
<html>
<head>
<title>Offsite Integration Example Using VB.Net</title>
</head>
<body>
<%
'' Here, we want to retrieve the user's image and display it on
the page. We can use the information stored
'' in the session to do it in conjuction with a special url!
If (IsNumeric(Session("ReferringDealerID")) AndAlso
Session("ReferringDealerID") > 0) Then
%><img
src='<%=WORKURL%>/MemberToolsDotNet/Utils/ReturnDealerImage.aspx?DealerID=<%=
Session("ReferringDealerID")%>' border=0 height=100 width=100 /> <%
End If
%>
<br />
<br />
<%
'' now we will display the users personal info.
```


If (IsNumeric(Session("ReferringDealerID")) AndAlso

Session("ReferringDealerID") > 0) Then

%>

<font face='arial'>

<h2><%=Session("ReferrerName")%></h2> <br /> Primary Phone: <%=Session("ReferrerPhone")%> <br /> Secondary Phone: <%=Session("ReferrerPhoneSecondary")%> <br /> Email: <%=Session("ReferrerEmail")%> <br /> <br /> <%=Session("ReferrerGreeting")%>

</font>

<% End If

%>

</body>

</html>
