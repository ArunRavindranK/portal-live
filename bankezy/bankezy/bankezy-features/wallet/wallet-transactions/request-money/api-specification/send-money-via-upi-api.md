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

| Response Field          | Field Description                                                                                          | Data Type                          | Length                   |
| ----------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------- | ------------------------ |
| status                  | SUCCESS, FAILURE status of the API                                                                         | String                             | Variable, 5–8 characters |
| merchantId              | Unique id for the merchant as passed in request headers                                                    | String                             | Variable, 5–8 characters |
| merchantChannelId       | Unique id for the merchant channel as passed in request headers                                            | String                             | Length: 36 characters    |
| merchantRequestId       | Merchant generated id for the transaction                                                                  | String                             | Length: 36 characters    |
| merchantCustomerId      | Merchant generated unique profile id for customer as passed in the request                                 | String                             | Length: 36 characters    |
| customerMobileNumber    | Customer mobile number                                                                                     | String                             | 12 digits mobile number  |
| payerVpa                | Customer vpa used for the payment                                                                          | String                             | Length: 36 characters    |
| payeeMcc                | MCC for the payee                                                                                          | String                             | Variable, 5–8 characters |
| payeeMerchantCustomerId | Merchant generated unique id for customer who received the payment. Only if it is an onus P2P transaction. | String                             | Length: 36 characters    |
| payeeVpa                | Vpa of the upi user who received the payment                                                               | String                             | Length: 36 characters    |
| refUrl                  | Reference url for the intent transaction                                                                   | String                             | Length: 36 characters    |
| bankAccountUniqueId     | Unique id for the selected bank account                                                                    | As passed in the request           | Length: 36 characters    |
| bankCode                | Bank code of the account which was used                                                                    | Valid bank IIN                     | Length: 36 characters    |
| maskedAccountNumber     | Masked account number of the account which was used                                                        | XXXX123456                         | Length: 36 characters    |
| amount                  | Amount for the payment                                                                                     | long                               | Length: 36 characters    |
| transactionTimestamp    | Timestamp of when the transaction was attempted                                                            | Transaction id returned by gateway | Length: 36 characters    |
| gatewayReferenceId      | Reference id returned by the gateway                                                                       | String                             | Length: 36 characters    |
| gatewayResponseStatus   | Response status returned by gateway                                                                        | String                             | Variable, 5–8 characters |
| udfParameters           |                                                                                                            |                                    | Variable, 5–8 characters |
|                         |                                                                                                            |                                    |                          |
|                         |                                                                                                            |                                    |                          |
|                         |                                                                                                            |                                    |                          |

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
    "isAmountBlocked" : "90438cddc696b80d1559c8d754b6088ae82ff45b170e46e569a4870ac1da9060",
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
  "status": "SUCCESS",
  "responseCode": "SUCCESS",
  "responseMessage": "SUCCESS",
  "payload": {
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
