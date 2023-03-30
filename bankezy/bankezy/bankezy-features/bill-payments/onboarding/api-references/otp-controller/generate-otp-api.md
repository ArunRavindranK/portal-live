---
description: This API is used to generate OTP.
---

# Generate OTP API

{% swagger method="post" path="" baseUrl="http://localhost:8083//onboarding/otp/generateOTP/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpEventType" required="true" %}

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

{% swagger-response status="400" description="" %}
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
    "mobile" : "7827737375",
    "email" : "bablu.krishana123@gmail.com",
    "otpEventType" :"ENROLL"
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "otpRef": "267c6076-7eca-430f-a209-2242b2ebd225",
        "otpVal": "720685",
        "mobile": "7827737375"
    }
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'http://192.168.105.70:8083//onboarding/otp/generateOTP/v1' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: application/json'
--data-raw '{
    "mobile" : "7827737375",
    "email" : "bablu.krishana123@gmail.com",
    "otpEventType" :"ENROLL"
}'
```
{% endtab %}
{% endtabs %}

##
