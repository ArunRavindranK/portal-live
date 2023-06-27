---
description: >-
  Fetch the wallet card details associated to user (card number, expiry,
  balance, status..), if user holds multiple card will return all or selected
  product type based on request
---

# Fetch Wallet Cards API

{% swagger method="post" path="" baseUrl="<domain>/wallet/fetch/cards/api/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="X-API-TOKEN  " type="String" required="true" %}
​The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="Int" required="true" %}
​Id (wallet Id)
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
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/fetch/cards/api/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-TOKEN:token'
\--header 'X-API-KEY:MOB-APP-2001'
\--data-raw '{ "id": 0 }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "id": 1
}
```

| <p><br></p> |
| ----------- |
{% endtab %}

{% tab title="Response sample" %}


```json
{
  "resCode": 200,
  "resDesc": "User Wallet cards fetched Successfully",
  "data": [
    {
      "customerId": "29",
      "name": "Naveen MN LN",
      "walletId": 13,
      "mobile": "8884373332",
      "cardNumber": "4895110034672441",
      "cardExpiry": "022026",
      "balance": 964416,
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
  ]
}son
```
{% endtab %}
{% endtabs %}
