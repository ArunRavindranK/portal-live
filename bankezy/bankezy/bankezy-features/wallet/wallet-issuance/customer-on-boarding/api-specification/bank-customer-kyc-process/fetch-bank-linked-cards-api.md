---
description: To fetch the bank linked cards
---

# Fetch Bank Linked cards API

{% swagger method="get" path="" baseUrl="<domain>/onboarding/bank/fetchBankLinkedCards/v1 " summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the

[login API](../authentication-and-authorization/login-api.md)

or

[Get Token API](../../common-apis/get-app-token-api.md)
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

{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location --request GET 'https://payment1.pcdev.enstage-sas.com/onboarding/bank/fetchBankLinkedCards/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-TOKEN:token'
\--header 'X-API-KEY:MOB-APP-2001'
```
{% endtab %}

{% tab title="Response sample" %}
```json
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
{% endtab %}
{% endtabs %}
