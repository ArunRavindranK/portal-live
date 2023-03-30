---
description: This API is used to verify the Aadhar number.
---

# Aadhaar Verify Number API

{% swagger method="post" path="" baseUrl="http://192.168.105.70:8083/onboarding/ekyc/v1/aadhaar/verify/number" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="aadhaarNumber" required="true" %}
User Aadhar number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userName" required="true" %}
User Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="emailId" required="true" %}
User email id
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
{% tab title="Request" %}
```json
{
    "aadhaarNumber" : "999643198087",
    "userName" : "Bal krisna mahto",
    "emailId" : "bablu.krishana123@gmail.com"
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "resCode": 200,
    "resDesc": "Success",
    "data": {
        "traceId": "d3b146bb-494f-42ea-94d1-0770a5db1437"
    }
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'http://192.168.105.70:8083/onboarding/ekyc/v1/aadhaar/verify/number' \
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: application/json'
--data-raw '{
    "aadhaarNumber" : "999643198087",
    "userName" : "Bal krisna mahto",
    "emailId" : "bablu.krishana123@gmail.com"
}'
```
{% endtab %}
{% endtabs %}
