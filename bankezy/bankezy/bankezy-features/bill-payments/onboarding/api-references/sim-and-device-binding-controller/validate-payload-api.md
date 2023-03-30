---
description: This API is used to validate the API.
---

# Validate PayLoad API

{% swagger method="post" path="" baseUrl="http://192.168.105.70:8083/onboarding/user/auth/validatePayLoad/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
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
    "smsbody" : "",
    "senderNumber" : "7827737375",
    "longcode" : "848130",
    "circleid" : "",
    "carrierid" : "",
    "keyword" : "",
    "subkeyword" : "",
    "timestamp" : ""
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "context": {
        "headers": {},
        "entity": null,
        "entityType": null,
        "entityAnnotations": [],
        "entityStream": {
            "closed": false,
            "committed": false
        },
        "lastModified": null,
        "date": null,
        "length": -1,
        "location": null,
        "language": null,
        "mediaType": null,
        "entityClass": null,
        "responseCookies": {},
        "acceptableLanguages": [
            "*"
        ],
        "requestCookies": {},
        "allowedMethods": [],
        "entityTag": null,
        "links": [],
        "stringHeaders": {},
        "committed": false,
        "acceptableMediaTypes": [
            {
                "type": "*",
                "subtype": "*",
                "parameters": {},
                "quality": 1000,
                "wildcardType": true,
                "wildcardSubtype": true
            }
        ]
    },
    "status": 200,
    "lastModified": null,
    "date": null,
    "length": -1,
    "location": null,
    "language": null,
    "mediaType": null,
    "allowedMethods": [],
    "entityTag": null,
    "links": [],
    "stringHeaders": {},
    "metadata": {},
    "statusInfo": "OK",
    "cookies": {},
    "entity": null,
    "headers": {}
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'http://192.168.105.70:8083/onboarding/user/auth/validatePayLoad/v1' \
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'Content-Type: application/json'
--data-raw '{
    "smsbody" : "",
    "senderNumber" : "7827737375",
    "longcode" : "848130",
    "circleid" : "",
    "carrierid" : "",
    "keyword" : "",
    "subkeyword" : "",
    "timestamp" : ""
}'
```
{% endtab %}
{% endtabs %}
