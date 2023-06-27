---
description: The API can be invoked to check transaction status.
---

# Transaction UPI Status API

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

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
Program ID
{% endswagger-parameter %}

{% swagger-parameter in="body" required="false" name="id" type="long" %}
Currency code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantRequestId" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantCustomerId" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerMobileNumber" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerVpa" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeMcc" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeMerchantCustomerId" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeName" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeVpa" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="refUrl" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankAccountUniqueId" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankCode" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="maskedAccountNumber" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionType" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionTimestamp" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="originalTxnId" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="gatewayTxnId" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="gatewayResponseStatus" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="gatewayReferenceId" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="gatewayResponseCode" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="gatewayResponseMessage" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="upiRequestId" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="message" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="updatedTs" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="createdTs" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="gatewayPayerResponseCode" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="gatewayPayeeResponseCode" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="gatewayPayerReversalResponseCode" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="gatewayPayeeReversalResponseCode" %}

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

<table><thead><tr><th width="257">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>Response code</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>resDesc</td><td>Response code description</td><td>String</td><td>Variable, 5–8 characters</td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Request" %}
```json
{"id": "",
  "txnInfo": {
    "gatewayTxnId": "PUI20230404123456"
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
{"id": "",
  "txnInfo": {
    "gatewayTxnId": "PUI20230404123456"
  }
  }

}'
```
{% endtab %}
{% endtabs %}
