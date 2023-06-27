---
description: This callback is given when the customer receives money from any upi user.
---

# Incoming Money to Customer - Pay API callback

| Parameters              | Description                                                                                                |
| ----------------------- | ---------------------------------------------------------------------------------------------------------- |
| amount                  | <p><br>Amount for which customer made the payment.</p>                                                     |
| bankAccountUniqueId     | Unique hash for the customer bank account used for transaction.                                            |
| bankCode                | IIN for the customer bank account used for transaction.                                                    |
| customResponse          | Stringified JSON parameter for future use.                                                                 |
| gatewayReferenceId      | Customer reference number (rrn) for the transaction.                                                       |
| gatewayResponseCode     | Response code returned by gateway for the transaction. Refer below.                                        |
| gatewayResponseMessage  | Verbose response message returned by gateway for the transaction.                                          |
| gatewayResponseStatus   | Response status returned by gateway                                                                        |
| gatewayTransactionId    | UPI request id returned by gateway for the transaction.                                                    |
| maskedAccountNumber     | Masked account number for the customer bank account used for transaction.                                  |
| merchantCustomerId      | Merchant generated unique id for customer who sent the payment.                                            |
| merchantId              | Unique id for merchant.                                                                                    |
| payeeMcc                | Merchant Category Code of the payee merchant.                                                              |
| payeeMerchantCustomerId | Merchant generated unique id for customer who received the payment. Only if it is an onus P2P transaction. |
| payeeMobileNumber       | Mobile number of the customer who received the payment.                                                    |
| payeeVpa                | Vpa of the customer who received the payment.                                                              |
| payerMerchantCustomerId | Merchant generated unique id for customer who sent the payment. Only if it is an onus transaction.         |
| payerName               | Name of the upi user who sent the payment.                                                                 |
| payerVpa                | Vpa of the upi user who sent the payment.                                                                  |
| refUrl                  | Invoice as sent by merchant or reference to the transaction in the form of url.                            |
| transactionTimestamp    | Timestamp of when the payment was received.                                                                |
| type                    | CUSTOMER\_CREDITED\_VIA\_PAY                                                                               |
| udfParameters           | Udf parameters as passed in the original payment request.                                                  |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
  "amount": "100.00",
  "bankAccountUniqueId" : "fb96f8b2b1ab0c070d0d894......",
  "bankCode" : "123456",
  "customResponse": "{}",
  "gatewayReferenceId": "806115044725",
  "gatewayResponseCode": "00",
  "gatewayResponseMessage": "Transaction is approved",
  "gatewayResponseStatus": "SUCCESS",
  "gatewayTransactionId": "XYZd0c077f39c454979...",
  "maskedAccountNumber" : "XXXX123456",
  "merchantCustomerId": "DEMO-CUST-1234",
  "merchantId": "DEMOUAT01",
  "payeeMcc": "4121",
  "payeeMerchantCustomerId": "DEMO-CUST-1234",
  "payeeMobileNumber" : "919812388554",
  "payeeVpa" : "customer1@abc",
  "payerMerchantCustomerId": "DEMO-CUST-5678",
  "payerName": "Customer Name",
  "payerVpa": "customer@xyz",
  "refUrl": "https://www.abcxyz.com/",
  "transactionTimestamp": "2016-11-25T00:00:00+05:30",
  "type": "CUSTOMER_CREDITED_VIA_PAY",
  "udfParameters": "{}"
}

```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/callback/v1/transaction/status?X-API-KEY=Juspay' \
--header 'X-PROGRAM-ID: 2001' \
--header 'Content-Type: application/json' \
--data-raw '{
  "amount": "",
  "bankAccountUniqueId": "",
  "bankCode" : "",
  "customResponse": "{}",
  "gatewayReferenceId": "",
  "gatewayResponseCode": "",
  "gatewayResponseMessage": "",
  "gatewayResponseStatus": "",
  "gatewayTransactionId": "",
  "maskedAccountNumber" : "",
  "merchantChannelId": "",
  "merchantCustomerId": "",
  "merchantId": "",
  "merchantRequestId": "",
  "payeeMcc": "",
  "payeeMerchantCustomerId": "",
  "payeeName": "",
  "payeeVpa": "",
  "payerMerchantCustomerId": "",
  "payerMobileNumber" : "",
  "payerVpa": "",
  "requestType": "",
  "collectType" : "",
  "seqNumber" : "",
  "refUrl": "",
  "transactionTimestamp": "",
  "type": "",
  "udfParameters": "{}"
}'
```
{% endtab %}
{% endtabs %}

