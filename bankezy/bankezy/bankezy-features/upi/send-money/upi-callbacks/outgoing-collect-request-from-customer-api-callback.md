---
description: >-
  This callback is given when a customer sends a collect request to any UPI
  user. This enables merchant server to notify the customer, that his collect
  request is send successfully.
---

# Outgoing Collect Request from Customer API callback

| Parameters              | Description                                                                                                                                                                                |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| amount                  | <p><br>Amount for which customer made the payment.</p>                                                                                                                                     |
| bankAccountUniqueId     | Unique hash for the customer bank account used for transaction.                                                                                                                            |
| bankCode                | IIN for the customer bank account used for transaction.                                                                                                                                    |
| customResponse          | Stringified JSON parameter for future use.                                                                                                                                                 |
| gatewayReferenceId      | Customer reference number (rrn) for the transaction.                                                                                                                                       |
| gatewayResponseCode     | Response code returned by gateway for the transaction. Refer below.                                                                                                                        |
| gatewayResponseMessage  | Verbose response message returned by gateway for the transaction.                                                                                                                          |
| gatewayResponseStatus   | Response status returned by gateway                                                                                                                                                        |
| gatewayTransactionId    | UPI request id returned by gateway for the transaction.                                                                                                                                    |
| maskedAccountNumber     | Masked account number for the customer bank account used for transaction.                                                                                                                  |
| merchantChannelId       | Unique id for the channel via which request is made.                                                                                                                                       |
| merchantCustomerId      | Merchant generated unique id for customer who sent the payment.                                                                                                                            |
| merchantId              | Unique id for merchant.                                                                                                                                                                    |
| merchantRequestId       | Merchant generated request id as passed in the collect request                                                                                                                             |
| expiry                  | Expiry timestamp for the collect request                                                                                                                                                   |
| payeeMcc                | Merchant Category Code of the payee merchant.                                                                                                                                              |
| payeeMerchantCustomerId | Merchant generated unique id for customer who received the payment. Only if it is an onus P2P transaction.                                                                                 |
| payeeName               | Name of the upi user who received the payment.                                                                                                                                             |
| payeeVpa                | Vpa of the upi user who received the payment.                                                                                                                                              |
| payerMerchantCustomerId | Merchant generated unique id for customer who sent the payment.                                                                                                                            |
| payerMobileNumber       | Mobile number of the customer who made the payment.                                                                                                                                        |
| payerVpa                | If collectType is null or TRANSACTION, Vpa of the customer who received the collect request and if collectType is MANDATE, umn of the mandate.                                             |
| requestType             | Action which was taken on the collect request. Will not be present in case of EXPIRED callback.                                                                                            |
| collectType             | Differentiates between a transaction collect request (TRANSACTION) or a mandate execution collect request (MANDATE).                                                                       |
| seqNumber               | applicable only for collect mandate Denotes the recurring cycle of mandate execution. Will be received only during mandate executions. It will only be present in case of mandate request. |
| refUrl                  | Invoice as sent by merchant or reference to the transaction in the form of url.                                                                                                            |
| remarks                 | Remarks sent by customer for the collect request.                                                                                                                                          |
| transactionTimestamp    | Timestamp of when the payment was received. (YYYY-MM-DDTHH:MM:SS+05:30)                                                                                                                    |
| type                    | COLLECT\_REQUEST\_SENT                                                                                                                                                                     |
| udfParameters           | Udf parameters as passed in the original payment request.                                                                                                                                  |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
  "amount": "100.00",
  "bankAccountUniqueId": "4536baef...32cdba67",
  "bankCode" : "123456",
  "customResponse": "{}",
  "expiry": "2016-11-25T00:30:00+05:30",
  "gatewayReferenceId": "806115044725",
  "gatewayResponseCode": "00",
  "gatewayResponseMessage": "Collect request sent successfully",
  "gatewayResponseStatus": "SUCCESS",
  "gatewayTransactionId": "XYZd0c077f39c454979...",
  "maskedAccountNumber" : "XXXXXXX9988",
  "merchantChannelId": "DEMOUAT01",
  "merchantCustomerId": "DEMO-CUST-1234",
  "merchantId": "DEMOUAT01",
  "merchantRequestId": "TXN1234567",
  "payeeMcc": "4121",
  "payeeMerchantCustomerId": "DEMO-CUST-1234",
  "payeeMobileNumber": "919876543210",
  "payeeVpa": "customer@xyz",
  "payerName": "Customer Name",
  "payerVpa": "customer1@abc",
  "refUrl": "https://www.abcxyz.com/",
  "remarks": "This is remarks",
  "transactionTimestamp": "2016-11-25T00:00:00+05:30",
  "type": "COLLECT_REQUEST_SENT",
  "udfParameters": "{}"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/callback/v1/outgoingCollectRequestFromCustomer?X-API-KEY=Juspay' \
--header 'x-program-id: 2001' \
--header 'Content-Type: application/json' \
--data-raw '{
  "amount": "100.00",
  "bankAccountUniqueId": "4536baef...32cdba67",
  "bankCode" : "123456",
  "customResponse": "{}",
  "expiry": "2016-11-25T00:30:00+05:30",
  "gatewayReferenceId": "806115044725",
  "gatewayResponseCode": "00",
  "gatewayResponseMessage": "Collect request sent successfully",
  "gatewayResponseStatus": "SUCCESS",
  "gatewayTransactionId": "",
  "maskedAccountNumber" : "XXXXXXX9988",
  "merchantChannelId": "DEMOUAT01",
  "merchantCustomerId": "DEMO-CUST-1234",
  "merchantId": "DEMOUAT01",
  "merchantRequestId": "TXN1234567",
  "payeeMcc": "4121",
  "payeeMerchantCustomerId": "DEMO-CUST-1234",
  "payeeMobileNumber": "919876543210",
  "payeeVpa": "customer@xyz",
  "payerName": "Customer Name",
  "payerVpa": "customer1@abc",
  "refUrl": "https://www.abcxyz.com/",
  "remarks": "This is remarks",
  "transactionTimestamp": "2016-11-25T00:00:00+05:30",
  "type": "COLLECT_REQUEST_SENT",
  "udfParameters": "{}"
}'
```
{% endtab %}
{% endtabs %}

