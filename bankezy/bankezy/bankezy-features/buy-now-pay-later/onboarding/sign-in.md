---
description: >-
  This API validate mobile and provide updated token with user account details,
  subsequently token will be used along with API calls in x-api-token header.
---

# Sign In

{% swagger method="post" path="lending/v1/token" baseUrl="<domain>" summary="" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
The token got from the 

[Get Token API](../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="token" type="String" required="true" %}
The token got from the 

[Get Token API](../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" type="String" required="true" %}
User mobile number
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
<pre><code>curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/token' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: &#x3C;REPLACE_WITH_TOKEN_FROM_GET_TOKEN_API_RESPONSE>' \
<strong>--data-raw '{
</strong>  "token": "&#x3C;REPLACE_WITH_TOKEN_FROM_GET_TOKEN_API_RESPONSE>",
  "mobile": "9999097535",
}'
</code></pre>
{% endtab %}

{% tab title="Request Example" %}
```json
{ 
    "token": "<REPLACE_WITH_TOKEN_FROM_GET_TOKEN_API_RESPONSE>", 
    "mobile": "9999097535" 
}
```


{% endtab %}

{% tab title="Response Example" %}
```json
{ 
"resCode": 200, 
"resDesc": "SUCCESS",
"data": {
    "resCode": 100, 
    "resDesc": "Success", 
    "token": "Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJMT0dJTl9VU0VSIiwiVE9LRU5fRVhQSVJZIjo5MDAsIlJFRkVSRU5DRV9JRCI6ImIzNzhkODkxLTQyNGMtNDczNy05OGExLThmM2JlMmU3YzcyMyIsIkFMTE9XRURfSVBTIjoiKiIsIlgtUFJPR1JBTS1JRCI6MTExMSwiaXNzIjoiaVRKMFRsbTFrVVdvSmFaTkd5YWFpR2ljWEt6WE1CNXAiLCJYLUFDQ09VTlQtTlVNQkVSIjoyODQxLCJleHAiOjE2NzAyMzE5MzcsIlBST0dSQU1fSUQiOjExMTEsImlhdCI6MTY3MDIzMTAzN30.KH0trvXrmxPuIzWq_6PAYsdBm3F7DZ1C6-rO9kjuw6u8binAQ4aRbbmh1V9WvSUkjIyx9eznbuoj9TGp0LWeGA", "expiry": 1670231937663 
 } 

```
{% endtab %}
{% endtabs %}

