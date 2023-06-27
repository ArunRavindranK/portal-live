---
description: Fetch the accounts for the customer
---

# Fetch Accounts API



{% swagger method="post" path="" baseUrl="<domain>/orchestrate/fetch/accounts/api/v2" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="category" type="String" required="true" %}
Category(ex: ac for accounts ,lc for linked cards
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="String" required="true" %}
ID (card ref #)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lcGrouping" type="String" required="true" %}
Linked card grouping. Accepts true or false. True  returns Map (key: cardType: value : list of cards). False returns list of cards
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
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

| Response Code | Response Description                |
| ------------- | ----------------------------------- |
| ORC002        | Customer Id is Mandatory            |
| ORC001        | ​fetch account request is mandatory |
| ​ORC003       | Account service not responded..     |
| ORC004        | Invalid Category                    |

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST '
https://payment1.pcdev.enstage-sas.com/orchestrate/fetch/accounts/api/v2'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:replace_with_basic_auth_to_be_built_by_client'
--data-raw'{ "category": "wc", "customerId": "29", "id": 13, "lcGrouping": "true", "mobile": "8892239811" }'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "category": "wc",
  "customerId": "29",
  "id": 13,
  "lcGrouping": "true",
  "mobile": "1420200001"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": "ORC200",
  "resDesc": "Account(s) fetched Successfully",
  "data": {
    "accounts": null,
    "linkedCards": null,
    "wallets": [
      {
        "customerId": "29",
        "name": "Nithya Kaimal",
        "walletId": 80,
        "mobile": "1420200001",
        "cardNumber": "4123480369026362",
        "cardExpiry": "092021",
        "balance": 1000000,
        "walletStatus": "Active",
        "productType": "OT",
        "kycLevel": 150,
        "txnProfile": [
          {
            "status": true,
            "type": "e-Com"
          }
        ]
      },
      {
        "customerId": "29",
        "name": "Naveen MN LN",
        "walletId": 13,
        "mobile": "1420200001",
        "cardNumber": "4895110034672441",
        "cardExpiry": "022026",
        "balance": 964416,
        "walletStatus": "Active",
        "productType": "RW",
        "kycLevel": 30,
        "txnProfile": [
          {
            "status": true,
            "type": "e-Com"
          }
        ]
      }
    ],
    "listOfCards": null
  }
}
```
{% endtab %}
{% endtabs %}
