---
description: Fetch user aml limits
---

# Fetch user aml limits

{% swagger method="post" path="" baseUrl="<domain>/wallet/internal/check/user/aml-limits/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" type="String" name="X-API-TOKEN " required="false" %}
​The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productType" required="true" type="String" %}
Product Type(wallet type ex: RW)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" required="true" type="String" %}
txn Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" required="true" type="String" %}
txn Type(ex: P2P,P2M)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" required="true" type="String" %}
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

{% swagger-response status="204: No Content" description="" %}
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
{% endswagger %}

| Response Code | Response Description |
| ------------- | -------------------- |
| 100           | Card Not found       |

{% tabs %}
{% tab title="Sample curl command" %}
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/internal/check/user/aml-limits/v1'

\\--header 'Content-Type: text/plain'

\\--header 'X-API-KEY: MOB-APP-2001'

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
200 --> Fetched limits successfully
{% endtab %}
{% endtabs %}
