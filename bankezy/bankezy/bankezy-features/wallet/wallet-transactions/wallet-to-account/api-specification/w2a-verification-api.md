---
description: Validate user is eligible for doing a wallet to account transaction
---

# W2A Verification API

This Api is used to identify the beneficiary cooling period, based on that beneficiary limits will be calculated. Source side transaction count and amount limit validation also will be calculated. Once amount limit validation has done, Fee and GST will be calculated.

{% swagger method="post" path="" baseUrl="<domain>/orchestrate /v1/validation" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiaryAccountNumber" type="String" required="true" %}
​
{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiaryId" type="Int" required="false" %}
Beneficiary Account Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiaryIfscCode" type="String" required="false" %}
Beneficiary IFSC Code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiaryName" type="String" required="false" %}
​Beneficiary Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sourceRefId" type="String" required="true" %}
Wallet Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmt" type="Int" required="true" %}
Transaction Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" type="String" required="true" %}
Transaction Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vpa" type="String" required="false" %}
VPA
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

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Custom response codes

| Code | Description                          |
| ---- | ------------------------------------ |
| 37   | amount is zero                       |
| ​52  | account number is empty              |
| 53   | ​account name is empty               |
| 54   | IFSC code is empty                   |
| ​65  | ​bank id is empty                    |
| 150  | Beneficiary Accounts addition failed |

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST 'http://localhost:8912/orchestrate/v1/validation' \
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain' \
--data-raw '{
    "sourceRefId":"114",
    "txnType":"W2A",
    "beneficiaryId": "115",
    "txnAmt":100 
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "sourceRefId":"114",
    "txnType":"W2A",
    "beneficiaryId": "115",
    "txnAmt":100 
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "beneficiaryId": 115,
        "feeAmount": 2,
        "gst": 0,
        "cgst": 0,
        "sgst": 0,
        "totalTxnAmount": 102,
        "message": "Additional fee is applicable for wallet to account transactions"
    }
}
```
{% endtab %}
{% endtabs %}
