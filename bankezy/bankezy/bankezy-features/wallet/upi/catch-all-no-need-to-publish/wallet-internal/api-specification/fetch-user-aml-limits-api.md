---
description: >-
  Api to Fetch user aml limits at issuer end for the given transaction type,
  this is the validation check to avoid transaction failure at later stage.
---

# Fetch user aml limits API

​

{% swagger method="post" path="" baseUrl="<domain>/wallet/internal/check/user/aml-limits/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" type="String" required="true" name="productType" %}
Product Type(wallet type ex: RW)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" type="Int" required="true" %}
txn Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" type="String" required="true" %}
txn Type 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" type="Int" required="true" %}
Wallet Id (wallet unique ref #)
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

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

| Response code | Response description |
| ------------- | -------------------- |
| ​100          | Card Not found       |
| ​             |                      |

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
  "productType": "string",
  "txnAmount": 0,
  "txnType": "string",
  "walletId": 1
}
```
{% endtab %}

{% tab title="Response" %}
200 -> Fetched limits successfully&#x20;

201 -> Created&#x20;

401 -> Unauthorized

403 -> Forbidden&#x20;

404 -> Not Found&#x20;

500 -> INTERNAL ERROR
{% endtab %}
{% endtabs %}
