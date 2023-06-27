---
description: To fetch the bank linked cards
---

# Fetch Bank Linked cards API

{% swagger method="get" path="" baseUrl="<domain>/onboarding/bank/v2/fetchBankLinkedCards " summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../../../version-1/customer-on-boarding/common-apis/get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":{
      "cardList":[
         {
            "cardType":"Credit",
            "cardNumber":"682616819602",
            "cardExpiryMM":"11",
            "cardExpiryYYYY":"2021",
            "nameOnCard":"CustomerName",
            "nickName":"CustomerName",
            "cardUnion":"MASTERCARD",
            "cardAssociation":"M",
            "refNo":"10001",
            "addedSource":"",
            "bankName":"HDFC BANK",
            "bankId":"HDFC",
            "countryCode":"91",
            "onUs":0,
            "primary":false
         },
         {
            "cardType":"Debit",
            "cardNumber":"892551658984",
            "cardExpiryMM":"11",
            "cardExpiryYYYY":"2021",
            "nameOnCard":"CustomerName",
            "nickName":"CustomerName",
            "cardUnion":"VISA",
            "cardAssociation":"V",
            "refNo":"10002",
            "addedSource":"",
            "bankName":"HDFC BANK",
            "bankId":"HDFC",
            "countryCode":"91",
            "onUs":0,
            "primary":false
         }
      ]
   }
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
{% endswagger %}

## Response Details

| Response Field           | Field Description                            | Data Type | Length |
| ------------------------ | -------------------------------------------- | --------- | ------ |
| cardList.cardType        | type of card                                 | String    |        |
| cardList.cardNumber      | unique clear card number                     | String    |        |
| cardList.cardExpiryMM    | expiry month of the card                     | String    |        |
| cardList.cardExpiryYYYY  | expiry year of the card                      | String    |        |
| cardList.nameOnCard      | name of user on the card                     | String    |        |
| cardList.nickName        | nick name of the card                        | String    |        |
| cardList.cardUnion       | card network                                 | String    |        |
| cardList.cardAssociation | card network representation                  | String    |        |
| cardList.refNo           | id of the card saved in the db               | String    |        |
| cardList.addedSource     |                                              | String    |        |
| cardList.bankName        | name of the bank                             | String    |        |
| cardList.bankId          | short code of the bank name                  | String    |        |
| cardList.countryCode     | country code                                 | String    |        |
| cardList.onUs            | representrs how card added                   | Integer   |        |
| cardList.primary         | represents whether its a primary card or not | Boolean   |        |

{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location --request GET 'https://payment1.pcdev.enstage-sas.com/onboarding/bank/v2/fetchBankLinkedCards'
\--header 'Content-Type: text/plain'
\--header 'X-API-TOKEN:token'
\--header 'X-API-KEY:MOB-APP-2001'
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
   "resCode":"ONB200",
   "resDesc":"SUCCESS",
   "data":{
      "cardList":[
         {
            "cardType":"Credit",
            "cardNumber":"682616819602",
            "cardExpiryMM":"11",
            "cardExpiryYYYY":"2021",
            "nameOnCard":"CustomerName",
            "nickName":"CustomerName",
            "cardUnion":"MASTERCARD",
            "cardAssociation":"M",
            "refNo":"10001",
            "addedSource":"",
            "bankName":"HDFC BANK",
            "bankId":"HDFC",
            "countryCode":"91",
            "onUs":0,
            "primary":false
         },
         {
            "cardType":"Debit",
            "cardNumber":"892551658984",
            "cardExpiryMM":"11",
            "cardExpiryYYYY":"2021",
            "nameOnCard":"CustomerName",
            "nickName":"CustomerName",
            "cardUnion":"VISA",
            "cardAssociation":"V",
            "refNo":"10002",
            "addedSource":"",
            "bankName":"HDFC BANK",
            "bankId":"HDFC",
            "countryCode":"91",
            "onUs":0,
            "primary":false
         }
      ]
   }
}
```
{% endtab %}
{% endtabs %}
