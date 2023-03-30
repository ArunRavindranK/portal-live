---
description: This API is used for setting BNPL limit after bureau policy execution.
---

# Get Limit



{% swagger method="post" path="" baseUrl="/lending/v1/onboard/limit" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
The token got from the 

[Get Token API](../../market-place/api-specification/get-token-api.md)


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
