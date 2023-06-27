---
description: This API is used to get the list of blocked mobile number
---

# Block Collect Request API

{% swagger method="post" path="" baseUrl="<domain>/wallet/rm/v3/accept/init" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
Program ID 
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" required="true" %}
Account Number 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnMode" required="true" %}
type of transaction ex: W2W
{% endswagger-parameter %}

{% swagger-parameter in="body" name="collectStatus" required="true" %}
collect request status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnRefNumber" required="true" %}
transaction reference number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeMobileNumber" required="true" %}
mobile number of payee
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" required="true" %}
wallet if
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" required="true" %}
transaction amount
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

## Custom response codes

| Response Code | Response Description                       |
| ------------- | ------------------------------------------ |
| WAL168        | Txn Mode is not valid                      |
| WAL169        | PayeeId is invalid/Payee details not found |
| WAL170        | Send Money failed or Null response         |
| WAL171        | Decline request has some issue             |
| WAL159        | Got response from UPI Service              |
| WAL200        | SUCCESS                                    |

### Response Details

<table><thead><tr><th width="279">Response Desc</th><th>Field desc</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>rescode</td><td>response Code of the API</td><td>String</td><td></td></tr><tr><td>resdesc</td><td>response Description of the API</td><td>String</td><td>Variable</td></tr><tr><td>txnDate</td><td>Date of Txn</td><td>long</td><td></td></tr><tr><td>approvalStatus</td><td>Status(ACCEPT,BLOCK,DECLINE)</td><td>String</td><td></td></tr><tr><td>txnId</td><td>Transaction ID</td><td>String</td><td></td></tr><tr><td>txnAmount</td><td>Transaction Amount</td><td>String</td><td></td></tr><tr><td>remarks</td><td></td><td>String</td><td></td></tr><tr><td>payeeMobileNumber</td><td>Payee Mobile Number</td><td>String</td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample  Curl Command" %}
```json
curl --location --request POST 'http://192.168.105.70:9000/wallet/rm/v3/accept/init' \
--header 'X-PROGRAM-ID: 1111' \
--header 'X-ACCOUNT-NUMBER: 404' \
--header 'Accept-Language: en' \
--header 'Content-Type: application/json' \
--data-raw '{
    "txnMode": "W2W",
    "collectStatus": "BLOCK",
    "txnRefNumber": "1315",
    "payeeMobileNumber": "9042179396",
    "walletId": "0",
    "txnAmount": "1400"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "txnMode": "W2W",
    "collectStatus": "BLOCK",
    "txnRefNumber": "1315",
    "payeeMobileNumber": "9042179396",
    "walletId": "0",
    "txnAmount": "1400"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode":"WAL200",
    "resDesc":"SUCCESS",
    "data":{    
        "txnDate":"20230529",
        "txnAmount": "100",
        "txnId":"",
        "remarks":"W2A",
        "approvalStatus":"BLOCK",
        "payeeMobileNumber":"12344567890"
    }
}
```
{% endtab %}
{% endtabs %}
