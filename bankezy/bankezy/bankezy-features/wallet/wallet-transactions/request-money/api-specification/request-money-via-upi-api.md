---
description: This api can be used to request money from another VPA.
---

# Request Money via UPI API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/transaction/v1/requestMoney" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeVPA" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="payerVPA" %}
Vpa of the payer to which collect request is to be sent
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerName" required="true" %}
Name of the payer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeName" required="true" %}
Name of the payee
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" type="long" required="true" %}
Transaction amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="remarks" required="true" %}
Remarks sent by customer for the collect request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="currency" required="true" %}
INR
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" %}
Optional
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

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Response Details

| Response Field       | Field Description                                                          | Data Type                 | Length                   |
| -------------------- | -------------------------------------------------------------------------- | ------------------------- | ------------------------ |
| Status               | SUCCESS, FAILURE status of the API                                         | String                    | Variable, 5–8 characters |
| merchantId           | Unique id for the merchant as passed in request headers                    | String                    | Variable, 5–8 characters |
| merchantChannelId    | Unique id for the merchant channel as passed in request headers            | String                    | Length: 36 characters    |
| merchantCustomerId   | Merchant generated unique profile id for customer as passed in the request | String                    | Length: 36 characters    |
| merchantRequestId    | Merchant generated id for the transaction                                  | As passed in the request  | Length: 36 characters    |
| customerMobileNumber | Customer mobile number                                                     | String                    | Customer mobile number   |
| amount               | Amount for transaction                                                     | long                      | Variable, 2-8 characters |
| expiryTimestamp      | Timestamp of when the collect request will expire                          | YYYY-MM-DDTHH:MM:SS+05:30 |                          |
| payeeVpa             | Customer vpa used for the payment                                          | As passed in the request  | Length: 36 characters    |
| payeeMcc             | MCC for the payee                                                          | String                    | Variable, 4–8 characters |
| payerVpa             | Vpa of the UPI user who received the collect request                       | String                    | Length: 36 characters    |
| payerName            | Name of the payer to whom collect request was sent                         | String                    | Variable, 5–8 characters |
| udfParameters        | Udf parameters as passed in the request                                    | String                    |                          |

## Response Status Code

| gatewayResponseCode | gatewayResponseStatus | Description                         |
| ------------------- | --------------------- | ----------------------------------- |
| 00                  | SUCCESS               | Collect sent successfully.          |
| 01                  | PENDING               | Transaction is in pending state.    |
| 96                  | DEEMED                | Response timeout (DEEMED APPROVED). |
| Else                | FAILURE               | Sending collect request failed.     |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
   "payeeVPA": "7022070219.citrus4@payu",
   "payerVPA": "7914717873@payu",
   "payerName" : "",
   "payeeName" : "",
    "txnAmount": 500.00,
    "walletId" : "354",
    "remarks": "testing",
    "currency" : "INR",
    "udfParameters" : ""

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
    "merchantRequestId": "TXN1234567",
    "customerMobileNumber": "919988776655",
    "amount": "2.00",
    "expiryTimestamp": "2017-06-09T18:27:49+05:30",
    "payeeVpa": "customervpa@bank",
    "payeeMcc": "0000",
    "payerVpa": "payer@xyz",
    "payerName": "John Doe",
    "refUrl": "https://www.abcxyz.com/",
    "remarks": "This is remarks",
    "bankAccountUniqueId": "fb96f8b2b1ab0c070d0d894fd2e577a3d6129882c874e3700505eebfb8070",
    "bankCode": "123456",
    "maskedAccountNumber": "XXXX123456",
    "amount": "2.00",
    "transactionTimestamp": "2017-06-09T17:57:49+05:30",
    "gatewayTransactionId": "AUTef1a2908395239df56663244f8c7deaa",
    "gatewayReferenceId": "809323430413",
    "gatewayResponseStatus": "SUCCESS",
    "gatewayResponseCode": "00",
    "gatewayResponseMessage": "Collect request sent successfully"
  },
  "udfParameters": "{}"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/transaction/v1/requestMoney' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
   "payeeVPA": "7022070219.citrus4@payu",
   "payerVPA": "7914717873@payu",
   "payerName" : "",
   "payeeName" : "",
    "txnAmount": 500.00,
    "walletId" : "354",
    "remarks": "testing",
    "currency" : "INR",
    "udfParameters" : ""

}'
```
{% endtab %}
{% endtabs %}
