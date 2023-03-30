---
description: >-
  This callback will be sent to merchant when the PSP receives a confirmation
  from the VMN aggregator on the customer mobile number and sms token.
---

# Device Status  Call Back API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/callback/v1/device/status" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
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

| Response Field | Field Description                  | Data Type | Length                   |
| -------------- | ---------------------------------- | --------- | ------------------------ |
| Status         | SUCCESS, FAILURE status of the API | String    | Variable, 5–8 characters |

{% tabs %}
{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi/callback/v1/device/status' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
```
{% endtab %}
{% endtabs %}

