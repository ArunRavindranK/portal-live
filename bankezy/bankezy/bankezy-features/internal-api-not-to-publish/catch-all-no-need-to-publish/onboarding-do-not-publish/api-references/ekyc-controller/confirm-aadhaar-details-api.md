---
description: This API is used to verify Aadhar details confirmation.
---

# Confirm Aadhaar Details API

{% swagger method="post" path="" baseUrl="http://192.168.105.70:8083/onboarding/ekyc/v1/aadhaar/userConfirmation" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="name" required="true" %}
User name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gender" required="true" %}
User gender
{% endswagger-parameter %}

{% swagger-parameter in="body" name="dob" required="true" %}
User date of birth
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" required="true" %}
User Address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="aadhaarNumber" required="true" %}
User Aadhar number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="traceId" required="true" %}
User trace id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="unMaskedAadharNumber" required="true" %}
User unmask aadhar number
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
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
    "name" : "Bal",
    "gender" : "male",
    "dob" : "15/04/1992",
    "address" :"",
    "aadhaarNumber" : "999643198087",
    "traceId" : "d8d29bad-5c4f-4f23-b0e4-86db0d1c289",
    "unMaskedAadharNumber" : ""
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "resCode": 150,
    "resDesc": "Confirm Aadhar details failed",
    "errorMessage": "OTP entered is invalid, retry with a valid OTP"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
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
