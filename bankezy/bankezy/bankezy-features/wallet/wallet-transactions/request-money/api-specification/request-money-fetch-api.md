---
description: >-
  Request Money Fetch API: it will fetch all pending requests for logged in user
  to take action either Accept/Reject
---

# Request Money Fetch API

{% swagger method="post" path="" baseUrl="<domain>/wallet/rm/fetch/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" type="String" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerId" type="String" required="true" %}
​Customer ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceName" type="String" required="true" %}
​Device Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobileNo" type="String" required="true" %}
Mobile Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="msgHash" type="String" required="true" %}
​Message Hash
{% endswagger-parameter %}

{% swagger-parameter in="body" name="token" type="String" required="true" %}
Token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="virtualAddress" type="String" required="true" %}
​Virtual Address
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="false" %}
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

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/rm/fetch/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw '{"customerId":"29","deviceName":"AndriodApp@samsungSM-G610F-airtel","mobileNo":"8892239811"}'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "customerId": "29",
  "deviceName": "AndriodApp@samsungSM-G610F-airtel",
  "mobileNo": "8892239811"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "Success",
  "data": {
    "walletServiceError": false,
    "walletListResponse": [
      {
        "txnMode": "W2W",
        "txnAmt": 100,
        "payeeDetails": "5555533333",
        "payeeId": "1180096",
        "txnDate": 1658215119000
      },
      {
        "txnMode": "W2W",
        "txnAmt": 1000,
        "payeeDetails": "1420200001",
        "payeeId": "1180097",
        "txnDate": 1658215121000
      },
      {
        "txnMode": "W2W",
        "txnAmt": 100,
        "payeeDetails": "5555533333",
        "payeeId": "1180098",
        "txnDate": 1658216745000
      }
    ],
    "upiServiceError": true,
    "collectListResponse": {
      "pspRefNo": null,
      "status": null,
      "statusDescription": null,
      "pendingList": null,
      "respCode": "000",
      "respDesc": "NA",
      "msgHash": "NA",
      "commonInfo": null
    }
  }
}json
```
{% endtab %}
{% endtabs %}

​
