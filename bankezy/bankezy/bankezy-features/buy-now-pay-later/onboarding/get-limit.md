---
description: >-
  This API is used for setting BNPL limit after success full user information
  confirmation. API internally invoke Bureau, underwrite and finally provide an
  amount can be set as a limit.
---

# Get Limit



{% swagger method="post" path="/lending/v1/onboard/limit" baseUrl="<domain>" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
The token got from the 

[Get Token API](../../market-place/api-specification/version-1/get-token-api.md)


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
{% tab title="Sample Curl Request" %}
<pre><code>curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/onboard/limit' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: &#x3C;REPLACE_WITH_TOKEN_FROM_GET_TOKEN_API_RESPONSE>' \
<strong>--data-raw '{
</strong>}'
</code></pre>
{% endtab %}

{% tab title="Request Example" %}
```json
{
}
```


{% endtab %}

{% tab title="Response Example" %}
```json
{ 
 "resCode": 200, 
 "resDesc": "SUCCESS", 
 "data": { 
  "assignedLimit": 12500.0 
 } 

```
{% endtab %}
{% endtabs %}

### Response Details

| Response Body | Data Type | Field Description    |
| ------------- | --------- | -------------------- |
| resCode       | String    | Response Code        |
| resDesc       | String    | Response Description |
| assignedLimit | Integer   | Limit Assigned       |

### Custom Response Codes

| Response Codes | Response Description                                  |
| -------------- | ----------------------------------------------------- |
| LND022         | User account doesnt exist                             |
| LND200         | SUCCESS                                               |
| LND002         | ONBOARD                                               |
| LND009         | There seems to be a technical issue. Try again later. |
| LND023         | BUREAU FAILED                                         |
