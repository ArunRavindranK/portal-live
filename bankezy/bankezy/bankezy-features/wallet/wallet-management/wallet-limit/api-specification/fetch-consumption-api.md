---
description: To fetch the user consumption till date
---

# Fetch Consumption API

{% swagger method="post" path="" baseUrl="<domain>/wallet/limit/fetch/consumption/api/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="cardNumber" type="String" required="true" %}
​Card Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="kycLevel" type="Int" required="true" %}
User KYC Level
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productType" type="String" required="true" %}
​Wallet type(regular, food card, cash back card etc)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" type="String" required="true" %}
​Transaction Type(P2M, W2A, P2P Credit and P2P Debit)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
​The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="val" type="Int" required="true" %}
​Transaction amount
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" %}
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

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/limit/fetch/consumption/api/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw '{"cardNumber":"4329095732384124","kycLevel":150,"productType":"RW","txnType":"P2P","val":1}'JS
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "cardNumber": "4329095732384124",
  "kycLevel": 150,
  "productType": "RW",
  "txnType": "P2P",
  "val": 1
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "Success"
}
```
{% endtab %}
{% endtabs %}
