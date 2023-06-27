# Request Money Accept/Decline API

{% swagger method="post" path="" baseUrl="http://bankezy-azure.pcdev.enstage-sas.com/upi-integration/collectrequest/v1/incoming" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnId" required="true" %}
transaction id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerVpa" required="true" %}
payer Vpa
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeVpa" required="true" %}
payee Vpa
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeName" required="true" %}
payee Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerName" required="true" %}
payer name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" required="true" %}
transaction amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="currency" %}
currency
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transacType" required="true" %}
transacion Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="approvalStatus" required="true" %}
user action example: ACCEPT, BLOCK, DECLINE
{% endswagger-parameter %}

{% swagger-parameter in="body" name="remarks" required="false" %}
remarks
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" required="true" %}
wallet id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnDate" required="true" %}
merchant category code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" required="false" %}
user definded field
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

| Response code | Response description                               |
| ------------- | -------------------------------------------------- |
| 411           | Payee VPA is invalid                               |
| 412           | Payer VPA is invalid                               |
| 200           | SUCCESS                                            |
| 202           | PENDING                                            |
| 100           | Sorry something went wrong. Please try again later |
| 300           | FAILURE                                            |

{% tabs %}
{% tab title="Sample CURL Request" %}
```json
curl --location 'http://localhost:7060/upi-integration/collectrequest/v1/incoming' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: replace-proper-token' \
--header 'Content-Type: application/json' \
--data-raw '{
    "txnId": "123123",
    "payerVpa": "test@123",
    "payeeVpa": "test@abc",
    "payeeName": "test123",
    "payerName": "test",
    "txnAmount": "100",
    "currency": "",
    "approvalStatus": "ACCEPT",
    "remarks": "",
    "walletId": "22",
    "txnDate": "",
    "udfParameters": {}
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
    "txnId": "123123",
    "payerVpa": "test@123",
    "payeeVpa": "test@abc",
    "payeeName": "test123",
    "payerName": "test",
    "txnAmount": "100",
    "currency": "",
    "approvalStatus": "ACCEPT",
    "remarks": "",
    "walletId": "22",
    "txnDate": "",
    "udfParameters": {}
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
  "respCode": "UPI200",
  "respDesc": "SUCCESS",
  "data": {
    "txnId": "123123",
    "payerVpa": "test@123",
    "payeeVpa": "test@abc",
    "payeeName": "test123",
    "txnMode":"REQUEST_MONEY_ACCEPT",
    "txnAmount": "100",
    "approvalStatus": "ACCEPT",
    "txnDesc":"Request money acceot",
    "wibmoRespCode":200,
    "wibmoResDesc":"Success",
    "walletId": "22",
    "txnDate": "20230530",
    "refUrl":"https://www.abcxyz.com/"
    "trackingTxnStatus": [
      {
        "id":7687697,
        "txnNumber":"345632DSVDSF"
        "txnStatusName":"success",
        "txnStatusDescription":"",
        "createAt":""
      }
    ]
  }
}
```
{% endtab %}
{% endtabs %}
