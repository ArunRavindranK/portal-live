---
description: >-
  This API is used to verify Aadhar by generating OTP to the Aadhar linked
  mobile number.
---

# Verify Aadhar API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/ekyc/v1/aadhaar/verify/number" summary="" %}
{% swagger-description %}
Verify Aadhaar Number by generating OTP to aadhaar linked mobile number
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the

[login API](../../authentication-and-authorization/login-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="aadhaarNumber" required="true" %}
Aadhar number of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userName" required="true" %}
User name entered by the user
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "Success",
    "data": {
        "traceId": "4e932354-e57d-4e67-80f2-6b669ed906cd"
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
{% tab title="Sample curl request" %}
```json
curl --location --request POST 'http://localhost:8083/onboarding/ekyc/v1/aadhaar/verify/number/' \
\--header 'Content-Type: text/plain'
\--header 'X-API-TOKEN: token'
\--header 'X-ACCOUNT-NUMBER: 312'
\--header 'X-API-KEY: MOB-APP-2001'
--data-raw '{
  "aadhaarNumber": "123456789012",
  "userName": "abc G"
}
'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "aadhaarNumber": "123456789012",
  "userName": "abc G"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "Success",
    "data": {
        "traceId": "4e932354-e57d-4e67-80f2-6b669ed906cd"
    }
}
```
{% endtab %}
{% endtabs %}
