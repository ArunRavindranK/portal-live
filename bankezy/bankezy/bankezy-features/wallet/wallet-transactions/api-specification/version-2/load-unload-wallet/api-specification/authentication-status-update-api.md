---
description: >-
  For Load money flow updating the Auth status, if auth status is success,
  Authorization leg invokes
---

# Authentication Status Update API



{% swagger method="post" path="" baseUrl="<domain>/orchestrate/lm/authupdate/api/v2" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="amount" required="true" type="String" %}
Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="authentication" required="true" type="String" %}
Authentication
{% endswagger-parameter %}

{% swagger-parameter in="body" name="chargeAttempted" required="true" type="String" %}
Charge Attempted
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchnatTxnId" required="true" type="String" %}
​Merchant transaction id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnDate" required="true" type="String" %}
Transaction Date
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" required="true" type="String" %}
Wallet  Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wibmoTxnId" required="true" type="String" %}
Wibmo transaction id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" type="String" %}
​The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
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

{% swagger-response status="204: No Content" description="" %}
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

## Custom error codes

| Response Code | Response Description                                          |
| ------------- | ------------------------------------------------------------- |
| ORC006        | ​request is empty                                             |
| ORC007        | ​Charge Attempt is Mandatory                                  |
| ORC008        | Merchant Id is Mandatory                                      |
| ORC009        | Transaction Date is Mandatory                                 |
| ORC010        | Wibmo transaction id is Mandatory                             |
| ORC011        | ​Amt should be greater than Zero                              |
| ​ORC012       | ​Wallet Id should be greater than Zero                        |
| ​ORC013       | Authentication status is mandatory                            |
| ​ORC014       | Transaction Details not found.. Please try with valid details |
| ORC015        | Authorization Failed                                          |
| ​ORC016       | Payment service not responding.. please try after some time   |
| ORC017        | Credit To Wallet Failed                                       |
| ORC018        | Wallet Service not responded.. Credit to wallet failed        |



{% tabs %}
{% tab title="Sample curl command" %}
```json
​curl --location --request POST '
https://payment1.pcdev.enstage-sas.com/orchestrate/lm/authupdate/api/v2'

\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token'
--data-raw'{
  "amount": 100,
  "authentication": true,
  "chargeAttempted": "false",
  "merchnatTxnId": "202208010642001447oT97zO8",
  "txnDate": "20220801",
  "walletId": 13,
  "wibmoTxnId": "2022080110010010017"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "amount": 100,
  "authentication": true,
  "chargeAttempted": "false",
  "merchnatTxnId": "202208010642001447oT97zO8",
  "txnDate": "20220801",
  "walletId": "13",
  "wibmoTxnId": "2022080110010010017"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "ORC200",
    "resDesc": "Success",
    "data": {
        "customerId": "73",
        "merchnatTxnId": "202304060757289915qA03dC0",
        "wibmoTxnId": "2023040620010010061",
        "amount": "1000",
        "availableBal": "119915",
        "walletid": "58"
    }
}
```
{% endtab %}
{% endtabs %}
