---
description: This API is used to very the SIM.
---

# Sim Verification API

{% swagger method="get" path="" baseUrl="http://192.168.105.70:8083/onboarding/user/auth/simVerification/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-DEVICE-UNIQUEID" required="true" %}
User Device id
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
    // Response
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

{% swagger-response status="404: Not Found" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Response" %}
```json
{
    "resCode": 100,
    "resDesc": "Failure.",
    "errorMessage": "device uniqueID mismatched"
}
```
{% endtab %}

{% tab title="Sample  Curl Command" %}
```json
curl --location --request GET 'http://192.168.105.70:8083/onboarding/user/auth/simVerification/v1' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-DEVICE-UNIQUEID: 869444038444108'
\--header 'X-API-KEY: MOB-APP-2001'
--header 'X-ACCOUNT-NUMBER: 1361'
```
{% endtab %}
{% endtabs %}
