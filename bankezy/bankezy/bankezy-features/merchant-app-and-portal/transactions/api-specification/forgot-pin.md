---
description: >-
  If Merchant forgot the Pin, He can select Forgot Pin option to reset the Pin.
  PAN Number is used for authentication.
---

# Forgot Pin

{% swagger method="post" path="/onboarding/user/kyc/v1/validatekyc" baseUrl="<domain>" summary="ValidateKyc" %}
{% swagger-description %}
This is to validate the given kyc doc id.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" type="String" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" type="String" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="body" name="kycDocId" type="int" required="true" %}
Kyc doc id
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="idNumber" type="String" %}
Kyc doc id number
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

{% swagger-response status="403: Forbidden" description="" %}
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
{% tab title="Sample curl command" %}
```json
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/onboarding/user/kyc/v1/validatekyc' \
--header 'X-API-TOKEN: token' \
--header 'X-API-KEY: MOB-APP1-1114' \
--header 'Content-Type: application/json' \
--data-raw '{
    "kycDocId":2,
    "idNumber": "CFWPK1905F"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json

{
    "kycDocId":2,
    "idNumber": "CFWPK1905F"
}

```
{% endtab %}

{% tab title="Response sample" %}
```json

{
    "resCode": "ONB_2000",
    "resDesc": "SUCCESS"
}

```
{% endtab %}
{% endtabs %}

## Custom response codes

| Response code | Response description    |
| ------------- | ----------------------- |
| ONB\_2000     | SUCCESS                 |
| ONB\_2010     | MISMATCH\_IN\_KYC\_INFO |
| ONB\_5000     | TRY\_LATER              |
