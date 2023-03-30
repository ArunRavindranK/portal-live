---
description: Auth leg status update for Auto subscription
---

# Auto Subscription Auth Status update API

{% swagger method="post" path="" baseUrl="<domain>/wallet/autoTopup/authStatus/update/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="X-API-TOKEN " type="String" required="true" %}
​The token got from the 

[login API](https://teams.microsoft.com/o/p6zvZh1r7XYNx0PmyEsS/s/CwdILEPBOX4lLKCKMZGB/~/changes/1N4jHPuBZcVMjqkduW8F/bankezy/bankezy/bankezy-features/wallet/wallet-issuance/customer-on-boarding/api-reference/authentication-and-authorization/login-api)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="authentication" type="String" required="true" %}
Authentication
{% endswagger-parameter %}

{% swagger-parameter in="header" name="chargeAttempted" type="Boolean" required="true" %}
​Charge Attempted
{% endswagger-parameter %}

{% swagger-parameter in="header" name="merchnatTxnId" type="String" required="true" %}
Merchant Txn Id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="thresholdAmt" type="String" required="true" %}
Threshold Amt 
{% endswagger-parameter %}

{% swagger-parameter in="header" name="topupAmt" type="String" required="true" %}
​Topup Amt
{% endswagger-parameter %}

{% swagger-parameter in="header" name="txnDate" type="String" required="true" %}
txn Date 
{% endswagger-parameter %}

{% swagger-parameter in="header" name="walletId" type="String" required="true" %}
Wallet Id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="wibmoTxnId" type="String" required="true" %}
Wibmo Txn Id
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

| Code | Description                                               |
| ---- | --------------------------------------------------------- |
| ​26  | ​Customer id is empty                                     |
| 66   | ​Charge attempted is empty                                |
| 67   | Wibmo txn id is empty                                     |
| 68   | Merchant txn id is empty                                  |
| 69   | Topup amount should not be less than or equal to zero     |
| 70   | Threshold amount should not be less than or equal to zero |
| 71   | ​Authentication is empty                                  |
| 72   | ​Txn date is empty                                        |
| ​73  | ​Topup amount should be grater than the threshold amount  |
| 100  | Txn Details not found.. Please try with valid details     |
| 150  | Authentication Failed or Authorization Failed             |



{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST '
https://payment1.pcdev.enstage-sas.com/wallet/autoTopup/authStatus/update/v1'

\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token'
--data-raw'{"authentication":true,"chargeAttempted":"true","merchnatTxnId":"202203110555565706yX15fU4","recurringPaymentRefId":0,"thresholdAmt":1,"topupAmt":2,"txnDate":"20220311","walletId":1,"wibmoTxnId":"202203110555565706yX15fU4"}
}'ONON
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "authentication": true,
  "chargeAttempted": "true",
  "merchnatTxnId": "202203110555565706yX15fU4",
  "recurringPaymentRefId": 0,
  "thresholdAmt": 1,
  "topupAmt": 2,
  "txnDate": "20220311",
  "walletId": 1,
  "wibmoTxnId": "202203110555565706yX15fU4"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "autotopup subscribed successfully"
}
```
{% endtab %}
{% endtabs %}
