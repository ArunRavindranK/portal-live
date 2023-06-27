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

<table><thead><tr><th width="279">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>​1</td><td>​fetch card details successfully</td></tr><tr><td>2</td><td>rrn is empty</td></tr><tr><td>3</td><td>internal server error</td></tr><tr><td>10</td><td>card not found</td></tr><tr><td>11</td><td>prepaid card details not found</td></tr><tr><td>20</td><td>request is empty</td></tr><tr><td>36</td><td>​rrn is empty</td></tr><tr><td>​39</td><td>product type or customer id is empty</td></tr></tbody></table>

## Response Details

| Response field    | Field description               | Data type |
| ----------------- | ------------------------------- | --------- |
| customerId        | user id                         | String    |
| walletId          | wallet id                       | Integer   |
| balance           | wallet balane                   | Integer   |
| kycLevel          | level of KYC                    | Integer   |
| productType       | wallet type                     | String    |
| mobile            | customer mobile number          | String    |
| name              | name of the customer            | String    |
| cardNumber        | wallet card number              | String    |
| cardExpiry        | wallet card expiry              | String    |
| walletStatus      | wallet status Active/ InActive  | String    |
| txnProfile.status | transaction profile type status | Boolean   |
| txnProfile.type   | transaction profile type        | String    |

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
