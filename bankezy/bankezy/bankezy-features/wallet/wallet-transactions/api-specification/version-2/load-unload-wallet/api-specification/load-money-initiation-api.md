---
description: Adding Funds into users wallet
---

# Load Money Initiation API



{% swagger method="post" path="" baseUrl="<domain>/orchestrate/lm/init/api/v2" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="amount" type="String" required="true" %}
Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productType" type="String" required="true" %}
Product Type(wallet type ex: RW)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
MOB-APP-2001
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

## Custom error codes

| Response Code | Response Description                                       |
| ------------- | ---------------------------------------------------------- |
| ORC006        | ​request is empty                                          |
| ORC002        | Customer Id is Mandatory                                   |
| ORC011        | Amt should be greater than Zero                            |
| ​ORC021       | ​Card is blocked for online transactions                   |
| ORC020        | Load Money Initiation failed.. Please try after some time. |

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location 'http://localhost:7060/orchestrate/lm/init/api/v2' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: replace-proper-token' \
--header 'Content-Type: application/json' \
--data '{
  "amount": 100,
  "customerId": "29",
  "kycLevel": 30,
  "productType": "RW"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "amount": 100,
  "customerId": "29",
  "kycLevel": 30,
  "productType": "RW"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": "ORC200",
  "resDesc": "Success",
  "data": {
    "merchantId": "171756421435003980",
    "merchantName": "Bankezy Wallet Card",
    "merchantTxnId": "202207251403294290xN66vO7"
  }
}
```
{% endtab %}
{% endtabs %}
