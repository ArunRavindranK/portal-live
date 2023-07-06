---
description: >-
  This API is used for creating loan for user purchases. A purchase involves the
  acquisition of goods or services in exchange for a payment in credit.
---

# Fetch EMI

{% swagger method="post" path="/lending/v1/txn/emiPlans" baseUrl="<domain>" summary="" %}
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
<pre><code>curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/txn/emiPlans\
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: &#x3C;REPLACE_WITH_TOKEN_FROM_GET_TOKEN_API_RESPONSE>' \
<strong>--header 'X-ACCOUNT-NUMBER: 102' \
</strong><strong>--data-raw '{
</strong>  "amount": 20.00,
  "merchantId": 5,
  "productId":2
}'
</code></pre>
{% endtab %}

{% tab title="Request Example" %}
```json
{ 
    "amount": 20.00, 
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
    "emiPlans": [
      {
        "emiAmount": "500.24",
        "noOfMonths": "3",
        "interestRate": "0.0",
        "planId": "EMI|3"
      },
      {
        "emiAmount": "258.95",
        "noOfMonths": "6",
        "interestRate": "12.0",
        "planId": "EMI|6"
      },
      {
        "emiAmount": "183.86",
        "noOfMonths": "9",
        "interestRate": "24.0",
        "planId": "EMI|9"
      }
    ]
  }
}
```
{% endtab %}
{% endtabs %}

### Response Details

| Response Body | Data Type | Field Description    |
| ------------- | --------- | -------------------- |
| resCode       | String    | Response Code        |
| resDesc       | String    | Response Description |
| emiPlans      | List      | emi plans            |
| emiAmount     | String    | emi amount           |
| noOfMonths    | String    | tenure               |
| interestRate  | String    | interest rate        |
| planId        | String    | planId               |

### Custom Response Codes

<table><thead><tr><th width="276">Response Codes</th><th>Response Description</th></tr></thead><tbody><tr><td>LND024</td><td>Invalid Product</td></tr><tr><td>LND025</td><td>INVALID AMOUNT</td></tr><tr><td>LND026</td><td>INVALID_MERCHANT</td></tr><tr><td>LND027</td><td>NO LIMIT</td></tr><tr><td>LND028</td><td>INSUFFICIENT AMOUNT</td></tr><tr><td>LND009</td><td>Try Later</td></tr><tr><td>LND022</td><td>User account does not exist.</td></tr><tr><td>LND200</td><td>SUCCESS</td></tr></tbody></table>
