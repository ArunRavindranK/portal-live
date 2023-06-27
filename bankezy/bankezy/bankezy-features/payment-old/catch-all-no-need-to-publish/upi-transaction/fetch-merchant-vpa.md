---
description: To fetch the VPA details for give merchant ID and mobile number
---

# Fetch Merchant VPA



{% swagger method="get" path="" baseUrl="<domain>/payments/upi/merchant/vpa/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="x-account-number" required="true" %}
Account Number
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-program-id" required="true" %}
Tenant Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" type="int" required="true" %}
Country code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" required="true" type="long" %}
10 digit mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="long" required="true" %}
Merchant Id, while onboarding a merchant this id will be generated
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
{% endswagger %}

{% tabs %}
{% tab title="Sample Curl Request" %}
```
curl --location --request GET '' \
--header 'x-account-number: 3513' \
--header 'x-program-id: 1111' \
--header 'Content-Type: application/json' \
--data-raw '{
    "countryCode": "91",
    "merchantId": "171756421435003980",
    "mobile": "9019632972"
}'
```
{% endtab %}

{% tab title="Request" %}
```json
{
    "countryCode": "91",
    "merchantId": "171756421435003980",
    "mobile": "9019632972"
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "resCode": "200",
    "resDesc": "SUCCESS",
    "data:": {
        "merchantVpa": "171756421435003980@bankezy"
    }
}
```
{% endtab %}
{% endtabs %}
