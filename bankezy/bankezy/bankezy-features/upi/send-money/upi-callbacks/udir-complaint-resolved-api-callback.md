---
description: This callback is given for complaint with resolve.
---

# UDIR Complaint Resolved API callback

| Parameters                   | Description                                                       |
| ---------------------------- | ----------------------------------------------------------------- |
| adjAmount                    | <p><br>Amount of transaction sent in request.</p>                 |
| adjFlag                      | Reason flag for complaint sent in request                         |
| adjCode                      | Reason code for complaint sent in request                         |
| customerMobileNumber         | Payer Mobile number                                               |
| currCycle                    | Is this resloved in current cycle                                 |
| crn                          | Customer ref number                                               |
| gatewayComplaintId           | UPI request id passed in the request.                             |
| gatewayResponseCode          | Response code returned by gateway for the transaction.            |
| gatewayResponseStatus        | Response status returned by gateway                               |
| gatewayResponseMessage       | Verbose response message returned by gateway for the transaction. |
| merchantId                   | UPI request id returned by gateway for the transaction.           |
| merchantChannelId            | Unique id for the channel via which request is made.              |
| merchantCustomerId           | Merchant generated unique id for customer who sent the payment.   |
| originalGatewayTransactionId | Unique Transaction Request id                                     |
| orgRespCode                  | -                                                                 |
| payeeVpa                     | Vpa of the customer who received the payment.                     |
| payerVpa                     | Vpa of the upi user who sent the payment.                         |
| remarks                      | Remarks for the txn                                               |
| originalTransactionTimestamp | Timestamp of when the payment was received.                       |
| type                         | CUSTOMER\_COMPLAINT\_RESOLVED                                     |
| transactionAmount            | Transaction amount                                                |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
"adjAmount": "0.50",
"adjFlag" : "PBRB",
"adjCode" : "U010",
"customerMobileNumber": "919988776655",
"crn": "302570532",
"currCycle" : "Y",
"gatewayComplaintId": "AIX699393106f865d1a9467c59725789tgh",
"gatewayReferenceId": "123456",
"gatewayResponseCode" : "00",
"gatewayResponseStatus": "SUCCESS"
"gatewayResponseMessage": "Complaint is Resolved"
"merchantId": "TEST",
"merchantChannelId": "TESTAPP",
"merchantCustomerId": "test-merchantcustomer-1",
"originalGatewayTransactionId" : "AIX699393106f865d1a9467c59725789tgh",
"orgSettRespCode" : "RR",
"originalTransactionTimestamp" : "2021-08-12T22:50:00+05:30",
"payeeVpa": "83746598743@2312",
"payerVpa": "123454306@1234",
"remarks" : "Goods not received",
"transactionAmount": "1.00" ,
"type": "CUSTOMER_COMPLAINT_RESOLVED"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/callback/resolved
?X-API-KEY=Juspay' \
--header 'X-PROGRAM-ID: 2001' \
--header 'Content-Type: application/json' \
--data-raw '{
"adjAmount": "0.50",
"adjFlag" : "PBRB",
"adjCode" : "U010",
"customerMobileNumber": "919988776655",
"crn": "302570532",
"currCycle" : "Y",
"gatewayComplaintId": "AIX699393106f865d1a9467c59725789tgh",
"gatewayReferenceId": "123456",
"gatewayResponseCode" : "00",
"gatewayResponseStatus": "SUCCESS"
"gatewayResponseMessage": "Complaint is Resolved"
"merchantId": "TEST",
"merchantChannelId": "TESTAPP",
"merchantCustomerId": "test-merchantcustomer-1",
"originalGatewayTransactionId" : "AIX699393106f865d1a9467c59725789tgh",
"orgSettRespCode" : "RR",
"originalTransactionTimestamp" : "2021-08-12T22:50:00+05:30",
"payeeVpa": "83746598743@2312",
"payerVpa": "123454306@1234",
"remarks" : "Goods not received",
"transactionAmount": "1.00" ,
"type": "CUSTOMER_COMPLAINT_RESOLVED"
}'
```
{% endtab %}
{% endtabs %}

