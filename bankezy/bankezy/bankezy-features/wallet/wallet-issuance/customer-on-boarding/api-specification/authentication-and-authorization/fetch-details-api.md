---
description: This API helps to return customer details
---

# Fetch Details API

{% swagger method="get" path="" baseUrl="<domain>/onboarding/userProfile/fetchDetails/v1 " summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the

[login API](login-api.md)

or

[Get Token API](../../common-apis/get-app-token-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="false" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":{
      "bankCustomer":false,
      "accountNumber":1477,
      "firstName":null,
      "middleName":null,
      "lastName":null,
      "gender":null,
      "allowEdit":0,
      "mobile":"7000000002",
      "emailId":null,
      "preferredLanguage":null,
      "kycLevel":0,
      "kycName":null,
      "kycDisplayName":null,
      "age":null,
      "walletStatus":"",
      "walletCreated":false,
      "vpa":null
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

{% tabs %}
{% tab title="Sample Curl Request " %}
```json
curl --location --request GET 'https://payment1.pcdev.enstage-sas.com/onboarding/userProfile/fetchDetails/v1'
\--header 'X-API-TOKEN:token'
\--header 'X-API-KEY:MOB-APP-2001'
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":{
      "bankCustomer":false,
      "accountNumber":1477,
      "firstName":null,
      "middleName":null,
      "lastName":null,
      "gender":null,
      "allowEdit":0,
      "mobile":"7000000002",
      "emailId":null,
      "preferredLanguage":null,
      "kycLevel":0,
      "kycName":null,
      "kycDisplayName":null,
      "age":null,
      "walletStatus":"",
      "walletCreated":false,
      "vpa":null
   }
}
```
{% endtab %}
{% endtabs %}
