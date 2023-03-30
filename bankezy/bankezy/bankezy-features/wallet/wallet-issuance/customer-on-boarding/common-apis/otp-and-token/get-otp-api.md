# Get OTP API

{% swagger method="get" path="" baseUrl="<domain>/onboarding/otp/getOTP/v1" summary="" %}
{% swagger-description %}
This API is used to get the OTP
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The response got from the

[Get Token A](../../../../../market-place/api-specification/get-token-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpRef" required="true" %}
reference value for the OTP
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="false" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "resCode": 200,
        "resDesc": "SUCCESS",
        "resendAttemptsLeft": 2,
        "expireAt": 1651464042000,
        "otpValue": "818643"
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
curl --location --request POST 'http://localhost:8083/onboarding/otp/getOTP/v1' \
\--header 'X-API-TOKEN;' \
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'Content-Type: text/plain' \
\--data-raw '{
   "otpRef":"b43cbdfa-dd44-4bdf-99c2-65a657289501"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
   "otpRef":"b43cbdfa-dd44-4bdf-99c2-65a657289501"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "resCode": 200,
        "resDesc": "SUCCESS",
        "resendAttemptsLeft": 2,
        "expireAt": 1651464042000,
        "otpValue": "818643"
    }
}
```
{% endtab %}
{% endtabs %}
