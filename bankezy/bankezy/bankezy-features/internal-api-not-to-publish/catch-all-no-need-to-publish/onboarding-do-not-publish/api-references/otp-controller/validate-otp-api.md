---
description: This API is used to validate the OTP
---

# Validate OTP API

{% swagger method="post" path="" baseUrl="http://192.168.105.70:8083//onboarding/otp/validateOTP/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" required="true" %}
User mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpRef" required="true" %}
Otp reference value
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpVal" required="true" %}
OTP value
{% endswagger-parameter %}

{% swagger-parameter in="body" name="token" required="true" %}
Otp token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="true" %}
Otp device id
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-TOKEN" %}
TOKEN
{% endswagger-parameter %}
{% endswagger %}

{% tabs %}
{% tab title="Request" %}
```json
{
    "mobile" :"7827737375",
    "otpRef" : "32e82c97-79df-4c5c-af46-2564058d2e9f",
    "otpVal" : "168896",
    "otpEventType": "ENROLL",
    "token" :"",
    "deviceId" :""
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'http://192.168.105.70:8083//onboarding/otp/validateOTP/v1' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: application/json'
--data-raw '{
    "mobile" :"7827737375",
    "otpRef" : "32e82c97-79df-4c5c-af46-2564058d2e9f",
    "otpVal" : "168896",
    "otpEventType": "ENROLL",
    "token" :"",
    "deviceId" :""
}'
```
{% endtab %}
{% endtabs %}
