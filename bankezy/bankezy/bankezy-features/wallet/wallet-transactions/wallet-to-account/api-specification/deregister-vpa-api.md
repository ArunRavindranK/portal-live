---
description: >-
  This API can be used to deregister the customer from UPI ecosystem. Customers
  device binding, all VPAS, all accounts and their mappings will be deleted.
---

# Deregister VPA API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/registration//v1/deregister" summary="This API can be used to deregister the customer from UPI ecosystem" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" required="true" %}
Stringified JSON for udf parameters
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
| merchantId           | Unique id for the merchant as passed in request headers                    | String    | Length: 36 characters    |
| merchantChannelId    | Unique id for the merchant channel as passed in request headers            | String    | Length: 36 characters    |
| merchantCustomerId   | Merchant generated unique profile id for customer as passed in the request | String    | Length: 36 characters    |
| customerMobileNumber | Customer mobile number as per device binding                               | String    | 12 digits mobile number  |
| udfParameters        | Udf parameters as passed in the request                                    | String    |                          |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
    "udfParameter" : ""
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
    "customerMobileNumber": "918969453703"
  }
  "udfParameters": "{}"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'http://localhost:7060/upi-integration/upi/registration//v1/deregister' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
    "udfParameter" : ""
}'
```
{% endtab %}
{% endtabs %}
