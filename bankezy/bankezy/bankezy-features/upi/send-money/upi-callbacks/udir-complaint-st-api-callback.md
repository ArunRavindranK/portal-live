---
description: This callback is given for complaint with resolve.
---

# UDIR Complaint St API callback

| Parameters                   | Description                                                       |
| ---------------------------- | ----------------------------------------------------------------- |
| approvalNumber               |                                                                   |
| reqAdjAmount                 | <p><br>Amount of transaction sent in request.</p>                 |
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
| type                         | CBS\_COMPLAINT\_STATUS\_UPDATE                                    |
| transactionAmount            | Transaction amount                                                |
| ref                          | ref details                                                       |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
approvalNumber: '828676',
merchantChannelId: 'APLTEST',
gatewayResponseStatus: 'CLOSED',
merchantId: 'APLTEST',
gatewayComplaintId: 'PTM5a6d0ab4e34544fab19dca35f755115',
reqAdjAmount: '14.00',
orgSettRespCode: 'RR',
gatewayResponseMessage: “'',
payerVpa: 'tester@mypsp',
originalTransactionTimestamp: '2022-08-30T01:32:03+05:30',
gatewayResponseCode: “'',
gatewayReferenceId: '105199974203',
reqAdjCode: 'U005',
crn: ‘UPI21022053596’,
payeeVpa: '6562774031@axisuat1',
reqAdjFlag: 'PBRB',
transactionAmount: '1.00',
type: 'CBS_COMPLAINT_STATUS_UPDATE',
originalGatewayTransactionId: 'abc9b123066e5414f2983c0ffad989a5e20',
currCycle: 'N',
remarks: 'DRC Initiated',
ref:[ {
adjAmt: '2.00',
adjCode: '102',
adjRefId: 'P1705110000338829745321',
adjFlag: 'DRC',
addr: 'resh@upi',
adjRemarks: 'DRC Initiated',
IFSC: 'AABF0003002',
adjTs: '2020-12-28T00:00:41+05:30',
type: ‘REMITTER’,
approvalNum: '651725'
},
{
adjAmt: '13.00',
adjCode: '102',
adjRefId: 'P1705110000338829745321',
adjFlag: 'TCC',
addr: 'resh@upi',
adjRemarks: 'Credit Reversal done online now',
IFSC: 'x',
adjTs: '2020-05-11T00:00:41+05:30',
type: 'BENEFICIARY',
approvalNum: '651725'
}]
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/callback/cbsComplaintStatusUpdate
?X-API-KEY=Juspay' \
--header 'X-PROGRAM-ID: 2001' \
--header 'Content-Type: application/json' \
--data-raw '{
approvalNumber: '828676',
merchantChannelId: 'APLTEST',
gatewayResponseStatus: 'CLOSED',
merchantId: 'APLTEST',
gatewayComplaintId: 'PTM5a6d0ab4e34544fab19dca35f755115',
reqAdjAmount: '14.00',
orgSettRespCode: 'RR',
gatewayResponseMessage: “'',
payerVpa: 'tester@mypsp',
originalTransactionTimestamp: '2022-08-30T01:32:03+05:30',
gatewayResponseCode: “'',
gatewayReferenceId: '105199974203',
reqAdjCode: 'U005',
crn: ‘UPI21022053596’,
payeeVpa: '6562774031@axisuat1',
reqAdjFlag: 'PBRB',
transactionAmount: '1.00',
type: 'CBS_COMPLAINT_STATUS_UPDATE',
originalGatewayTransactionId: 'abc9b123066e5414f2983c0ffad989a5e20',
currCycle: 'N',
remarks: 'DRC Initiated',
ref:[ {
adjAmt: '2.00',
adjCode: '102',
adjRefId: 'P1705110000338829745321',
adjFlag: 'DRC',
addr: 'resh@upi',
adjRemarks: 'DRC Initiated',
IFSC: 'AABF0003002',
adjTs: '2020-12-28T00:00:41+05:30',
type: ‘REMITTER’,
approvalNum: '651725'
},
{
adjAmt: '13.00',
adjCode: '102',
adjRefId: 'P1705110000338829745321',
adjFlag: 'TCC',
addr: 'resh@upi',
adjRemarks: 'Credit Reversal done online now',
IFSC: 'x',
adjTs: '2020-05-11T00:00:41+05:30',
type: 'BENEFICIARY',
approvalNum: '651725'
}]
}'
```
{% endtab %}
{% endtabs %}

