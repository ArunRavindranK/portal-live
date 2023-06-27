---
description: >-
  Request Money Accept Initiate API: once Requestee takes an action either
  Accept/Reject, if user accepts fund movement will happen from Requestee to
  Requester
---

# Request Money Accept Initiate API

{% swagger method="post" path="" baseUrl="<domain>/wallet/rm/v3/accept/init" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="collectStatus" type="String" required="true" %}
​Collect Status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeDetails" type="String" required="true" %}
payeeDetails
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeId" type="String" required="true" %}
payeeId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="rmUpiAcceptRequest" type="JSON" required="true" %}
rmUpiAcceptRequest
{% endswagger-parameter %}

{% swagger-parameter in="body" name="appName" type="String" required="true" %}
appName
{% endswagger-parameter %}

{% swagger-parameter in="body" name="approvalStatus" type="String" required="true" %}
approvalStatus
{% endswagger-parameter %}

{% swagger-parameter in="body" name="capability" type="String" required="true" %}
​capability
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" type="String" required="true" %}
deviceId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceName" type="String" required="true" %}
deviceName
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceType" type="String" required="true" %}
​deviceType
{% endswagger-parameter %}

{% swagger-parameter in="body" name="geoCode" type="String" required="true" %}
geoCode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ip" type="String" required="true" %}
ip
{% endswagger-parameter %}

{% swagger-parameter in="body" name="location" type="String" required="true" %}
location
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobileNo" type="String" required="true" %}
​mobileNo
{% endswagger-parameter %}

{% swagger-parameter in="body" name="msgHash" type="String" required="true" %}
msgHash
{% endswagger-parameter %}

{% swagger-parameter in="body" name="npciTxnId" type="String" required="true" %}
​npciTxnId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="os" type="String" required="true" %}
os
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeName" required="true" %}
​payeeName
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeVPA" type="String" required="true" %}
​payeeVPA
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerAccountId" type="String" required="true" %}
​Payer AccountId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerVirtualAddress" type="String" required="true" %}
​Payer VirtualAddress
{% endswagger-parameter %}

{% swagger-parameter in="body" name="simId" type="String" required="true" %}
simI d
{% endswagger-parameter %}

{% swagger-parameter in="body" name="token" type="String" required="true" %}
token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" type="String" required="true" %}
Transaction Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnNote" type="String" required="true" %}
TxnAmount Note
{% endswagger-parameter %}

{% swagger-parameter in="body" name="upiTxnRefNo" type="String" required="true" %}
upi Txn RefNo
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmt" type="Int" required="true" %}
Transaction Amt
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnMode" type="String" required="true" %}
Transaction Mode
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

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Custom response code

| Response code | Response description                       |
| ------------- | ------------------------------------------ |
| WAL13         | Request is empty                           |
| WAL14         | INTERNAL ERROR                             |
| WAL169        | PayeeId is invalid/Payee details not found |
| WAL171        | Decline request has some issue             |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/rm/v3/accept/init'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw '{ "collectStatus": "A", "payeeDetails": "", "payeeId": "1180066", "txnAmt": 1, "txnMode": "W2W", "walletId": "1" }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}


```json
{
  "collectStatus": "A",
  "payeeDetails": "",
  "payeeId": "1180066",
  "txnAmt": 1,
  "txnMode": "W2W",
  "walletId": "1"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "collectStatus": "A",
  "payeeDetails": "",
  "payeeId": "1180066",
  "txnAmt": 1,
  "txnMode": "W2W",
  "walletId": "1"
}
```
{% endtab %}
{% endtabs %}
