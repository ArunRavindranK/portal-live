---
description: The API can be invoked to check transaction status.
---

# Transaction Status API

resCode

{% swagger method="put" path="/upi-integration/upi/internal/v1/transaction/status" baseUrl="" summary="" %}
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

| Response Field | Field Description         | Data Type | Length                   |
| -------------- | ------------------------- | --------- | ------------------------ |
| resCode        | Response code             | String    | Variable, 5–8 characters |
| resDesc        | Response code description | String    | Variable, 5–8 characters |

{% tabs %}
{% tab title="Sample Request" %}
```json
{"id": "",
  "txnInfo": {
    "gatewayTxnId": ""
  }
  }
```
{% endtab %}

{% tab title="Sample Response" %}
```json
  {
  "resCode": "200",
  "resDesc": "SUCCESS"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/internal/v1/transaction/status' \
\--header 'X-PROGRAM-ID: 2001'
\--header 'X-ACCOUNT-NUMBER: 5'
\--header 'TXN-ID: PUO625376537621'
\--header 'Content-Type: text/plain'
--data-raw '{

}'
```
{% endtab %}
{% endtabs %}
