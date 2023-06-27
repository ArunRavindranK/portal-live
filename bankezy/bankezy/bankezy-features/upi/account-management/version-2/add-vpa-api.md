---
description: >-
  This API creates an alias to an existing vpa. All the accounts liked to
  customerPrimaryVpa will be linked to customerVpa
---

# Add VPA API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/account/v2/addvpa" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerVpa" required="true" %}
user entered vpa
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deleteCustomerPrimaryVpa" type="boolean" required="false" %}
delete primary account
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" %}
json string
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
| UPI29        | MAX\_COUNT\_EXCEEDED                     |
| UPI120       | Server error. Please try after some time |
| UPI125       | VPA Added Successfully                   |
| UPI127       | VPA not Available                        |
| UPI128       | VPA addition Failed                      |
| UPI126       | Add VPA Juspay Call failure              |

## Response Details

{% tabs %}
{% tab title="Sample Request" %}
```json
{
    "customerVpa":"kumudha.citrus@payu"
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
  "resCode": UPI125,
  "resDesc": "VPA Added Successfully"
}


```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location 'http://localhost:7060/upi-integration/upi/account/v1/addvpa' \
--header 'X-API-TOKEN:  replace-with-actual-token' \
--header 'X-API-KEY:  MOB-APP-2001' \
--header 'Content-Type: application/json' \
--data-raw '{
    "customerVpa":"kumudha.citrus@payu"
}'
```
{% endtab %}
{% endtabs %}
