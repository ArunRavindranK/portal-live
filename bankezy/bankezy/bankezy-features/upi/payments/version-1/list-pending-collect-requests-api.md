# List Pending Collect Requests API

{% swagger method="post" path="" baseUrl="http://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/transaction/listPendingCollectRequests/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantCustomerId" required="true" %}
merchantCustomerId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" type="JSON" required="true" %}
user definded parameters
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

## Custom response codes

{% tabs %}
{% tab title="Sample CURL request" %}
```
curl --location --request POST 'http://localhost:7060/upi-integration/upi/transaction/v1/listPendingCollectRequests' \
--header 'x-program-id: 2001' \
--header 'x-account-number: 3461'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
  "merchantCustomerId": "2928",
  "udfParameters": "{}"
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
  "status": "SUCCESS",
  "responseCode": "UPI200",
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
{% endtabs %}
