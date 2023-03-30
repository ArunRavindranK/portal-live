---
description: >-
  Update Service Type (E-com), it's a user driven flag, user can enable/disable
  Ecom transactions in App. If this flag is disabled user will not be allowed
  for merchant transactions
---

# Update Service type(e-com)

{% swagger method="post" path="" baseUrl="<domain>/wallet/update/servicetype/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" type="String" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="service" type="JSON" required="true" %}
​Service
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="Boolean" required="true" %}
Status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" type="String" required="true" %}
Type(Ex: E-com)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" type="Int" required="true" %}
Wallet Id (wallet unique ref #)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="false" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="201: Created" description="" %}
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

{% swagger-response status="403: Forbidden" description="" %}
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

## Custom error codes

| Error code | Description           |
| ---------- | --------------------- |
| 300        | Service is empty      |
| 301        | Service type is empty |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/update/servicetype/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw '{ "service": { "status": true, "type": "e-Com" }, "walletId": 1 }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "service": {
    "status": true,
    "type": "e-Com"
  },
  "walletId": 1
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "BankEzy Wallet xxxx 7653 has been active",
  "data": true
}
```
{% endtab %}
{% endtabs %}
