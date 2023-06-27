---
description: To fetch linkedCards information like card details, status, balance..
---

# Fetch LinkedCards API



{% swagger method="post" path="" baseUrl="<domain>/wallet/lc/fetch/api/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="Int" required="true" %}
​ID( card ref #)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lcGrouping" type="Boolean" required="true" %}
lc Grouping
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
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/lc/fetch/api/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:replace_with_basic_auth_to_be_built_by_client' --data-raw '{ "id": 1, "lcGrouping": true }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "id": 1,
  "lcGrouping": true
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "User Linked cards fetched Successfully",
  "data": {
    "Credit": [
      {
        "id": 287,
        "binId": 72,
        "customerId": "2022",
        "cardNumber": "4329xxxxxxxx1280",
        "expiryMm": "02",
        "expiryYyyy": "2024",
        "nameOnCard": "AbhinavAradhya",
        "nickName": "Abhinav",
        "cardAddedSource": "SELF",
        "cvv2": null,
        "status": 1,
        "primary": false,
        "cardType": "Credit",
        "cardUnion": "",
        "bankName": "HDFC",
        "cardAssociation": "V",
        "onUs": 0,
        "cardAddedDate": "2022-07-19T07:18:51.000+00:00",
        "cardUpdatedDate": null
      },
      {
        "id": 288,
        "binId": 1,
        "customerId": "2022",
        "cardNumber": "4329xxxxxxxx4124",
        "expiryMm": "01",
        "expiryYyyy": "2024",
        "nameOnCard": "AbhinavAradhya",
        "nickName": "Abhinav",
        "cardAddedSource": "SELF",
        "cvv2": null,
        "status": 1,
        "primary": false,
        "cardType": "Credit",
        "cardUnion": "Visa",
        "bankName": "HDFC",
        "cardAssociation": "V",
        "onUs": 0,
        "cardAddedDate": "2022-07-20T13:23:04.000+00:00",
        "cardUpdatedDate": null
      },
      {
        "id": 289,
        "binId": 1,
        "customerId": "2022",
        "cardNumber": "4329xxxxxxxx0538",
        "expiryMm": "01",
        "expiryYyyy": "2024",
        "nameOnCard": "AbhinavAradhya",
        "nickName": "Abhinav",
        "cardAddedSource": "SELF",
        "cvv2": null,
        "status": 1,
        "primary": false,
        "cardType": "Credit",
        "cardUnion": "Visa",
        "bankName": "HDFC",
        "cardAssociation": "V",
        "onUs": 0,
        "cardAddedDate": "2022-07-20T13:33:32.000+00:00",
        "cardUpdatedDate": null
      }
    ]
  }
}
```
{% endtab %}
{% endtabs %}
