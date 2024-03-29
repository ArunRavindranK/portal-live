---
description: Debit funds from wallet
---

# Debit Fund API

{% swagger method="post" path="" baseUrl="<domain>/wallet/v2/debit/api" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="Int" required="true" %}
amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiaryName" type="String" required="true" %}
beneficiary Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mcc" type="String" required="true" %}
mcc
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="String" required="true" %}
Merchant Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="originalRRN" type="String" required="true" %}
merchantId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="rrn" type="String" required="true" %}
​rrn
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" type="String" required="true" %}
txnType
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" type="Int" required="true" %}
walletId
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
{% endswagger %}

## Custom error codes

| Response code | Response description                                                                                                                                                       |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ​WAL61        | funds debited successfully                                                                                                                                                 |
| WAL165        | Invalid wallet Id Passed (or) impl id not found (or) debit funds is disabled for this cardimpl id not found (or) card not found (or) Failure (or) prepaid response is null |
| WAL130        | debit funds is disabled for this card                                                                                                                                      |
| WAL13         | request is empty                                                                                                                                                           |
| WAL01         | cu​stomer id is empty                                                                                                                                                      |
| ​WAL59        | rrn is empty                                                                                                                                                               |
| WAL56         | amount is zero                                                                                                                                                             |
| WAL57         | ​wallet id is zero                                                                                                                                                         |
| WAL60         | txn type is empty                                                                                                                                                          |
| WAL63         | Merchant Id is empty                                                                                                                                                       |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/debit/api/v1' \--header 'Content-Type: application/json'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw '{ "amount": 0, "beneficiaryName": "string", "mcc": "string", "merchantId": "string", "originalRRN": "string", "rrn": "string", "txnType": "Load Money", "walletId": 0 }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "amount": 0,
  "beneficiaryName": "string",
  "mcc": "string",
  "merchantId": "string",
  "originalRRN": "string",
  "rrn": "string",
  "txnType": "Load Money",
  "walletId": 0
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": "WAL61",
  "resDesc": "funds debited successfully",
  "data": {
    "custId": "1992",
    "walletId": 318,
    "refNumber": "5164940",
    "amount": 200,
    "availableBal": 79498,
    "remarks": "Card Recharge",
    "ppTxnId": "1962032"
  }
}
```
{% endtab %}
{% endtabs %}
