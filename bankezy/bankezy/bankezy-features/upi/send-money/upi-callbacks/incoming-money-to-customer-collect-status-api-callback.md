---
description: >-
  This callback is given when the customer sends a collect request to any upi
  user and when the same gets approved/declined/expired.
---

# Incoming Money to Customer - Collect Status API callback

| Parameters              | Description                                                                                                |
| ----------------------- | ---------------------------------------------------------------------------------------------------------- |
| amount                  | <p><br>Amount for which customer made the payment.</p>                                                     |
| bankAccountUniqueId     | Unique hash for the customer bank account used for transaction.                                            |
| bankCode                | IIN for the customer bank account used for transaction.                                                    |
| customResponse          | Stringified JSON parameter for future use.                                                                 |
| expiry                  | Expiry timestamp for the collect request.                                                                  |
| gatewayReferenceId      | Customer reference number (rrn) for the transaction.                                                       |
| gatewayResponseCode     | Response code returned by gateway for the transaction. Refer below.                                        |
| gatewayResponseMessage  | Verbose response message returned by gateway for the transaction.                                          |
| gatewayResponseStatus   | Response status returned by gateway                                                                        |
| gatewayTransactionId    | UPI request id returned by gateway for the transaction.                                                    |
| maskedAccountNumber     | Masked account number for the customer bank account used for transaction.                                  |
| merchantChannelId       | Unique id for the channel via which request is made.                                                       |
| merchantCustomerId      | Merchant generated unique id for customer who sent the payment.                                            |
| merchantId              | Unique id for merchant.                                                                                    |
| merchantRequestId       | Merchant generated request id as passed in the collect request.                                            |
| payeeMcc                | Merchant Category Code of the payee merchant.                                                              |
| payeeMerchantCustomerId | Merchant generated unique id for customer who received the payment. Only if it is an onus P2P transaction. |
| payeeMobileNumber       | Mobile number of the customer who received the payment.                                                    |
| payeeVpa                | Vpa of the customer who received the payment.                                                              |
| payerMerchantCustomerId | Merchant generated unique id for customer who sent the payment. Only if it is an onus transaction.         |
| payerName               | Name of the upi user who sent the payment.                                                                 |
| payerVpa                | Vpa of the upi user who sent the payment.                                                                  |
| refUrl                  | Invoice as sent by merchant or reference to the transaction in the form of url.                            |
| transactionTimestamp    | Timestamp of when the payment was received.                                                                |
| type                    | Event type of the callback - CUSTOMER\_CREDITED\_VIA\_COLLECT.                                             |
| udfParameters           | Udf parameters as passed in the original payment request.                                                  |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
  "amount": "100.00",
  "bankAccountUniqueId" : "fb96f8b2b...1ab0c070d0d894",
  "bankCode" : "123456",
  "customResponse": "{}",
  "expiry": "2016-11-25T00:10:00+05:30",
  "gatewayReferenceId": "806115044725",
  "gatewayResponseCode": "00",
  "gatewayResponseMessage": "Transaction is approved",
  "gatewayResponseStatus": "SUCCESS",
  "gatewayTransactionId": "XYZd0c077...f39c454979",
  "maskedAccountNumber" : "XXXX123456",
  "merchantChannelId": "DEMOUATAPP",
  "merchantCustomerId": "DEMO-CUST-1234",
  "merchantId": "DEMOUAT01",
  "merchantRequestId": "TXN1234567",
  "payeeMcc": "4121",
  "payeeMerchantCustomerId": "DEMO-CUST-1234",
  "payeeMobileNumber" : "919812388554",
  "payeeVpa" : "customer1@abc",
  "payerMerchantCustomerId": "DEMO-CUST-5678"
  "payerName": "Customer Name",
  "payerVpa": "customer@xyz",
  "refUrl": "https://www.abcxyz.com/",
  "remarks" : "Sample remarks",
  "transactionTimestamp": "2016-11-25T00:00:00+05:30",
  "type": "CUSTOMER_CREDITED_VIA_COLLECT",
  "udfParameters": "{}"
}

```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/callback/v1/incomingMoneyToCustomerCsCallback?X-API-KEY=Juspay' \
--header 'x-program-id: 2001' \
--header 'Content-Type: application/json' \
--data-raw '{
  "amount": "1.00",
  "bankAccountUniqueId" : "fb96f8b2b...1ab0c070d0d894",
  "bankCode" : "123456",
  "customResponse": "{}",
  "expiry": "2016-11-25T00:10:00+05:30",
  "gatewayReferenceId": "806115044725",
  "gatewayResponseCode": "00",
  "gatewayResponseMessage": "Transaction is approved",
  "gatewayResponseStatus": "SUCCESS",
  "gatewayTransactionId": "XYZd0c077...f39c454979",
  "maskedAccountNumber" : "XXXX123456",
  "merchantChannelId": "DEMOUATAPP",
  "merchantCustomerId": "DEMO-CUST-1234",
  "merchantId": "DEMOUAT01",
  "merchantRequestId": "TXN1234567",
  "payeeMcc": "4121",
  "payeeMerchantCustomerId": "DEMO-CUST-1234",
  "payeeMobileNumber" : "919812388554",
  "payeeVpa" : "customer1@abc",
  "payerMerchantCustomerId": "DEMO-CUST-5678",
  "payerName": "Customer Name",
  "payerVpa": "customer@xyz",
  "refUrl": "https://www.abcxyz.com/",
  "remarks" : "Sample remarks",
  "transactionTimestamp": "2016-11-25T00:00:00+05:30",
  "type": "CUSTOMER_CREDITED_VIA_COLLECT",
  "udfParameters": "{}"
}'
```
{% endtab %}
{% endtabs %}

