---
description: >-
  This callback is given when a customer receives a collect request from any UPI
  user. This enables merchant server to notify the customer, so that she can
  take action on the request.
---

# Incoming Collect Request to Customer API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/callback/v1/v1/incomingCollectRequestToCustomer" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-TOKEN" %}
TOKEN
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

| Response Parameter      | Response Description                                                                                                                           |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| amo                     | Amount for which customer received the collect request.                                                                                        |
| customResponse          | Stringified JSON parameter for future use.                                                                                                     |
| expiry                  | Expiry timestamp for the collect request.                                                                                                      |
| gatewayReferenceId      | Customer reference number (rrn) for the transaction.                                                                                           |
| gatewayTransactionId    | UPI request id returned by gateway for the transaction.                                                                                        |
| isVerifiedPayee         | Stringified boolean flag if the payee is a verified vpa.                                                                                       |
| isMarkedSpam            | Stringified boolean flag if the payee is marked as spam.                                                                                       |
| merchantCustomerId      | Merchant generated unique id for customer who received the collect request.                                                                    |
| merchantId              | Unique id for merchant.                                                                                                                        |
| payeeMcc                | Merchant Category Code of the payee merchant.                                                                                                  |
| payeeMerchantCustomerId | Merchant generated unique id for customer who initiated the collect request.                                                                   |
| payeeName               | Name of the upi user who sent the collect request.                                                                                             |
| payeeVpa                | Vpa of the upi user who sent the collect request.                                                                                              |
| payerMerchantCustomerId | Merchant generated unique id for customer who received the collect request.                                                                    |
| payerVpa                | If collectType is null or TRANSACTION, Vpa of the customer who received the collect request and if collectType is MANDATE, umn of the mandate. |
| collectType             | Differentiates between a transaction collect request (TRANSACTION) or a mandate execution collect request (MANDATE).                           |
| seqNumber               | Denotes the recurring cycle of mandate execution. Will be received only during mandate executions.                                             |
| refUrl                  | Invoice as sent by merchant or reference to the transaction in the form of url.                                                                |
| remarks                 | Remarks sent by upi user for the collect request.                                                                                              |
| type                    | Event type of the callback - COLLECT\_REQUEST\_RECEIVED.                                                                                       |
| transactionTimestamp    | Timestamp of when the collect request was received. (YYYY-MM-DDTHH:MM:SS+05:30)                                                                |
