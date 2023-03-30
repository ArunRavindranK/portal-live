---
description: This API helps to save the user credentials into BankEzy.
---

# Save Credentials API



{% swagger method="post" path="" baseUrl="<domain>/onboarding/user/saveCredentials/v1 " summary="" %}
{% swagger-description %}
This API helps to save the user credentials into BankEzy. There are two different ways of login options are there&#x20;

&#x20;                     1\. Pin Based Login (4 Digit numerical value)

&#x20;                     2\. Device Based Login (Bio metric authentication)
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../common-apis/get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" %}
text/plain
{% endswagger-parameter %}

{% swagger-parameter in="body" name="keyRef" required="true" %}
Public Key Reference to b passed for device based authentication which was shared on 

[Public Key API](../biometric-authentication/public-key-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="pin" required="true" %}
Based on signInMode pin can be vary.

Pin Based Auth - 4 digit pin

Device Based Auth - encrypted device uniqueId with public key shared on [Publick Key API](../biometric-authentication/public-key-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="signInMode" required="true" type="int" %}
1 - Pin based authentication

2 - Device based authentication
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":{
      "msg":"PIN set successfully"
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
{% tab title="Sample Curl Request" %}
```json
curl --location --request POST 'http://localhost:8083/onboarding/user/saveCredentials/v1'
--header 'X-API-TOKEN: token'
--header 'Content-Type: text/plain'
\--header 'X-API-KEY:MOB-APP-2001'
--data-raw '{ "keyRef": "", "pin": "1111", "signInMode": 1 }'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
   "keyRef":"", //Public key ref to be passed for Device based authentication
   "pin":"1111",
   "signInMode":1 //1-PIN based Auth, 2-Device based Auth
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":{
      "msg":"PIN set successfully"
   }
}
```
{% endtab %}
{% endtabs %}
