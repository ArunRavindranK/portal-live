---
description: Update NickName on selected linked card
---

# Update NickName API

{% swagger method="post" path="" baseUrl="<domain>/orchestrate/nickname/update/api/v2" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" type="String" %}
​The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardRefId" type="Int" required="true" %}
​Card RefId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nickName" type="String" required="true" %}
Nick Name
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="201: Created" description="" %}
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

{% swagger-response status="403: Forbidden" description="" %}
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

## Custom response codes

| Code    | Description                              |
| ------- | ---------------------------------------- |
| ORC002  | customer id is empty                     |
| ORC025  | nick name is mandatory                   |
| ​ORC021 | ​Card is blocked for online transactions |

### Response Details

<table><thead><tr><th width="140">Response Field</th><th>Field Desc</th><th>Data Type</th><th>length</th></tr></thead><tbody><tr><td>rescode</td><td></td><td>String</td><td></td></tr><tr><td>resdesc</td><td>SUCCESS, FAILURE status of the API</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td></td><td></td><td></td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/orchestrate/nickname/update/api/v2'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:replace_with_basic_auth_to_be_built_by_client' --data-raw '{ "refId": 195,
  "nickName": "Abhinav",
  "category":"wc" }'​
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "refId": 195,
  "nickName": "Abhinav",
  "category":"wc"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": "ORC200",
  "resDesc": "Success"
}
```
{% endtab %}
{% endtabs %}
