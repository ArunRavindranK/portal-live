---
description: To link Debit/Credit card into BankEzy App to further use on payments
---

# Link-Card API



{% swagger method="post" path="" baseUrl="<domain>/wallet/lc/link/api/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accounts" type="JSON" required="true" %}
Accounts
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accounts" type="String" required="true" %}
Accounts
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accountNumber" type="String" required="true" %}
Account Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accountType" type="String" required="true" %}
​Account Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankName" type="String" required="true" %}
Bank Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="branch" type="String" required="true" %}
Branch
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ifscCode" type="String" required="true" %}
​IFSCCode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nickName" type="String" required="true" %}
​Nick Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pin" type="Boolean" required="true" %}
Pin
{% endswagger-parameter %}

{% swagger-parameter in="body" name="primary" type="Boolean" required="true" %}
Primary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vpa" type="String" required="true" %}
vpa
{% endswagger-parameter %}

{% swagger-parameter in="body" name="category" type="String" required="true" %}
Category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="linkedCardInfo" type="JSON" required="true" %}
LinkedCard Info
{% endswagger-parameter %}

{% swagger-parameter in="body" name="addedSource" type="String" required="true" %}
Added Source
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankName" type="String" required="true" %}
Bank Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardAssociation" type="String" required="true" %}
​CardAssociation
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardExpiryMM" type="String" required="true" %}
CardExpiryMM
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardExpiryYYYY" type="String" required="true" %}
Card ExpiryYYYY
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardNumber" type="String" required="true" %}
Card Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardType" type="String" required="true" %}
​Card Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardUnion" type="String" required="true" %}
Card Union
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" type="String" required="true" %}
CountryCode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nameOnCard" type="String" required="true" %}
NameOnCard
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nickName" type="String" required="true" %}
NickName
{% endswagger-parameter %}

{% swagger-parameter in="body" name="onUs" type="Int" required="true" %}
onUs
{% endswagger-parameter %}

{% swagger-parameter in="body" name="primary" type="Boolean" required="true" %}
Primary
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

| Code | Description                                  |
| ---- | -------------------------------------------- |
| 1    | ​card linked successfully                    |
| 2    | payment card type api response failed        |
| 20   | request is empty                             |
| 57   | ​linked card info is empty                   |
| 58   | card number is empty                         |
| 59   | card expiry mm is empty                      |
| 60   | card expiry yyyy is empty                    |
| 61   | name on card is empty                        |
| 62   | ​card expiry year is less than current year  |
| 63   | card expiry month is less than current month |
| 64   | card added source is empty                   |

| <p><br></p> |
| ----------- |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/lc/link/api/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw '{"accounts":{"accountName":"Abhinav","accountNumber":"0041487199714541","accountType":"SA","bankName":"HDFC","branch":"MG Road","ifscCode":"HDFC00087","nickName":"Abhi","pin":true,"primary":true,"vpa":"8892239811@bankezy"},"category":"lc","linkedCardInfo":{"addedSource":"SELF","bankName":"HDFC","cardAssociation":"string","cardExpiryMM":"01","cardExpiryYYYY":"2024","cardNumber":"4329092197757365","cardType":"string","cardUnion":"string","countryCode":"91","nameOnCard":"Abhinav","nickName":"Abhi","onUs":0,"primary":true},"mobile":"8892239811"}'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}


```json
{
  "accounts": {
    "accountName": "Abhinav",
    "accountNumber": "0041487199714541",
    "accountType": "SA",
    "bankName": "HDFC",
    "branch": "MG Road",
    "ifscCode": "HDFC00087",
    "nickName": "Abhi",
    "pin": true,
    "primary": true,
    "vpa": "8892239811@bankezy"
  },
  "category": "lc",
  "linkedCardInfo": {
    "addedSource": "SELF",
    "bankName": "HDFC",
    "cardAssociation": "string",
    "cardExpiryMM": "01",
    "cardExpiryYYYY": "2024",
    "cardNumber": "4329092197757365",
    "cardType": "string",
    "cardUnion": "string",
    "countryCode": "91",
    "nameOnCard": "Abhinav",
    "nickName": "Abhi",
    "onUs": 0,
    "primary": true
  },
  "mobile": "8892239811"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 1,
  "resDesc": "card linked successfully"
}
```
{% endtab %}
{% endtabs %}
