---
description: To fetch linkedCards information like card details, status, balance..
---

# Fetch LinkedCards API



{% swagger method="post" path="" baseUrl="<domain>/orchestrate/fetch/accounts/api/v2" summary="" %}
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

| ResponseCode | ResponseDesc                               |
| ------------ | ------------------------------------------ |
| ORC001       | fetch account request is mandatory         |
| ORC002       | Customer Id is mandatory                   |
| ORC003       | Account service not responded..            |
| ORC004       | Invalid Category                           |
| ORC200       | SUCCESS                                    |
| ORC005       | some thing went wrong.. try after sometime |

### Response Details

<table><thead><tr><th>Response Field</th><th width="229">Filed Desc</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>Response Code</td><td>String</td><td></td></tr><tr><td>resDesc</td><td>Response Description</td><td>String</td><td></td></tr><tr><td>id</td><td>ID</td><td>int</td><td></td></tr><tr><td>binId</td><td>Bin ID</td><td>int</td><td></td></tr><tr><td>customerId</td><td>Customer ID</td><td>String</td><td></td></tr><tr><td>cardNumber</td><td>CardNumber of Card linked</td><td>String</td><td></td></tr><tr><td>expiryYYYY</td><td>Expiry of card YYYY</td><td>String</td><td></td></tr><tr><td>nameoncard</td><td>Name of card</td><td>String</td><td></td></tr><tr><td>nickname</td><td>Nick Name</td><td>String</td><td></td></tr><tr><td>cardAddedSources</td><td>Card added Source</td><td>String</td><td></td></tr><tr><td>cvv2</td><td>cvv of card Number</td><td>String</td><td></td></tr><tr><td>status</td><td>status of card</td><td>int</td><td></td></tr><tr><td>primary</td><td>Primary</td><td>boolean</td><td></td></tr><tr><td>cardType</td><td>Card Type</td><td>String</td><td></td></tr><tr><td>cardUnion</td><td>card Union</td><td>String</td><td></td></tr><tr><td>bankName</td><td>Bank Name</td><td>String</td><td></td></tr><tr><td>cardassociation</td><td>card Association</td><td>String</td><td></td></tr><tr><td>onUs</td><td></td><td>int</td><td></td></tr><tr><td>cardAddedDate</td><td>Date on which card added</td><td>Timestamp</td><td></td></tr><tr><td>cardupdateddate</td><td>Date on which card updated</td><td>Timestamp</td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/orchestrate/fetch/accounts/api/v2'
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
  "resCode": "ORC200",
  "resDesc": "Success",
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
