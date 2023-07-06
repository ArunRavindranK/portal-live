---
description: >-
  API validates the BNPL transaction with respect to Merchant, product and
  amount and based on OTP configuration, authentication is initiated.
---

# Init Transaction  / Loan

{% swagger method="post" path="/v1/txn/initBnpl" baseUrl="<domain>" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
The token got from the 

[Get Token API](../../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" type="String" required="true" %}
102
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="Number" %}
Numeric value with max 2 decimals
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="Int" %}
Merchant ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productId" type="int" %}
Product Identifier
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
{% tab title="Sample Curl Request" %}
```
curl --location 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/txn/initBnpl' 
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: <REPLACE_WITH_TOKEN_FROM_GET_TOKEN_API_RESPONSE>' \
 --data '{

  "amount": 500,

  "merchantId": 76,

  "productId": 323

}'
```
{% endtab %}

{% tab title="Request Example" %}
```json
{

  "amount": 500,

  "merchantId": 76,

  "productId": 323

}
```
{% endtab %}

{% tab title="Response Example" %}
```json
{
    "resCode": "LND200",
    "resDesc": "SUCCESS",
    "data": {
        "otpRequired": "N"
    }
}
```
{% endtab %}
{% endtabs %}

### Response Details

| Response Body | Data Type | Field Description            |
| ------------- | --------- | ---------------------------- |
| resCode       | String    | Response Code                |
| resDesc       | String    | Response Description         |
| otpRequired   | String    | returns otp required or not  |

### Custom Response Codes

| Response Codes | Response Description                                  |
| -------------- | ----------------------------------------------------- |
| LND024         | Invalid Product                                       |
| LND025         | Invalid Amount                                        |
| LND026         | Merchant Invalid                                      |
| LND027         | Limit exhausted                                       |
| LND028         | Insufficient Amount                                   |
| LND009         | There seems to be a technical issue. Try again later. |
| LND022         | User account does not exist                           |
