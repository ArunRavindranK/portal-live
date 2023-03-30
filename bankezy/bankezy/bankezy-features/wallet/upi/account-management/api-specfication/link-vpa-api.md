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

{% swagger-parameter in="body" name="ssid" required="true" %}
Identifier of the SIM used to send the SMS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="true" %}
Unique identifier for the device
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

| Response Field                        | Field Description                              | Data Type | Length                   |
| ------------------------------------- | ---------------------------------------------- | --------- | ------------------------ |
| status                                | SUCCESS, FAILURE status of the API             | String    | Variable, 5–8 characters |
| <pre><code>description
</code></pre>  | <pre><code>description of status
</code></pre> | String    | Variable                 |
| <pre><code>vpa
</code></pre>          | primary vap                                    | String    | Length: 100              |
| <pre><code>bankUniqueId
</code></pre> | unique id for customer                         | String    | Length: 100              |

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
