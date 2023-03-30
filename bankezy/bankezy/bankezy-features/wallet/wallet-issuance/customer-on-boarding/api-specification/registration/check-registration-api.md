---
description: >-
  This API is intended to check if the user has been registered in the system
  and is eligible to proceed further.
---

# Check Registration API

{% swagger method="post" path="" baseUrl=" <domain>/onboarding/user/checkRegStatus/v1 " summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the

[Get Token API](../../../../../market-place/api-specification/get-token-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="appVersion" required="true" %}
The current app version which the user is using
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" required="true" %}
Country code Example : +91
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" required="true" %}
Unique identifier for a user provided by the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="moreInfo" type="boolean" required="false" %}
If additional info is required pass true
{% endswagger-parameter %}

{% swagger-parameter in="body" name="osType" required="true" %}
Indicates the OS type as either Android / iOS
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" %}
text/plain
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="false" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":[
      {
         "registered":false,
         "mobile":"7000000002",
         "signInMode":0,
         "accountNumber":0,
         "deviceId":null,
         "appUpdateRequired":false
      }
   ]
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
{% tab title="Sample curl request" %}
```json
curl --location --request POST 'http://localhost:8083/onboarding/user/checkRegStatus/v1' \
--header 'X-API-TOKEN: tokenvalue'
--header 'Content-Type: text/plain'
\--header 'X-API-KEY:MOB-APP-2001'
--data-raw '{
    "mobile":"1420200033",
    "otpRef":"",
    "moreInfo":true,
    "appVersion":"2.14.00.02",
    "osType":"Andriod"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
   "appVersion":"2.10.00.00",
   "countryCode":"+91",
   "mobile":"7000000002",
   "moreInfo":true,
   "osType":"Android"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":[
      {
         "registered":false,
         "mobile":"7000000002",
         "signInMode":0,
         "accountNumber":0,
         "deviceId":null,
         "appUpdateRequired":false
      }
   ]
}
```
{% endtab %}
{% endtabs %}
