---
description: >-
  Fetch the wallet card details based on card type or wallet Id(card number,
  expiry, balance, status..)
---

# Fetch Card API

{% swagger method="post" path="" baseUrl="<domain>/wallet/fetch/card/api/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" type="String" %}
​​The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productType" type="RW" required="true" %}
​Product Type(wallet type ex: RW)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" type="Int" required="true" %}
​Wallet Id (wallet unique ref #)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="false" %}
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

## Custom response codes

| Response code | Response description                 |
| ------------- | ------------------------------------ |
| ​1            | ​fetch card details successfully     |
| 2             | rrn is empty                         |
| 3             | internal server error                |
| 10            | card not found                       |
| 11            | prepaid card details not found       |
| 20            | request is empty                     |
| 36            | ​rrn is empty                        |
| ​39           | product type or customer id is empty |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/fetch/card/api/v1'
\--header 'Content-aType: text/plain'
\--header 'X-API-TOKEN:token'
\--header 'X-API-KEY:MOB-APP-2001'
\--data-raw '{ "productType": "RW", "walletId": 1 }'​
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "productType": "RW",
  "walletId": 1
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 1,
  "resDesc": "fetch card details successfully",
  "data": {
    "customerId": "1",
    "name": "name1",
    "walletId": 1,
    "mobile": "1111111111",
    "cardNumber": "4895110074527653",
    "cardExpiry": "012026",
    "balance": 38800,
    "walletStatus": "Active",
    "productType": "RW",
    "kycLevel": 30,
    "txnProfile": [
      {
        "status": true,
        "type": "e-Com"
      }
    ]
  }
}
```
{% endtab %}
{% endtabs %}
