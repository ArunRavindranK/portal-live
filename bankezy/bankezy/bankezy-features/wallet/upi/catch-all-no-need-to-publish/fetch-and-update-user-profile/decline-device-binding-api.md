---
description: >-
  This API is to be used for declining the device binding in case of an app
  toggle by customer.
---

# Decline Device Binding API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/registration/v1/decline/deviceBinding" summary="" %}
{% swagger-description %}
This API is to be used for declining the device binding in case of an app toggle by customer
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" required="true" %}
Stringified JSON for udf parameters
{% endswagger-parameter %}

{% swagger-parameter in="body" name="smsContent" required="true" %}
SMS content to be used for device binding for this token
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

| Response Field         | Field Description                                                          | Data Type      | Length                   |
| ---------------------- | -------------------------------------------------------------------------- | -------------- | ------------------------ |
| Status                 | SUCCESS, FAILURE status of the API                                         | String         | Variable, 5–8 characters |
| merchantId             | Unique id for the merchant as passed in request headers                    | String         | Variable, 5–8 characters |
| merchantChannelId      | Unique id for the merchant channel as passed in request headers            | String         | Length: 36 characters    |
| merchantCustomerId     | Merchant generated unique profile id for customer as passed in the request | String         | Length: 36 characters    |
| gatewayResponseCode    | Response code for device binding                                           | Boolean string | Variable, 5–8 characters |
| gatewayResponseMessage | Response message for device binding                                        | Boolean string | Variable, 5–8 characters |
| udfParameters          | Udf parameters as passed in the request                                    |                |                          |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
    "udfParameters" : "",
    "smsContent" : "UPIACT ad56ef90396348bac56099"
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
    "gatewayResponseCode": "JP19",
    "gatewayResponseMessage": "Device binding declined"
  },
  "udfParameters": "{}"
}

```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/registration/v1/decline/deviceBinding' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
    "udfParameters" : "{}",
    "smsContent" : "UPIACT ad56ef90396348bac56099"
}'
```
{% endtab %}
{% endtabs %}
