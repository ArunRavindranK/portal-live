---
description: This API can be used to link VPA to given mobile number.
---

# Link VPA API



{% swagger method="post" path="" baseUrl="/upi-integration/upi/registration/v1/link/vpa" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobileNumber" required="true" %}
12 digit mobile number with country code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParams" required="false" %}
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

<table><thead><tr><th width="248">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>status</td><td>SUCCESS, FAILURE status of the API</td><td>String </td><td>Variable, 5–8 characters</td></tr><tr><td><pre><code>description
</code></pre></td><td><pre><code>description of status
</code></pre></td><td>String</td><td>Variable</td></tr><tr><td><pre><code>vpa
</code></pre></td><td>primary vap </td><td>String</td><td>Length: 100</td></tr><tr><td><pre><code>bankUniqueId
</code></pre></td><td>unique id for customer</td><td>String </td><td>Length: 100</td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Request" %}
```json
{
  "mobileNumber":"8900112233",
  "udfParams":"{}"
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
  "status": "SUCCESS",
  "resCode": "200",
  "resDesc": "SUCCESS",
  "data": {
    "status":"VERIFIED",
    "description":"",
    "vpa":"99911199.citrus@payu",
    "bankUniqueId":"bmnbhj654gjd76a76et3qbhje"
    }
} 
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/registration/v1/link/vpa' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
  "mobileNumber":"8900112233",
  "udfParams":"{}"
}'
```
{% endtab %}
{% endtabs %}
