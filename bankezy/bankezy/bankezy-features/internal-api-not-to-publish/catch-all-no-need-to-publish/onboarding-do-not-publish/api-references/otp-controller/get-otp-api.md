---
description: This API is used to get the OTP.
---

# Get OTP API

{% swagger method="post" path="" baseUrl="http://192.168.105.70:8083//onboarding/otp/getOTP/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpRef" required="true" %}
OTP reference value
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
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
{% tab title="Request" %}
```json
{
    "otpRef" : "32e82c97-79df-4c5c-af46-2564058d2e9"
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "resCode": 301,
        "resDesc": "Invalid Otp Reference",
        "resendAttemptsLeft": 0,
        "expireAt": 0
    }
}
```
{% endtab %}

{% tab title="Sample Curl  Command" %}
```json
curl --location --request POST 'http://192.168.105.70:8083//onboarding/otp/getOTP/v1' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: application/json'
--data-raw '{
    "otpRef" : "32e82c97-79df-4c5c-af46-2564058d2e9"
}'
```
{% endtab %}
{% endtabs %}
