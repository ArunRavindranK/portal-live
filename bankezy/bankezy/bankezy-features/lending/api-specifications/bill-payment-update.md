---
description: API to update bill payment
---

# Bill Payment Update

{% swagger method="post" path="" baseUrl="/lending/v1/bill/pay/update" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" type="String" required="true" name="X-API-TOKEN" %}
The token got from the 

[Get Token API](../../market-place/api-specification/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" type="String" required="true" name="X-ACCOUNT-NUMBER" %}
1812
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantTxnId" type="String" required="true" %}
Merchant Txn ID got from 

[Bill Payment Init API](bill-payment-init.md)

.
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
{% tab title="Sample Curl Request" %}
```
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/bill/pay/update' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: <REPLACE_WITH_TOKEN_FROM_GET_TOKEN_API_RESPONSE>' \
--header 'X-ACCOUNT-NUMBER: 1812' \
--data-raw '{
  "merchantTxnId": "<REPLACE_WITH_MERCHANT_TXN_ID_FROM_BILL_PAYMENT_INIT_API_RESPONSE>"
}'
```
{% endtab %}

{% tab title="Request Example" %}
```json
{
    "merchantTxnId":"202212070919383575lM71bY4"
}
```
{% endtab %}

{% tab title="Response Example" %}
```
{
    "resCode": "LND_200",
    "resDesc": "SUCCESS",
    "data": {
        "merchantTxnId": "202212070919383575lM71bY4",
        "amount": "500"
    }
}
```
{% endtab %}
{% endtabs %}
