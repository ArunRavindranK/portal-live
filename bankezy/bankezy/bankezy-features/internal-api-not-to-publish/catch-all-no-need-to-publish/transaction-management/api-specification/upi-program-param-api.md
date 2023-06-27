---
description: The API can be invoked to fetch program param value.
---

# UPI Program Param API

resCode

{% swagger method="put" path="/upi-integration/upi/internal/programParamByName" baseUrl="" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
program id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="PROG-PARAM-NAME" required="true" %}
Program param to fetch Value
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

<table><thead><tr><th width="257">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>Response code</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>resDesc</td><td>Response code description</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>data</td><td>Value of program para key</td><td>String</td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Request" %}
```json
{

}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
  {
  "resCode": "200",
  "resDesc": "SUCCESS"
  "data" : "Test Value"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/internal/programParamByName' \
\--header 'X-PROGRAM-ID: 2001'
\--header 'PROG-PARAM-NAME: RT_TIME_OUT'
--data-raw '{

}'
```
{% endtab %}
{% endtabs %}
