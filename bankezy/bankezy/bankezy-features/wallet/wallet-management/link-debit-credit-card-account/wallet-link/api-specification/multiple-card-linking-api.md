---
description: This API allows to link multiple cards passed.
---

# Multiple card linking API

{% swagger method="post" path="" baseUrl="<domain>/wallet/lc/autoLinkCard/api/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
​The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="category" type="String" required="true" %}
category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="linkedCardInfo" type="JSON" required="true" %}
Linked CardInfo
{% endswagger-parameter %}

{% swagger-parameter in="body" name="addedSource" type="String" required="true" %}
Added Source
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankName" type="String" required="true" %}
Bank Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardAssociation" type="String" required="true" %}
​Card Association
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardExpiryMM" type="String" required="true" %}
Card ExpiryMM
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardExpiryYYYY" type="String" required="true" %}
Card ExpiryYYYY
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardNumber" type="String" required="true" %}
Card Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardType" type="String" required="true" %}
Card Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardUnion" type="String" required="true" %}
Card Union
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" type="String" required="true" %}
Country Code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nameOnCard" type="String" required="true" %}
Name On Card
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nickName" type="String" required="true" %}
Nick Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="onUs" type="Int" required="true" %}
onUs
{% endswagger-parameter %}

{% swagger-parameter in="body" name="primary" type="True" required="true" %}
​Primary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" type="String" required="true" %}
Mobile
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

## Custom response codes

| Response code | Response description                  |
| ------------- | ------------------------------------- |
| 1             | card linked successfully              |
| 2             | payment card type api response failed |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/lc/autoLinkCard/api/v1' 
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:replace_with_basic_auth_to_be_built_by_client' --data-raw '{"category":"lc","linkedCardInfo":[{"addedSource":"SELF","bankName":"HDFC","cardAssociation":"V","cardExpiryMM":"01","cardExpiryYYYY":"2024","cardNumber":"4329092197757365","cardType":"string","cardUnion":"VISA","countryCode":"string","nameOnCard":"AbhinavAradhya","nickName":"Abhinav","onUs":0,"primary":true}],"mobile":"8892239811"}'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "category": "lc",
  "linkedCardInfo": [
    {
      "addedSource": "SELF",
      "bankName": "HDFC",
      "cardAssociation": "V",
      "cardExpiryMM": "01",
      "cardExpiryYYYY": "2024",
      "cardNumber": "4329092197757365",
      "cardType": "string",
      "cardUnion": "VISA",
      "countryCode": "string",
      "nameOnCard": "AbhinavAradhya",
      "nickName": "Abhinav",
      "onUs": 0,
      "primary": true
    }
  ],
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
