---
description: This API is used to check the status of vpa
---

# VPA Polling API

{% swagger method="post" path="" baseUrl="<domain>/upi-integration/upi/registration/v1/polling" summary="receives programId and account numbers from headers and fetch the status of vpa for that account number" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
token
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refNumber" required="true" %}
Account Number
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
{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://${domain_name}/upi-integration/upi/registration/v1/polling' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=268743CC4FCDD918A01893968C83A481' \
--data-raw '{
    "refNumber" : "3"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "refNumber" : "3"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": "503",
  "resDesc": "Successfully created VPA and linked account",
  "data": {
    "vpa": "XXXXXXXXXX.bankezyX@payu"
  }
}
```
{% endtab %}
{% endtabs %}
