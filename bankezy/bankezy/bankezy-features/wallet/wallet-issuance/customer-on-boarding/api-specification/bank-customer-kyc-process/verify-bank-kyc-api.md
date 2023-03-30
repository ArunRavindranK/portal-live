---
description: API to verify the KYC details of the customer with bank's system.
---

# Verify Bank KYC API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/kyc/verifyBankKyc/v1 " summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the

[login API](../authentication-and-authorization/login-api.md)

or

[Get Token API](../../common-apis/get-app-token-api.md)

​
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" %}
text/plain
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankCustId" required="true" %}
The unique bank customer id of the customer
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
      "code":"2000",
      "message":"Verified",
      "displayMessage":"Bank KYC successfully completed",
      "kycLevel":150
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
{% code overflow="wrap" %}
```
curl --location --request POST '/onboarding/kyc/verifyBankKyc/v1'
\--header 'X-API-TOKEN: token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain' --data-raw '{ "bankCustId":"11224343434" }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
   "bankCustId":"11224343434"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":{
      "code":"2000",
      "message":"Verified",
      "displayMessage":"Bank KYC successfully completed",
      "kycLevel":150
   }
}
```
{% endtab %}
{% endtabs %}
