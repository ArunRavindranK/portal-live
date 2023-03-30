---
description: This api returns list of all the pending collect requests for the customer.
---

# List Pending Collect Requests API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/transaction/v1/listPendingCollectRequests" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
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

| Response Field       | Field Description                                                                                                    | Data Type                  | Length                   |
| -------------------- | -------------------------------------------------------------------------------------------------------------------- | -------------------------- | ------------------------ |
| status               | SUCCESS, FAILURE                                                                                                     | String                     | Variable, 5–8 characters |
| merchantId           | Unique id for the merchant as passed in request headers                                                              | String                     | Variable, 5–8 characters |
| merchantChannelId    | Unique id for the merchant channel as passed in request headers                                                      | String                     | Length: 36 characters    |
| merchantCustomerId   | Merchant generated unique profile id for customer as passed in the request                                           | String                     | Length: 36 characters    |
| customerMobileNumber | Customer mobile number                                                                                               | String                     | 12 digits mobile number  |
| payerVpa             | Vpa of the customer/payer to which collect request request was sent                                                  | As passed in the request   | Length: 36 characters    |
| payeeVpa             | Customer vpa used for the payment                                                                                    | As passed in the request   | Length: 36 characters    |
| payeeName            | Name of the payee by whom collect request was sent                                                                   | String                     | Variable, 5–8 characters |
| isVerifiedPayee      | Flag if the payee is a verified vpa                                                                                  | String                     | Variable, 5–8 characters |
| isMarkedSpam         | Flag if the payee is marked as spam                                                                                  | String                     | Variable, 5–8 characters |
| payeeMcc             | Merchant Category Code of the payee vpa                                                                              | String                     | Variable, 5–8 characters |
| transactionTimestamp | Timestamp of when the transaction was attempted                                                                      | YYYY-MM-DDTHH:MM:SS+05:30  |                          |
| remarks              | Transaction remarks sent by payee                                                                                    | String                     | Variable, 5–8 characters |
| udfParameters        | Udf parameters as passed in the request                                                                              | String                     | Variable, 5–8 characters |
| collectType          | Differentiates between a transaction collect request (TRANSACTION) or a mandate execution collect request (MANDATE). | `TRANSACTION` or `MANDATE` | Variable, 5–8 characters |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
  "merchantCustomerId": "2928",
  "udfParameters": "{}"
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
    "customerMobileNumber": "919988776655",
    "pendingTransactions": [{
      "payerVpa": "vpa@bank",
      "payeeVpa": "swiggy@upi",
      "payeeName": "Swiggy",
      "isVerifiedPayee": "true",
      "isMarkedSpam": "true",
      "amount": "100.00",
      "payeeMcc": "1520",
      "transactionTimestamp": "2017-06-09T07:46:45+00:00",
      "gatewayTransactionId": "AUTef1a2908395239df56663244f8c7deaa",
      "gatewayReferenceId": "809323430413",
      "remarks": "REMARKS",
      "expiry": "2017-06-09T10:46:45+00:00",
      "refUrl": "https://www.asd.com",
      "refCategory": "02",
      "collectType": "MANDATE",
      "seqNumber": "2"
    }]
  },
  "udfParameters": "{}"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/transaction/v1/listPendingCollectRequests' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
  "merchantCustomerId": "2928",
  "udfParameters": "{}"
}'J
```
{% endtab %}
{% endtabs %}
