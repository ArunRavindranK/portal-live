---
description: Fetch the given wallet Card CVV
---

# Fetch Card CVV API

{% swagger method="post" path="" baseUrl="<domain>/wallet/fetch/cvv/api/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="productType" type="String" %}
Product Type(wallet type ex: RW)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" type="Int" %}
Wallet Id (wallet unique ref #)
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

| Response code | Response description                 |
| ------------- | ------------------------------------ |
| 1             | fetch card details successfully      |
| ​3            | internal server error                |
| 11            | prepaid card details not found       |
| ​20           | request is empty                     |
| 39            | product type or customer id is empty |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/fetch/cvv/api/v1' --header 'Content-Type: text/plain' --header 'X-API-TOKEN:replace_with_basic_auth_to_be_built_by_client' --data-raw '{ "productType": "RW", "walletId": 1 }'​
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}


```json
{
  "productType": "RW",
  "walletId": 1
}
```
{% endtab %}

{% tab title="Response sample" %}


```json
{
  "resCode": 1,
  "resDesc": "fetch card details successfully",
  "data": {
    "customerId": "1",
    "walletId": 1,
    "cvv": "298"
  }
}n
```
{% endtab %}
{% endtabs %}
