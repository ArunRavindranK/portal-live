---
description: This api returns list of all the pending collect requests for the customer.
---

# List Pending Collect UPI Requests API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/transaction/v1/listPendingCollectRequests" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
program id
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

<table><thead><tr><th width="238">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td></td><td>int</td><td></td></tr><tr><td>resDesc</td><td>SUCCESS, FAILURE </td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>data</td><td>List of response Objects</td><td>Object</td><td></td></tr></tbody></table>

| Response Field    | Field Description                 | Data Type | Length |
| ----------------- | --------------------------------- | --------- | ------ |
| Object            |                                   |           |        |
| payeeMobileNumber | monible number of the payee       | String    |        |
| payeeVPA          | payee VPA                         | String    |        |
| payeeName         | name of the payee                 | String    |        |
| txnRefNumber      | transaction reference number      | String    |        |
| requestedDate     | requested date of the transaction | long      |        |
| expiryDate        | expiry date for the transaction   | long      |        |
| txnMode           | mode of the transaction           | String    |        |
| txnAmount         | transaction amount                | String    |        |
| desc              | description of the transaction    | String    |        |
| refUrl            | refUrl for the gateway            | String    |        |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
 
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": [
        {
            "txnDate": "04th Apr 2023",
            "wibmoResCode": 200,
            "wibmoResDesc": "SUCCESS",
            "wibmoErrorMessage": null,
            "txnRefNum": ""2435626,
            "payeeName": "Test",
            "txnDesc": "Test description",
            "txnAmount": "200",
            "payeeMobileNumber": ""9987XXXXX,
            "payeeVPA": "Test@VPA",
            "payerVPA": "Test2@VPA"
        }
    ]
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/transaction/v1/listPendingCollectRequests' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'x-program-id: 2001' 
\--header 'Content-Type: text/plain'
--data-raw '{
  
}'J
```
{% endtab %}
{% endtabs %}
