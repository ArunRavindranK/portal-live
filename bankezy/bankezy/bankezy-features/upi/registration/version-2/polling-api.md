---
description: This API can be used to get the latest status VPA registration.
---

# Polling API

```
resDesc
```

{% swagger method="post" path="" baseUrl="/upi-integration/upi/registration/v2/polling" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refNumber" required="true" type="BigInteger" %}
Ref number received from device binding api
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

<table><thead><tr><th width="248">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td></td><td>String</td><td>Variable</td></tr><tr><td>resDesc</td><td></td><td>String</td><td></td></tr><tr><td>vpa</td><td></td><td>String</td><td></td></tr></tbody></table>

#### Response Code

|        |                                               |
| ------ | --------------------------------------------- |
| UPI12  | Successfully created VPA and linked account   |
| UPI501 | Device binding process declined due to fraud. |
| UPI502 | Device binding expired.                       |

## Response Details

<table><thead><tr><th width="248">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td></td><td>String</td><td>Variable</td></tr><tr><td>resDesc</td><td></td><td>String</td><td></td></tr><tr><td>vpa</td><td></td><td>String</td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Request" %}
```json
{
  "refNumber":"8900112233"
}
```
{% endtab %}

{% tab title="Sample Response" %}
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

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/registration/v2/polling' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
    "refNumber":"8900112233"
}'
```
{% endtab %}
{% endtabs %}
