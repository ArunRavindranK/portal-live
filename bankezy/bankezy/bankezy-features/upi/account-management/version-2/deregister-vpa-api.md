---
description: >-
  This API can be used to deregister the customer from UPI ecosystem. Customers
  device binding, all VPAS, all accounts and their mappings will be deleted.
---

# Deregister VPA API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/registration/v2/deregister" summary="This API can be used to deregister the customer from UPI ecosystem" %}
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

| ResponseCode | ResponseDesc                             |
| ------------ | ---------------------------------------- |
| UPI120       | Server error. Please try after some time |
| UPI14        | UPI is successfully de-registered!       |
| UPI15        | No VPA Details present for customer      |
| UPI16        | UPI Deregistered Failed                  |

## Response Details

| Response Field | Field Description                           | Data Type | Length                 |
| -------------- | ------------------------------------------- | --------- | ---------------------- |
| resCode        | Success or failure in number representation | int       | 3 digits response code |
| resDesc        | description of the response code            | String    |                        |



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
  "resCode": UPI14,
  "resDesc": "UPI is successfully de-registered!"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location 'http://localhost:7060/upi-integration/upi/registration/v1/deregister' \
--header 'X-API-TOKEN:  replace-with-actual-token' \
--header 'X-API-KEY:  MOB-APP-2001' \
--header 'Content-Type: application/json' \
--data '{
    "udfParameter" : ""
}'
```
{% endtab %}
{% endtabs %}
