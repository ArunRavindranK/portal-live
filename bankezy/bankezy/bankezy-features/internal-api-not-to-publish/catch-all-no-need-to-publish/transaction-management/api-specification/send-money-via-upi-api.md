---
description: >-
  The API can be invoked to process different types of payments. The
  transactionType key of request is used to identify the type of payment.
  Possible values are P2M_PAY, P2P_PAY, INTENT_PAY and SCAN_PAY
---

# Send Money via UPI API



{% swagger method="post" path="/upi-integration/upi/transaction/v1/sendMoney" baseUrl="" summary="The API can be invoked to process different types of payment" %}
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

| Response Fields | Fields Description              | Data Type | Length |
| --------------- | ------------------------------- | --------- | ------ |
| resCode         | response code of the api        | int       |        |
| resDesc         | response description of the api | String    |        |
| data            | response object of the api      | Object    |        |

<table><thead><tr><th width="257">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>Object</td><td></td><td></td><td></td></tr><tr><td>status</td><td>SUCCESS, FAILURE status of the API</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>responseCode</td><td></td><td>String</td><td></td></tr><tr><td>responseMessage</td><td></td><td>String</td><td></td></tr><tr><td>customGatewayStatusCode</td><td></td><td>String</td><td></td></tr><tr><td>trackingTxnStatus</td><td></td><td>String</td><td></td></tr><tr><td>wibmoRespCode</td><td></td><td>int</td><td></td></tr><tr><td>wibmoResDesc</td><td></td><td>String</td><td></td></tr><tr><td>wibmoErrorMessage</td><td></td><td>String</td><td></td></tr><tr><td>merchantId</td><td>Unique id for the merchant as passed in request headers</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>merchantChannelId</td><td>Unique id for the merchant channel as passed in request headers</td><td>String</td><td>Length: 36 characters</td></tr><tr><td>merchantRequestId</td><td>Merchant generated id for the transaction</td><td>String </td><td>Length: 36 characters</td></tr><tr><td>merchantCustomerId</td><td>Merchant generated unique profile id for customer as passed in the request</td><td>String</td><td>Length: 36 characters</td></tr><tr><td>customerMobileNumber</td><td>Customer mobile number</td><td>String</td><td>12 digits mobile number</td></tr><tr><td>payerVpa</td><td>Customer vpa used for the payment</td><td>String</td><td>Length: 36 characters</td></tr><tr><td>payeeMcc</td><td>MCC for the payee</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>payeeMerchantCustomerId</td><td>Merchant generated unique id for customer who received the payment. Only if it is an onus P2P transaction.</td><td>String</td><td>Length: 36 characters</td></tr><tr><td>payeeVpa</td><td>Vpa of the upi user who received the payment</td><td>String</td><td>Length: 36 characters</td></tr><tr><td>payeeName</td><td></td><td>String</td><td></td></tr><tr><td>refUrl</td><td>Reference url for the intent transaction</td><td>String</td><td>Length: 36 characters</td></tr><tr><td>bankAccountUniqueId</td><td>Unique id for the selected bank account</td><td>As passed in the request</td><td>Length: 36 characters</td></tr><tr><td>bankCode</td><td>Bank code of the account which was used</td><td>Valid bank IIN</td><td>Length: 36 characters</td></tr><tr><td>maskedAccountNumber</td><td>Masked account number of the account which was used</td><td>XXXX123456</td><td>Length: 36 characters</td></tr><tr><td>amount</td><td>Amount for the payment</td><td>long</td><td>Length: 36 characters</td></tr><tr><td>transactionType</td><td></td><td>String</td><td></td></tr><tr><td>transactionTimestamp</td><td>Timestamp of when the transaction was attempted</td><td>Transaction id returned by gateway</td><td>Length: 36 characters</td></tr><tr><td>gatewayTransactionId</td><td>transaction Id returned by gateway</td><td>String</td><td></td></tr><tr><td>gatewayReferenceId</td><td>Reference id returned by the gateway</td><td>String </td><td>Length: 36 characters</td></tr><tr><td>gatewayResponseStatus</td><td>Response status returned by gateway</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>udfParameters</td><td></td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>gatewayResponseCode</td><td>response code which will receive from the gateway</td><td>String</td><td></td></tr><tr><td>gatewayResponseMessage</td><td>response message which will receive from the gateway</td><td>String</td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Request" %}
```json
{
    "deviceFingerprint" : "",
    "payerVpa" : "9620686057.bankezy@payu",
    "payeeVpa" : "918296364009.bankezy@payu",
    "payeeName" : "",
    "amount" : "100",
    "upiRequestId" : "",
    "bankAccountUniqueId" : "89",
    "remarks" : "",
    "currency" :"INR",
    "transacType" : "P2P_PAY",
    "isAmountBlocked" : "true",
    "refUrl" : "https://www.juspay.com/",
    "refCategory" :"",
    "mcc" : "",
    "transacationReference" : "",
    "udfParameters" :"",
    "originalTxnId" : "202207110910298029hQ36zM2"
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
  "resCode": 200,
  "resDesc": "SUCCESS",
  "data": {
    "merchantId": "TEST",
    "merchantChannelId": "TESTAPP",
    "merchantCustomerId": "test-merchantcustomer-1",
    "merchantRequestId": "redId1234",
    "customerMobileNumber": "919988776655",
    "payerVpa": "customervpa@bank",
    "payeeMcc": "0000",
    "payeeMerchantCustomerId": "DEMO-CUST-5678",
    "payeeName": "John Doe",
    "payeeVpa": "payee@xyz",
    "refUrl": "https://www.abcxyz.com/",
    "bankAccountUniqueId": "fb96f8b2b1ab0c070d0d894fd2e577a3d6129882c874e3700505eebfb8070",
    "bankCode": "123456",
    "maskedAccountNumber": "XXXX123456",
    "amount": "2.00",
    "transactionType": "INTENT_PAY",
    "transactionTimestamp": "2017-06-09T17:57:49+05:30",
    "gatewayTransactionId": "AUTef1a2908395239df56663244f8c7deaa",
    "gatewayReferenceId": "809323430413",
    "gatewayResponseStatus": "SUCCESS",
    "gatewayResponseCode": "00",
    "gatewayResponseMessage": "Your transaction is successful"
  },
  "udfParameters": "{}"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/transaction//v1/sendMoney' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
    "deviceFingerprint" : "",
    "payerVpa" : "9620686057.bankezy@payu",
    "payeeVpa" : "918296364009.bankezy@payu",
    "payeeName" : "",
    "amount" : "100",
    "upiRequestId" : "",
    "bankAccountUniqueId" : "89",
    "remarks" : "",
    "currency" :"INR",
    "transacType" : "P2P_PAY",
    "isAmountBlocked" : "90438cddc696b80d1559c8d754b6088ae82ff45b170e46e569a4870ac1da9060",
    "refUrl" : "https://www.juspay.com/",
    "refCategory" :"",
    "mcc" : "",
    "transacationReference" : "",
    "udfParameters" :"",
    "originalTxnId" : "202207110910298029hQ36zM2"
}'
```
{% endtab %}
{% endtabs %}
