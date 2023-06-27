---
description: >-
  This API is to be used for declining the device binding in case of an app
  toggle by customer.
---

# Decline Device Binding API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/registration/v2/decline/deviceBinding" summary="" %}
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

#### Response Details

<table><thead><tr><th width="257">Response Field</th><th>Field Description</th><th>Data Type</th></tr></thead><tbody><tr><td>resCode</td><td>Response code</td><td>String</td></tr><tr><td>resDesc</td><td>Response Description</td><td>String</td></tr></tbody></table>

#### Response Code

|        |         |
| ------ | ------- |
| UPI200 | SUCCESS |
| UPI100 | FAILURE |
|        |         |

## Response Details

<table><thead><tr><th width="257">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td></td><td>String</td><td></td></tr><tr><td>resDesc</td><td></td><td>String</td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Request" %}
```json
{
    "smsContent" : "UPIACT ad56ef90396348bac56099"
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS"
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
    "smsContent" : "UPIACT ad56ef90396348bac56099"
}'
```
{% endtab %}
{% endtabs %}
