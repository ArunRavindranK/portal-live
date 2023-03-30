---
description: This API can be used to check the status of  Device Binding.
---

# UPI Registration Status Inquiry API



{% swagger method="post" path="" baseUrl="/upi-integration/upi/registration/v1/status" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ssid" required="true" %}
Identifier of the SIM used to send the SMS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="true" %}
Unique identifier for the device
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

| Response Field        | Field Description                                                          | Data Type | Length                   |
| --------------------- | -------------------------------------------------------------------------- | --------- | ------------------------ |
| status                | SUCCESS, FAILURE status of the API                                         | String    | Variable, 5–8 characters |
| merchantId            | Unique id for the merchant as passed in request headers                    | String    | Variable, 5–8 characters |
| merchantChannelId     | Unique id for the merchant channel as passed in request headers            | String    | Length: 36 characters    |
| merchantCustomerId    | Merchant generated unique profile id for customer as passed in the request | String    | Length: 36 characters    |
| customerMobileNumber  | Customer mobile number                                                     | String    | 12 digits mobile number  |
| gatewayTransactionId  | upiRequestId as passed in request                                          | String    | Length: 36 characters    |
| gatewayResponseStatus | Response status returend by gateway                                        | String    | Variable, 5–8 characters |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
  "ssid" :  ["1c776e05188a0f27c"],   
   " deviceId": "8991000903658589244"
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
    "queryClosingTimestamp": "2016-11-25T00:00:00+05:30",
    "gatewayTransactionId": "AUTef1a2908395239df56663244f8c7deaa",
    "gatewayReferenceId": "809323430413", 
 }
} 
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/registration/v1/status' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
  "ssid" :  ["1c776e05188a0f27c"],   
   " deviceId": "8991000903658589244"
}'
```
{% endtab %}
{% endtabs %}
