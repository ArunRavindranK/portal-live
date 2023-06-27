---
description: This API is used to verify the Aadhar OTP.
---

# Aadhaar Verify Otp API

{% swagger method="post" path="" baseUrl="http://192.168.105.70:8083/onboarding/ekyc/v1/aadhaar/verify/otp" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="199" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

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
    "otp": "107400",
    "traceId": "d8d29bad-5c4f-4f23-b0e4-86db0d1c289f"
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "resCode": 150,
    "resDesc": "Aadhaar OTP verification failed",
    "errorMessage": "OTP entered is invalid, retry with a valid OTP"
}
```
{% endtab %}

{% tab title="Sample  Curl Command" %}
```json
curl --location --request POST 'http://192.168.105.70:8083/onboarding/ekyc/v1/aadhaar/verify/otp' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: application/json'
--data-raw '{
    "otp": "107400",
    "traceId": "d8d29bad-5c4f-4f23-b0e4-86db0d1c289f"
}'
```
{% endtab %}
{% endtabs %}
