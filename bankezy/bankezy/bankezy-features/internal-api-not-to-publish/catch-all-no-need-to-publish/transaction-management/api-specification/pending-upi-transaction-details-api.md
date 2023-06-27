---
description: The API can be invoked to fetch all peding state transaction details.
---

# Pending UPI transaction details API

resCode

{% swagger method="post" path="/upi-integration/upi/internal/pendingTxns" baseUrl="" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-LIMIT" type="String" required="true" %}
Offset fetch pending transactions based on pagination
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" type="String" %}
programId
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-LAST-PROCESSED-ID" required="false" %}
last processed from the last batch
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

<table><thead><tr><th width="257">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>Response code</td><td>int</td><td></td></tr><tr><td>resDesc</td><td>Response code description</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>data</td><td>This is list transaction details whech are in pending.</td><td>List&#x3C;Object></td><td></td></tr></tbody></table>

<table><thead><tr><th>Response Field</th><th width="205">Filed Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>Object</td><td></td><td></td><td></td></tr><tr><td>id</td><td></td><td>Big Integer</td><td></td></tr><tr><td>merchantRequestId</td><td></td><td>String</td><td>varchar (50)</td></tr><tr><td>merchantCustomerId</td><td></td><td>String</td><td>varchar (20)</td></tr><tr><td>customerMobileNumber</td><td>customer mobile number</td><td>String</td><td>varchar (12)</td></tr><tr><td>payerVpa</td><td>vpa of the payer</td><td>String</td><td>varchar (35)</td></tr><tr><td>payeeMcc</td><td></td><td>String</td><td>varchar (25)</td></tr><tr><td>payeeMerchantCustomerId</td><td></td><td>String</td><td>varchar (20)</td></tr><tr><td>payeeName</td><td>name of the payee</td><td>String</td><td>varchar (25)</td></tr><tr><td>payeeVpa</td><td>vpa of the payee</td><td>String</td><td>varchar (100)</td></tr><tr><td>refUrl</td><td>reference url of the request</td><td>String</td><td>varchar (50)</td></tr><tr><td>bankAccountUniqueId</td><td></td><td>String</td><td>varchar (100)</td></tr><tr><td>bankCode</td><td></td><td>String</td><td>varchar (20)</td></tr><tr><td>maskedAccountNumber</td><td>masked account number</td><td>String</td><td>varchar (20)</td></tr><tr><td>amount</td><td>transaction amount</td><td>double</td><td>Big Integer</td></tr><tr><td>transactionType</td><td>type of the transaction</td><td>String</td><td>varchar (20)</td></tr><tr><td>transactionTimestamp</td><td></td><td>Timestamp</td><td></td></tr><tr><td>originalTxnId</td><td>transaction whis is intiated in the wibmo backend</td><td>String</td><td>varchar (50)</td></tr><tr><td>gatewayTxnId</td><td>transaction id which is intiated in the gateway</td><td>String</td><td>varchar (50)</td></tr><tr><td>gatewayResponseStatus</td><td>response status of the gateway</td><td>String</td><td>varchar (20)</td></tr><tr><td>gatewayReferenceId</td><td>reference id of the gateway</td><td>String</td><td>varchar (20)</td></tr><tr><td>gatewayResponseCode</td><td>resposne code of the gateway</td><td>String</td><td>varchar (20)</td></tr><tr><td>gatewayResponseMessage</td><td>response message of the gateway</td><td>String</td><td>varchar (100)</td></tr><tr><td>upiRequestId</td><td></td><td>String</td><td>varchar (100)</td></tr><tr><td>status</td><td></td><td>String</td><td>varchar (100)</td></tr><tr><td>message</td><td></td><td>String</td><td>varchar (100)</td></tr><tr><td>updatedTs</td><td></td><td>Timestamp</td><td></td></tr><tr><td>createdTs</td><td></td><td>Timestamp</td><td></td></tr><tr><td>gatewayPayerResponseCode</td><td>payer response code of the gateway</td><td>String</td><td>varchar (50)</td></tr><tr><td>gatewayPayeeResponseCode</td><td>payee response code of the gateway</td><td>String</td><td>varchar (50)</td></tr><tr><td>gatewayPayerReversalResponseCode</td><td>payer reversal response code in gateway</td><td>String</td><td>varchar (50)</td></tr><tr><td>gatewayPayeeReversalResponseCode</td><td>payee reversal response code in gateway</td><td>String</td><td>varchar (50)</td></tr></tbody></table>

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
            "id": 123,
            "merchantRequestId": "4567893",
            "merchantCustomerId": null,
            "customerMobileNumber": "9967548934",
            "payerVpa": "Test@VPA",
            "payeeMcc": null,
            "payeeMerchantCustomerId": null,
            "payeeName": "Test",
            "payeeVpa": "Test2@VPA",
            "refUrl": null,
            "bankAccountUniqueId": null,
            "bankCode": "1234",
            "maskedAccountNumber": null,
            "amount": 123.0,
            "transactionType": "W2UPI",
            "transactionTimestamp": null,
            "originalTxnId": "202304045678945678",
            "gatewayTxnId": "PUI123456789",
            "gatewayResponseStatus": "00",
            "gatewayReferenceId": null,
            "gatewayResponseCode": null,
            "gatewayResponseMessage": null,
            "upiRequestId": null,
            "status": null,
            "message": null,
            "updatedTs": null,
            "createdTs": null,
            "gatewayPayerResponseCode": null,
            "gatewayPayeeResponseCode": null,
            "gatewayPayerReversalResponseCode": null,
            "gatewayPayeeReversalResponseCode": null
        }
    ]
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/internal/pendingTxns' \
\--header 'X-PROGRAM-ID: 2001'
\--header 'X-LIMIT: 5'
\--header 'X-LAST-PROCESSED-ID: 10'
\--header 'Content-Type: text/plain'
--data-raw '{

}'
```
{% endtab %}
{% endtabs %}
