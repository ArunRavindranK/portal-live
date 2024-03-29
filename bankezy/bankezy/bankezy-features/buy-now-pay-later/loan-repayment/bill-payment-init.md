---
description: >-
  This API is used to initiate bill payment for billed or unbilled transactions.
  User is provided with merchantTxnId using which Payment MS to be called for
  init transaction and inturn get redirect link
---

# Bill Payment Init

{% swagger method="post" path="" baseUrl="/lending/v1/bill/pay/init" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-TOKEN" type="String" %}
The token got from the 

[Get Token API](../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="billId" type="Int" required="true" %}
Bill ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="Int" required="false" %}
Bill Amount
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
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/bill/pay/init' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: <REPLACE_WITH_TOKEN_FROM_GET_TOKEN_API_RESPONSE>' \
--header 'X-ACCOUNT-NUMBER: 1812' \
--data-raw '{
  "billId": 4545,
  "amount": 485
}'
```
{% endtab %}

{% tab title="Request Example" %}
```json
{
    "billId":4545,
    "amount":485
}
```
{% endtab %}

{% tab title="Response Example" %}
```json
{
    "resCode": "LND_200",
    "resDesc": "SUCCESS",
    "data": {
        "merchantTxnId": "202212070919383575lM71bY4",
        "merchantName": "Test Merchant 01",
        "merchantId": "171756421435003981",
        "txnAmt": "485.0",
        "txnDesc": "BNPL"
    }
}
```
{% endtab %}
{% endtabs %}

### Response Details

| Response Body | Data Type | Field Description       |
| ------------- | --------- | ----------------------- |
| resCode       | String    | Response Code           |
| resDesc       | String    | Response Description    |
| merchantTxnId | String    | merchant Transaction Id |
| merchantName  | String    | Merchant name           |
| merchantId    | String    | Merchant Id             |
| amount        | Long      | Amount                  |
| txnDesc       | String    | Transaction Description |

### Custom Response code

| Response Code | Response Description                                  |
| ------------- | ----------------------------------------------------- |
| LND027        | NO LIMIT                                              |
| LND200        | SUCCESS                                               |
| LND009        | There seems to be a technical issue. Try again later. |

