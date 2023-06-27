---
description: The API can be invoked to fetch transaction details using transaction id.
---

# UPI transaction details API

resCode

{% swagger method="post" path="/upi-integration/upi/internal/vpaTxnDetails" baseUrl="" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="VPA-TXN-ID" required="true" %}

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

| Response Field | Field Description                  | Data Type | Length |
| -------------- | ---------------------------------- | --------- | ------ |
| resCode        |                                    | int       |        |
| resDesc        | SUCCESS, FAILURE status of the API | String    |        |
| data           |                                    | Object    |        |

<table><thead><tr><th>Response Field</th><th width="174">Filed Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>Object</td><td></td><td></td><td></td></tr><tr><td>id</td><td>unique id in the backend</td><td>Big Integer</td><td></td></tr><tr><td>merchantRequestId</td><td></td><td>String</td><td>varchar (50)</td></tr><tr><td>merchantCustomerId</td><td></td><td>String</td><td>varchar (20)</td></tr><tr><td>customerMobileNumber</td><td>customer mobile number</td><td>String</td><td>varchar (12)</td></tr><tr><td>payerVpa</td><td>payer VPA</td><td>String</td><td>varchar (35)</td></tr><tr><td>payeeMcc</td><td></td><td>String</td><td>varchar (25)</td></tr><tr><td>payeeMerchantCustomerId</td><td></td><td>String</td><td>varchar (20)</td></tr><tr><td>payeeName</td><td>payee name</td><td>String</td><td>varchar (25)</td></tr><tr><td>payeeVpa</td><td>payee vpa</td><td>String</td><td>varchar (100)</td></tr><tr><td>refUrl</td><td>refeence url for the request</td><td>String</td><td>varchar (50)</td></tr><tr><td>bankAccountUniqueId</td><td></td><td>String</td><td>varchar (100)</td></tr><tr><td>bankCode</td><td></td><td>String</td><td>varchar (20)</td></tr><tr><td>maskedAccountNumber</td><td>masked account number</td><td>String</td><td>varchar (20)</td></tr><tr><td>amount</td><td>transaction amount</td><td>double</td><td>Big Integer</td></tr><tr><td>transactionType</td><td>type of the transaction</td><td>String</td><td>varchar (20)</td></tr><tr><td>transactionTimestamp</td><td></td><td>Timestamp</td><td></td></tr><tr><td>originalTxnId</td><td>transaction id intiated in wibmo backend</td><td>String</td><td>varchar (50)</td></tr><tr><td>gatewayTxnId</td><td>transaction id intiated in the gateway</td><td>String</td><td>varchar (50)</td></tr><tr><td>gatewayResponseStatus</td><td>resposne status of the gateway</td><td>String</td><td>varchar (20)</td></tr><tr><td>gatewayReferenceId</td><td>response id of the gateway</td><td>String</td><td>varchar (20)</td></tr><tr><td>gatewayResponseCode</td><td>response code of the gateway</td><td>String</td><td>varchar (20)</td></tr><tr><td>gatewayResponseMessage</td><td>response message of the gateway</td><td>String</td><td>varchar (100)</td></tr><tr><td>upiRequestId</td><td></td><td>String</td><td>varchar (100)</td></tr><tr><td>status</td><td></td><td>String</td><td>varchar (100)</td></tr><tr><td>message</td><td></td><td>String</td><td>varchar (100)</td></tr><tr><td>updatedTs</td><td></td><td>Timestamp</td><td></td></tr><tr><td>createdTs</td><td></td><td>Timestamp</td><td></td></tr><tr><td>gatewayPayerResponseCode</td><td>gateway PayerResponse Code</td><td>String</td><td>varchar (50)</td></tr><tr><td>gatewayPayerResponseCode</td><td>gateway PayerResponse Code</td><td>String</td><td>varchar (50)</td></tr><tr><td>gatewayPayerReversalResponseCode</td><td>payer reversal response code of the gateway</td><td>String</td><td>varchar (50)</td></tr><tr><td>gatewayPayeeReversalResponseCode</td><td>payee reversal response code of the gateway</td><td>String</td><td>varchar (50)</td></tr></tbody></table>

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
  "resCode": "200",
  "resDesc": "SUCCESS",
  "data": {
    "gatewayTxnId": "123456789",
    "gatewayReferenceId": "123rf456",
    "customerMobileNumber": "99767XXXX",
    "payerVpa": "Test@VPA",
    "payeeMcc": "",
    "payeeMerchantCustomerId": "",
    "payeeName": "Test",
    "payeeVpa": "Test2@VPA",
    "refUrl": "",
    "bankAccountUniqueId": "",
    "bankCode": "1234",
    "originalTxnId": "20230404123456789",
    "amount": "200",
    "message": ""
  }
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/internal/vpaTxnDetails' \
\--header 'X-PROGRAM-ID: 2001'
\--header 'X-ACCOUNT-NUMBER: 5'
\--header 'VPA-TXN-ID: PUO625376537621'
\--header 'Content-Type: text/plain'
--data-raw '{

}'
```
{% endtab %}
{% endtabs %}
