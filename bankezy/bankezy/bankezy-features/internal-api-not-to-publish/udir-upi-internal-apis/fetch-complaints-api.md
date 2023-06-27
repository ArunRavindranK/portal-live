---
description: The API can be invoked to fetch list of complaint
---

# Fetch Complaints API

resCode

{% swagger method="post" path="/upi-integration/upi/dispute-management/v1/complaints" baseUrl="" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceFingerPrint" required="true" %}
Device fingerprint of the customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerVpa" required="true" %}
VPA of the customer to be used for payment
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeName" required="true" %}
Name of the payee
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" type="Long" name="amount" %}
Amount for transaction
{% endswagger-parameter %}

{% swagger-parameter in="body" name="upiRequestId" required="true" %}
Unique id sent to UPI switch for the request
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="bankAccountUniqueId" %}
Unique id for the selected bank account
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="remarks" type="" %}
Any transaction summary
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="currency" %}
Currency code
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

<table><thead><tr><th width="257">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>Response code</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>resDesc</td><td>Response code description</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>errorMessage</td><td>Error Message</td><td>String</td><td>Length: 36 characters</td></tr><tr><td>data</td><td>This is list complaint details.</td><td>JSON Array </td><td>Sample data :: [{ "complaintRefNo": "", "complaintStatus": "", "amount": "", "status": "", "name": "", "createdTime": "", "txnId": "", "transDesc": "", "adjFlag": "", "adjCode": "" }]</td></tr><tr><td>complaintRefNo</td><td>It is complaint reference number</td><td>String</td><td></td></tr><tr><td>complaintStatus</td><td>Status of complaint</td><td>String</td><td>Raised/Resolved</td></tr><tr><td>amount</td><td>Transaction amount</td><td>String</td><td>Amount in decimal value</td></tr><tr><td>status</td><td>Status of the transaction</td><td>String</td><td></td></tr><tr><td>name</td><td>Payee name</td><td>String</td><td></td></tr><tr><td>createdTime</td><td>Transaction time</td><td>String</td><td></td></tr><tr><td>txnId</td><td>Transaction Id</td><td></td><td></td></tr><tr><td>transDesc</td><td>Transaction description</td><td>String</td><td></td></tr><tr><td>adjFlag</td><td>AdjFlag value value raising complaint</td><td>String</td><td></td></tr><tr><td>adjCode</td><td>AdjCode value while raising complaint</td><td>String</td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Request" %}
```json
{
  "type": null,
  "fromDate": null,
  "toDate": null,
  "status": null,
  "offset": null,
  "limit": null
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
  {
  "resCode": "200",
  "resDesc": "SUCCESS",
  "errorMessage": "null",
  "data": [{
      "complaintRefNo": "",
      "complaintStatus": "",
      "amount": "",
      "status": "",
      "name": "",
      "createdTime": "",
      "txnId": "",
      "transDesc": "",
      "adjFlag": "",
      "adjCode": ""
    }]
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/dispute-management/v1/complaints' \
\--header 'X-PROGRAM-ID: 2001'
\--header 'X-ACCOUNT-NUMBER: 5'
\--header 'Content-Type: text/plain'
--data-raw '{
  "type": null,
  "fromDate": null,
  "toDate": null,
  "status": null,
  "offset": null,
  "limit": null
}'
```
{% endtab %}
{% endtabs %}
