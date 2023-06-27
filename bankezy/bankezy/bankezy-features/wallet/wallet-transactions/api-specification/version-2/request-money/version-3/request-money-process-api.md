---
description: >-
  Request Money Process API :  User Initiating the Request money from other
  BankEzy user
---

# Request Money Process API

{% swagger method="post" path="" baseUrl="<domain>wallet/rm/v3/initiate" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" type="String" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amt " type="String" required="true" %}
Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requesteeCustomerId" required="true" type="String" %}
​Requestee CustomerId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requesteeName" required="true" type="String" %}
Requestee Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requesterCustomerId" required="true" type="String" %}
​Requester CustomerId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnMode" required="true" type="String" %}
Transaction Mode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="upiReq" type="JSON" required="true" %}
​capability, deviceId, deviceName, deviceType, expiryTime, geoCode, ip, location, mobileNo, msgHash, os, payeeAccountId, payeeVirtualAddress, payerName, payerVirtualAddress, simId, token, transactionNote and txnAmount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="appName" required="true" type="String" %}
App name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="capability" required="true" type="String" %}
capability
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="true" type="String" %}
DeviceId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceName" required="true" type="String" %}
​Device Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceType" required="true" type="String" %}
Device Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="expiryTime" required="true" type="String" %}
Expiry Time
{% endswagger-parameter %}

{% swagger-parameter in="body" name="geoCode" required="true" type="String" %}
Geo Code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ip" required="true" type="String" %}
IP address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="location" required="true" type="String" %}
location
{% endswagger-parameter %}

{% swagger-parameter in="body" name="msgHash" required="true" type="String" %}
​msgHash
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobileNo" required="true" type="String" %}
​mobileNo
{% endswagger-parameter %}

{% swagger-parameter in="body" name="os" required="true" type="String" %}
Operating System
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeAccountId" required="true" type="String" %}
PayeeAccountId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeVirtualAddress" required="true" type="String" %}
​Payee Virtual Address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerName" required="true" type="String" %}
PayerName
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerVirtualAddress" required="true" type="String" %}
payerVirtualAddress
{% endswagger-parameter %}

{% swagger-parameter in="body" name="simId" required="true" type="String" %}
sim Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="token" required="true" type="String" %}
token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionNote" type="String" %}
​Transaction Note
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" required="true" type="String" %}
Transaction Amount
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" type="" required="true" %}
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

| Response code | Response description                         |
| ------------- | -------------------------------------------- |
| WAL100        | Failure                                      |
| WAL174        | User don't have wallet                       |
| WAL175        | Failed to insert to DB                       |
| WAL159        | Got response from UPI Service                |
| WAL160        | Account service not responded                |
| WAL157        | Request Money Txn Type/Txn Mode is not valid |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/v3/rm/initiate'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw '{ "amount": "100", "requesteeMobile": "8892239811", "requesteeName": "Abhinav", "requesterCustomerId": "29", "txnMode": "W2W" }'​
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}


```json
{
  "amount": "100",
  "requesteeMobile": "8892239811",
  "requesteeName": "Abhinav",
  "requesterCustomerId": "29",
  "txnMode": "W2W"
}
```
{% endtab %}

{% tab title="Response sample" %}


```json
{
  "resCode": "WAL173",
  "resDesc": "Request Money Success",
  "data": {
    "id": 0,
    "txnId": "202207251203528673sL4",
    "requsterCustomerId": "29",
    "requsteeCustomerId": "29",
    "amount": 100,
    "rmStatus": "P",
    "reqType": "W2W",
    "sourceType": "13",
    "destinationType": "13",
    "createdDt": 1658750632867,
    "remarks": null,
    "initiateFrom": "RM"
  }
}
```
{% endtab %}
{% endtabs %}

​
