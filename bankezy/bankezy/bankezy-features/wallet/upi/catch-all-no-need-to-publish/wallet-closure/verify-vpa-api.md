---
description: >-
  This api checks the availability of the VPA and also provides suggestion if
  the vpa is not available.
---

# Verify VPA API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/transaction/v1/verifyVpa" summary="This api checks the availability of the VPA and also provides suggestion if the vpa is not available" %}
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

| Response Field       | Field Description                                                          | Data Type | Length                   |
| -------------------- | -------------------------------------------------------------------------- | --------- | ------------------------ |
| status               | SUCCESS, FAILURE status of the API                                         | String    | Variable, 5–8 characters |
| merchantId           | Unique id for the merchant as passed in request headers                    | String    | Variable, 5–8 characters |
| merchantChannelId    | Unique id for the merchant channel as passed in request headers            | String    | Length: 36 characters    |
| merchantCustomerId   | Merchant generated unique profile id for customer as passed in the request | String    | Length: 36 characters    |
| customerMobileNumber | Customer mobile number                                                     | String    | 12 digits mobile number  |
| udfParameters        | Udf parameters as passed in the request                                    | String    | Variable, 5–8 characters |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
 "vpa":"7914717873@payu",
 "udfParameters":""
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
    "available" : "true"/"false",
    "vpaSuggestions" : ["qwert@abcd",...]
  },
  "udfParameters": "{}"
}
```
{% endtab %}

{% tab title="Sample Curl Command " %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/transaction/v1/verifyVpa' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
 "vpa":"7914717873@payu",
 "udfParameters":"{}"
 }'
```
{% endtab %}
{% endtabs %}
