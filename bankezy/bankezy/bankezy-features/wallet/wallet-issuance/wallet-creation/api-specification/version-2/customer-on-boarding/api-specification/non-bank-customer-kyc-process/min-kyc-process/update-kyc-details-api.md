---
description: >-
  Verifies the user entered document details i.e) PAN and updates the KYC
  details of the user
---

# Update KYC Details API



{% swagger method="post" path="" baseUrl="<domain>/onboarding/user/kyc/v2/verifyKyc " summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../../../../version-1/customer-on-boarding/common-apis/get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="dob" required="true" %}
DOB as given in the document proof (DD/MM/YYYY)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="docId" required="true" %}
Value fetched from 

[Fetch Client Rules API](../../../../../version-1/customer-on-boarding/api-specification/non-bank-customer-kyc-process/min-kyc-process/fetch-client-rules-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="docValue" required="true" %}
Document number as given in the document proof 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" required="true" %}
User email id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gender" required="true" %}
User gender
{% endswagger-parameter %}

{% swagger-parameter in="body" name="groupId" required="true" %}
Value fetched from 

[Fetch Client Rules API](../../../../../version-1/customer-on-boarding/api-specification/non-bank-customer-kyc-process/min-kyc-process/fetch-client-rules-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" required="true" %}
Name as specified in the document proof 
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":{
      "code":"1000",
      "message":"Basic KYC successfully completed",
      "kycLevel":"30",
      "displayMessage":"Basic KYC successfully completed"
   }
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Response Details

<table><thead><tr><th width="212.33333333333331">Response Field</th><th>Field Description</th><th>Data Type</th></tr></thead><tbody><tr><td>code</td><td>response code</td><td>String</td></tr><tr><td>message</td><td>response description</td><td>String</td></tr><tr><td>kycLevel</td><td>level of kyc</td><td>String</td></tr><tr><td>displayMessage</td><td>detailed response message</td><td>String</td></tr></tbody></table>



{% tabs %}
{% tab title="Sample Curl Request" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'http://localhost:8083/onboarding/user/kyc/verifyKyc/v1'
\--header 'X-API-TOKEN: token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
\--header 'Cookie: JSESSIONID=FD96BB282228C8CE2A6B65984B4D60D8'
--data-raw '{ "dob":"01/01/1980", "docId":"ad689f1c-a9d9-449f-897d-33d78ebedfb5", "docValue":"AICER3452C", "email":"abc@gmail.com", "gender":"F", "groupId":"6d1c792b-7f38-498f-a402-d723ac8966a5", "name":"Test K" }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
   "dob":"01/01/1980",
   "docId":"ad689f1c-a9d9-449f-897d-33d78ebedfb5",
   "docValue":"AICER3452C",
   "email":"abc@gmail.com",
   "gender":"F",
   "groupId":"6d1c792b-7f38-498f-a402-d723ac8966a5",
   "name":"Test K"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
   "resCode":"ONB200",
   "resDesc":"SUCCESS",
   "data":{
      "code":"1000",
      "message":"Basic KYC successfully completed",
      "kycLevel":"30",
      "displayMessage":"Basic KYC successfully completed"
   }
}
```
{% endtab %}
{% endtabs %}
