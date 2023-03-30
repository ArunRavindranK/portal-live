---
description: >-
  This callback is given when a customer receives a collect request from any UPI
  user. This enables merchant server to notify the customer, so that she can
  take action on the request.
---

# Incoming Collect Request to Customer API callback

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
    "amount": "2.89",
    "customResponse": "{}",
    "expiry": "2022-12-01T13:17:31+05:30",
    "gatewayReferenceId": "233530629228",
    "gatewayTransactionId": "PUO1669879051108497",
    "merchantCustomerId": "65",
    "merchantId": "WIBMOPAYUTEST",
    "payeeMcc": "0000",
    "payeeMerchantCustomerId": "497",
    "payeeName": "SaraswathiManmi",
    "payeeVpa": "7022070219.citrus25@payu",
    "payerMerchantCustomerId": "3178",
    "payerVpa": "8951851037.citrus4@payu",
    "refCategory": "00",
    "refUrl": "https://www.juspay.com/",
    "remarks": "testing",
    "transactionTimestamp": "2022-12-01T12:47:31+05:30",
    "type": "COLLECT_REQUEST_RECEIVED"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/callback/v1/incomingCollectRequestToCustomer?X-API-KEY=Juspay' \
--header 'X-PROGRAM-ID: 2001' \
--header 'Content-Type: application/json' \
--data-raw '{
    "amount": "2.89",
    "customResponse": "{}",
    "expiry": "2022-12-01T13:17:31+05:30",
    "gatewayReferenceId": "233530629228",
    "gatewayTransactionId": "PUO1669879051108497",
    "merchantCustomerId": "65",
    "merchantId": "WIBMOPAYUTEST",
    "payeeMcc": "0000",
    "payeeMerchantCustomerId": "497",
    "payeeName": "SaraswathiManmi",
    "payeeVpa": "7022070219.citrus25@payu",
    "payerMerchantCustomerId": "3178",
    "payerVpa": "8951851037.citrus4@payu",
    "refCategory": "00",
    "refUrl": "https://www.juspay.com/",
    "remarks": "testing",
    "transactionTimestamp": "2022-12-01T12:47:31+05:30",
    "type": "COLLECT_REQUEST_RECEIVED"
}'
```
{% endtab %}
{% endtabs %}

