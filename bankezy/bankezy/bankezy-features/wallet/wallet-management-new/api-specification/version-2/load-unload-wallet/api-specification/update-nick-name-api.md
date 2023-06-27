---
description: updates the nick name of Linked Account or card
---

# Update Nick Name Api



{% swagger method="post" path="" baseUrl="<domain>/orchestrate/nickname/update/api/v2" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="category" required="true" type="String" %}
Category(ac for accounts, lc for linked card)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nickName" required="true" type="String" %}
​Nick Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refId" required="true" type="String" %}
ref Id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" type="String" %}
​The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
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

{% swagger-response status="204: No Content" description="" %}
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

## Custom response codes

| Response Code | Response Description                  |
| ------------- | ------------------------------------- |
| ORC002        | Customer Id is Mandatory              |
| ​ORC022       | ​update nickname request is mandatory |
| ​ORC023       | category is mandatory                 |
| ORC024        | ​RefId is mandatory                   |
| ORC025        | ​nick name is mandatory               |
| ORC026        | Wallet service not responded..        |
| ORC020        | ​unsupported category :               |
| ORC027        | Account service not responded         |

{% tabs %}
{% tab title="Sample curl command" %}
​curl --location --request POST '[https://payment1.pcdev.enstage-sas.com/orchestrate/nickname/update/api/v1'](https://payment1.pcdev.enstage-sas.com/orchestrate/nickname/update/api/v1')

\\--header 'Content-Type: text/plain'

\\--header 'X-API-KEY: MOB-APP-2001'

\\--header 'X-API-TOKEN:token'

\--data-raw'{

&#x20; "nickName": "string",

&#x20; "refId": "string"

}'
{% endtab %}

{% tab title="Request sample" %}


```json
{
  "nickName": "string",
  "refId": "string"
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
