---
description: This api can be used to request money from another VPA.
---

# Request Money via UPI API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/transaction/v1/requestMoney" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeVPA" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="payerVPA" %}
Vpa of the payer to which collect request is to be sent
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerName" required="false" %}
Name of the payer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeName" required="false" %}
Name of the payee
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" type="long" required="true" %}
Transaction amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="remarks" required="false" %}
Remarks sent by customer for the collect request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="currency" required="false" %}
INR
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="refUrl" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" %}
Optional
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

## Response Details

<table><thead><tr><th width="238">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>response code of the api</td><td>int</td><td></td></tr><tr><td>resDesc</td><td>SUCCESS, FAILURE status of the API</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>data</td><td>response object of the API</td><td>Object</td><td></td></tr></tbody></table>

| Response Field    | Field Description                   | Data Type | Length |
| ----------------- | ----------------------------------- | --------- | ------ |
| Object            |                                     | String    |        |
| txnDate           | date of the transaction             | String    |        |
| wibmoResCode      | response code of api                | int       |        |
| wibmoResDesc      | response description of the api     | String    |        |
| wibmoErrorMessage | error message of the api            | String    |        |
| txnRefNum         | transaction reference number        | String    |        |
| payeeName         | name of the payee                   | String    |        |
| txnDesc           | transaction description             | String    |        |
| txnAmount         | amount intiated for the transaction | String    |        |
| payeeMobileNumber | mobile number of the payee          | String    |        |
| payeeVPA          | payee vpa                           | String    |        |
| payerVPA          | payer vpa                           | String    |        |

## Response Status Code

| gatewayResponseCode | gatewayResponseStatus | Description                         |
| ------------------- | --------------------- | ----------------------------------- |
| 00                  | SUCCESS               | Collect sent successfully.          |
| 01                  | PENDING               | Transaction is in pending state.    |
| 96                  | DEEMED                | Response timeout (DEEMED APPROVED). |
| Else                | FAILURE               | Sending collect request failed.     |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
   "payeeVPA": "7022070219.citrus4@payu",
   "payerVPA": "7914717873@payu",
   "payerName" : "",
   "payeeName" : "",
    "txnAmount": 500.00,
    "walletId" : "354",
    "remarks": "testing",
    "currency" : "INR",
    "udfParameters" : ""

}
```
{% endtab %}

{% tab title="Sample Response" %}
```json

{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "txnDate": "",
        "wibmoResCode": 0,
        "wibmoResDesc": "SUCESS",
        "wibmoErrorMessage": null,
        "txnRefNum": "TEST REF NUMBER",
        "payeeName": "TEST",
        "txnDesc": "DESC",
        "txnAmount": "200",
        "payeeMobileNumber": null,
        "payeeVPA": null,
        "payerVPA": null
    }
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/transaction/v1/requestMoney' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
   "payeeVPA": "7022070219.citrus4@payu",
   "payerVPA": "7914717873@payu",
   "payerName" : "",
   "payeeName" : "",
    "txnAmount": 500.00,
    "walletId" : "354",
    "remarks": "testing",
    "currency" : "INR",
    "udfParameters" : ""

}'
```
{% endtab %}
{% endtabs %}
