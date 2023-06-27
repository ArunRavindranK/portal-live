---
description: >-
  Split Bill: User can share the bill amount  with other BankEzy
  user(s)(one-many) , once the requestee approves amount will be transferred to
  Requester
---

# Split Bill API

{% swagger method="post" path="" baseUrl="<domain>/wallet/sb/v2/initiate" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" type="String" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" type="JSON" name="sbRequest " required="true" %}
sbRequest
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requesteeAccounts" type="JSON" required="true" %}
RappNameequestee Accounts
{% endswagger-parameter %}

{% swagger-parameter in="body" name="appName" type="String" required="true" %}
​app Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="capability" type="String" required="true" %}
capability
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" type="String" required="true" %}
deviceId 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceType" required="true" %}
device Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="expiryTime" type="String" required="true" %}
expiryTime
{% endswagger-parameter %}

{% swagger-parameter in="body" name="geoCode" type="String" required="true" %}
geoCode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ip" type="String" required="true" %}
IP
{% endswagger-parameter %}

{% swagger-parameter in="body" name="location" type="String" required="true" %}
Location
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobileNo" type="String" required="true" %}
Mobile No
{% endswagger-parameter %}

{% swagger-parameter in="body" name="msgHash" type="String" required="true" %}
msgHash
{% endswagger-parameter %}

{% swagger-parameter in="body" name="os" type="String" required="true" %}
OS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeAccountId" type="String" required="true" %}
Payee AccountId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeVirtualAddress" type="String" required="true" %}
Payee VirtualAddress
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerName" type="String" required="true" %}
​Payer Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerVirtualAddress" type="String" required="true" %}
Payer VirtualAddress
{% endswagger-parameter %}

{% swagger-parameter in="body" name="simId" type="String" required="true" %}
​Sim Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="token" type="String" required="true" %}
token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionNote" type="String" required="true" %}
Transaction Note
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" type="String" required="true" %}
Txn Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requesteeWallets" type="JSON" required="true" %}
​Requestee Wallets
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="Int" required="true" %}
​Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requesteeCustomerId" type="String" required="true" %}
Requestee CustomerId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requesteeMobile" type="String" required="true" %}
Requestee Mobile
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" type="Int" required="true" %}
​Wallet Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnMode" type="W2W" required="true" %}
Transaction Mode
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

| Response code | Response description                      |
| ------------- | ----------------------------------------- |
| WAL28         | Split bill Txn Type/Txn Mode is not valid |
| WAL29         | Mobile# or Customer Id is Mandatory       |
| WAL13         | Request is empty                          |
| WAL173        | Request Money Success                     |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/sb/v2/initiate'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw '{"requesteeWallets":[{"requesteeName":"Abhinav Aradhya","amount":1000,"requesteeMobile":"8892239811"}], "txnMode":"W2W"}'​
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "requesteeWallets": [
    {
      "requesteeName": "Abhinav Aradhya",
      "amount": 1000,
      "requesteeMobile": "8892239811"
    }
  ],
  "txnMode": "W2W"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": "WAL200",
  "resDesc": "SUCCESS",
  "data": {
    "reqDate": 1658218281507,
    "txnDetails": [
      {
        "resDesc": "Request Money Success",
        "resCode": 200,
        "amount": 1000,
        "txnId": "202207190811214759tI2",
        "requesteeMobile": "1420200001",
        "requesteeName": "User1"
      }
    ]
  }
}
```
{% endtab %}
{% endtabs %}

| Response code | Response description                       |
| ------------- | ------------------------------------------ |
| ​100          | ​Split bill Txn Type/Txn Mode is not valid |
| 120           | Mobile# or Customer Id is Mandatory        |
