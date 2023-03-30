---
description: >-
  In some scenario if OTP is not received to the user, at that time this api is
  used to create a new OTP to the user
---

# Resend OTP API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/ekyc/v1/aadhaar/verify/resendOtp" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the

[login API](../../authentication-and-authorization/login-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="previousTraceId" required="true" %}
TraceId from

[verify Aadhar API](verify-aadhar-api.md)

response
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "Success",
    "data": {
        "traceId": "be8587bd-3bf0-42b0-acc4-a35b9746f64f"
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
{% tab title="Sample curl request " %}
```json
curl --location --request POST 'http://localhost:8083/onboarding/ekyc/v1/aadhaar/verify/resendOtp' \
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API: 1111'
\--header 'Cookie: JSESSIONID=C0D114845B4EC3A92A840A1B862E96F4'
\--data-raw '{
    "previousTraceId" : "e849af82-9d1f-4cc9-9d8a-376b06c11187"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "previousTraceId" : "e849af82-9d1f-4cc9-9d8a-376b06c11187"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "Success",
    "data": {
        "traceId": "be8587bd-3bf0-42b0-acc4-a35b9746f64f"
    }
}
```
{% endtab %}
{% endtabs %}
