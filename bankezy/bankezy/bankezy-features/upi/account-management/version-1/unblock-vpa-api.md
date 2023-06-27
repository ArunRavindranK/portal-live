---
description: >-
  This API will be used to unblock a VPA which was blocked earlier by the
  customer.
---

# Unblock VPA API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/accountmanagement/v1/vpa/unblockvpa" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vpa" required="true" %}
Vpa that has to be Unblocked
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

<table><thead><tr><th width="259">Response Field</th><th>Field Description</th><th>Data Type</th></tr></thead><tbody><tr><td>resCode</td><td>SUCCESS, FAILURE status of the API</td><td>int</td></tr><tr><td>resDesc</td><td>Response message returned by the gateway for unblocking the VPA</td><td>String</td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Request" %}
```json
{
    "vpa":"9988776655.bankezy@payu"
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
    "resCode": 200,
    "resDesc": "Vpa unblocked successfull"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'http://localhost:7060/upi-integration/upi/accountmanagement/v1/vpa/unblockvpa' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
    "vpa":"9988776655.bankezy@payu"
}'
```
{% endtab %}
{% endtabs %}
