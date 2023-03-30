---
description: >-
  The PSP calls this API exposed by CBS to initiate a credit operation on a
  virtual (PPI) account.
---

# Credit Money API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/callback/v1/creditMoneyCBS" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnId" required="true" %}
Trnsaction ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerVpa" required="true" %}
Vpa of the UPI user who received the collect request.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeVpa" required="true" %}
Vpa of the customer who sent the collect request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeName" required="true" %}
Name of the payer to whom collect request was sent.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerName" required="true" %}
Name of the payer to whom collect request was sent.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" required="true" %}
Transaction Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="currency" required="true" %}
INR
{% endswagger-parameter %}

{% swagger-parameter in="body" name="approvalStatus" required="true" %}
Transaction status approval
{% endswagger-parameter %}

{% swagger-parameter in="body" name="remarks" required="true" %}
Remarks sent by customer for the collect request.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnDate" required="true" %}
Transaction date
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

| Parameter Name       | Description                                                         |   |
| -------------------- | ------------------------------------------------------------------- | - |
| gatewayTransactionId | This is upi request id                                              |   |
| accountIdentifier    | unique account number of payee                                      |   |
| amount               | Amount which we need to credit to payee                             |   |
| gatewayReferenceId   | gatewayReferenceId which received from juspay as unique key         |   |
| type                 | <p>Possible values are <br>1. Transaction <br>2. Debit_reversal</p> |   |
|                      |                                                                     |   |
|                      |                                                                     |   |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
  "gatewayTransactionId" : "PUOd5f83e3cd66e484d90d2e6f",
  "accountIdentifier" : "69254133884",
  "amount" : "10.00",
  "gatewayReferenceId" : "236004274689",
  "remarks" : "Send Money ppi pre approved test1",
  "type" : "TRANSACTION"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/callback/v1/creditMoneyCBS?X-API-KEY=Juspay' \
--header 'Content-Type: application/json' \
--data-raw '{
  "gatewayTransactionId" : "PUOd5f83e3cd66e484d90d2e6f",
  "accountIdentifier" : "69254133884",
  "amount" : "10.00",
  "gatewayReferenceId" : "236004274689",
  "remarks" : "Send Money ppi pre approved test1",
  "type" : "TRANSACTION"
}'
```
{% endtab %}
{% endtabs %}

