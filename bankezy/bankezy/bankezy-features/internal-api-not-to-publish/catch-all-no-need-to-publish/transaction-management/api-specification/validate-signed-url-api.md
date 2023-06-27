---
description: The API can be used to validate signed url.
---

# Validate signed URL API



{% swagger method="post" path="upi-integration/upi/transaction/v1/validateUrl" baseUrl="" summary="Post scan to validate sign will use this url." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="url" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" type="String" %}

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

## Respdonse Details

<table><thead><tr><th width="257">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td></td><td>int</td><td></td></tr><tr><td>resDesc</td><td>SUCCESS, FAILURE status of the API</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>data</td><td>null</td><td>Obect</td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Request" %}
```json
{
    "url": "upi://pay?pa=test@mypsp&pn=3dqc8tkr2kb&tn=SignedIntentTesting&am=&mam=null&cu=INR&tr=UPITestHelper1&mode=00&orgid=158002&sign=MEUCIQDfuE08NavtqTAeOW+WBwDuFBUa83KGipzmyWeOOQZd8wIgFfRY6jwtty0WleXUT2Ir4jnfHpa59K4ZB8SVsd+R6JE=",
    "udfParameters": "{}"
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{    
"resCode": 200,
"resDesc": "SUCCESS",
"data": null
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/transaction/v1/validateUrl' \
--header 'X-ACCOUNT-NUMBER: 3110' \
--header 'X-PROGRAM-ID: 2001' \
--header 'Content-Type: application/json' \
--data-raw '{
    "url": "upi://pay?pa=test@mypsp&pn=3dqc8tkr2kb&tn=SignedIntentTesting&am=&mam=null&cu=INR&tr=UPITestHelper1&mode=00&orgid=158002&sign=MEUCIQDfuE08NavtqTAeOW+WBwDuFBUa83KGipzmyWeOOQZd8wIgFfRY6jwtty0WleXUT2Ir4jnfHpa59K4ZB8SVsd+R6JE=",
    "udfParameters": "{}"
}'
```
{% endtab %}
{% endtabs %}
