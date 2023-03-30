---
description: Initiating wallet to account transaction once verification successful
---

# W2A Transaction API

This API is used to initiate a wallet to account transaction.

{% swagger method="post" path="" baseUrl="<domain>/orchestrate/v1/transfer" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="finalAmount" type="Int" required="true" %}
Final Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mcc" type="String" required="true" %}
MCC
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="String" required="true" %}
Merchant Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="rrn" type="String" required="true" %}
RRN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" type="Int" required="true" %}
Transaction Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" type="String" required="true" %}
Transaction Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" type="Int" required="true" %}
Wallet Id
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
{% endswagger %}

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST 'http://localhost:8912/orchestrate/v1/transfer'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
--data-raw '{
    "txnType": "W2A",
    "txnAmt": 102,
    "sourceRefId": "114",
    "beneficiaryId": "115"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "txnType": "W2A",
    "txnAmt": 102,
    "sourceRefId": "114",
    "beneficiaryId": "115"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode":200,
    "resDesc":"Transaction initiated successfully",
    "data": {
        "txnId":"202208011105327855bP02aI5",
        "amount":102,
        "txnDate":20221922,
        "payoutTxnId":"PAY208011105327855bP02aI5"
    }
}
```
{% endtab %}
{% endtabs %}
