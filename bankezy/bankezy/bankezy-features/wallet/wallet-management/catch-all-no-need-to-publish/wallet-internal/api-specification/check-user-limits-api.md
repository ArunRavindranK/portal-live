---
description: >-
  Api to perform the Velocity limits check, weather transaction can be allowed
  or not
---

# Check user limits API

{% swagger method="post" path="" baseUrl="<domain>/wallet/internal/check/user/limits/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
​The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardNumber" type="String" required="true" %}
CardNumber
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productType" type="String" required="true" %}
Product Type(wallet type ex: RW)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" type="Int" required="true" %}
​txn Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnFlow" type="String" required="true" %}
txn Flow
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" type="String" required="true" %}
txn Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" type="Int" required="true" %}
wallet Id
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="201: Created" description="" %}
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

| Response code | Response description                             |
| ------------- | ------------------------------------------------ |
| 37            | amount is zero                                   |
| 101           | ​customerid/walletid or product type is mismatch |
| 110           | Transaction Flow is Mandatory                    |

{% tabs %}
{% tab title="Sample curl command" %}
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/internal/check/user/aml-limits/v1'

\\--header 'Content-Type: text/plain'

```
\--header 'X-API-KEY: MOB-APP-2001'
```

\\--header 'X-API-TOKEN:token' --data-raw '{ "productType": "string", "txnAmount": 0, "txnType": "string", "walletId": 1 }'​
{% endtab %}

{% tab title="Request" %}
```
{
  "cardNumber": "string",
  "productType": "string",
  "txnAmount": 0,
  "txnFlow": "string",
  "txnType": "string",
  "walletId": 1
}
```
{% endtab %}

{% tab title="Response" %}
200 -> allow transaction

201 -> Created

401 -> Unauthorized

403 -> Forbidden

404 -> Not Found

500 -> INTERNAL ERROR
{% endtab %}
{% endtabs %}
