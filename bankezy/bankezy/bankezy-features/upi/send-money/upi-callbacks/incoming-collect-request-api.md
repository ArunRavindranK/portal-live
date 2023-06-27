---
description: >-
  This callback is given when a customer receives a collect request from any UPI
  user. This enables merchant server to notify the customer, so that she can
  take action on the request.
---

# Incoming Collect Request API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/callback/v1/incomingCollectRequestToCustomer" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnId" required="true" %}
Trnsaction ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerVpa" required="true" %}
Vpa of the UPI user who received the collect request.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeVpa" required="true" %}
Vpa of the customer who sent the collect request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeName" required="true" %}
Name of the payer to whom collect request was sent.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerName" required="true" %}
Name of the payer to whom collect request was sent.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" required="true" %}
Transaction Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="currency" required="true" %}
INR
{% endswagger-parameter %}

{% swagger-parameter in="body" name="approvalStatus" required="true" %}
Transaction status approval
{% endswagger-parameter %}

{% swagger-parameter in="body" name="remarks" required="true" %}
Remarks sent by customer for the collect request.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnDate" required="true" %}
Transaction date
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

{% tabs %}
{% tab title="Sample Request" %}
```json
{
   "txnId": "PUODQrLhZDEExH8VsfdX2pxblATKYy0iVaQ",

    "payeeVpa": "9902881784.bankezy1@payu",

    "payerVpa": "9620686057.bankezy3@payu",

    "txnAmount": 100,

    "approvalStatus": "ACCEPT",

    "remarks": "test",

    "walletId": "695"

}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/collectrequest/v1/incoming' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
   "txnId": "PUODQrLhZDEExH8VsfdX2pxblATKYy0iVaQ",

    "payeeVpa": "9902881784.bankezy1@payu",

    "payerVpa": "9620686057.bankezy3@payu",

    "txnAmount": 100,

    "approvalStatus": "ACCEPT",

    "remarks": "test",

    "walletId": "695"

}'
```
{% endtab %}
{% endtabs %}

