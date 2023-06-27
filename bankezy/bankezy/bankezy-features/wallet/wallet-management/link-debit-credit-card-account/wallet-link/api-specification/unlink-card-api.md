---
description: 'Un-linkAccount: delete the linked card in App'
---

# Unlink Card API



{% swagger method="post" path="" baseUrl="<domain>/wallet/lc/unlink/api/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login APIcategory
{% endswagger-parameter %}

{% swagger-parameter in="body" name="category" type="String" required="true" %}
​category(ac for accounts, lc for liked cards)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="Int" required="true" %}
id
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
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/lc/unlink/api/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw '{ "category": "lc", "id": 195 }'​
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "category": "lc",
  "id": 195
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 1,
  "resDesc": "Card un-linked successfully"
}
```
{% endtab %}
{% endtabs %}
