---
description: This API deletes a customer VPA and its mapping to corresponding accounts.
---

# Delete VPA API



{% swagger method="post" path="" baseUrl="/upi-integration/upi/account/v1/deletevpa" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerVpa" required="true" %}
vpa entered by the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" %}
Stringified JSON for udf parameters
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Response

| Parameter Name | Description           |
| -------------- | --------------------- |
| resCode        | Response code         |
| resDesc        | Resposnse Description |
|                |                       |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
    "customerVpa" : "9620686057.bankezy@payu"  
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'http://localhost:7060/upi-integration/upi/account/v1/deletevpa' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
    "customerVpa" : "9620686057.bankezy@payu"
    
}'
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
    "resCode":"200",
    "resDesc":"VPA Deleted Successfully"
}
```
{% endtab %}
{% endtabs %}

