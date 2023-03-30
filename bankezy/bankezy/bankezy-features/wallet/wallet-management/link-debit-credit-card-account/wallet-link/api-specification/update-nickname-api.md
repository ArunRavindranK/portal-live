---
description: Update NickName on selected linked card
---

# Update NickName API

{% swagger method="post" path="" baseUrl="<domain>/wallet/lc/nickname/api/v1" summary="" %}
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

| Code | Description             |
| ---- | ----------------------- |
| 26   | customer id is empty    |
| 65   | user nick name is empty |
| ​66  | ​card id is empty       |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/lc/nickname/api/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:replace_with_basic_auth_to_be_built_by_client' --data-raw '{ "cardRefId": 195, "nickName": "Abhinav" }'​
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "cardRefId": 195,
  "nickName": "Abhinav"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "user nickname updated successfully"
}
```
{% endtab %}
{% endtabs %}
