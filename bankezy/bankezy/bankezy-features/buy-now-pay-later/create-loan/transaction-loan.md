---
description: >-
  This API is used for creating loan for user purchases. A purchase involves the
  acquisition of goods or services in exchange for a payment in credit.
---

# Transaction  / Loan

{% swagger method="post" path="/lending/v1/txn/bnpl" baseUrl="<domain>" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
The token got from the 

[Get Token API](../../market-place/api-specification/version-1/get-token-api.md)


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
<pre><code>curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/txn/bnpl' \
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
    "merchantId": 0, 
    "productId": 2 
}
```
{% endtab %}

{% tab title="Response Example" %}
<pre class="language-json"><code class="lang-json">{ 
"resCode": "LND_2001", 
"resDesc": "SUCCESS", 
"data": { 
<strong>    "txnRefNum": "83483483438" 
</strong>}
</code></pre>
{% endtab %}
{% endtabs %}

### Response Details

| Response Body | Data Type | Field Description            |
| ------------- | --------- | ---------------------------- |
| resCode       | String    | Response Code                |
| resDesc       | String    | Response Description         |
| txnRefNum     | String    | Transaction Reference Number |

### Custom Response Codes

| Response Codes | Response Description                                  |
| -------------- | ----------------------------------------------------- |
| LND024         | INVALID PRODUCT                                       |
| LND025         | INVALID AMOUNT                                        |
| LND026         | INVALID\_MERCHANT                                     |
| LND027         | NO LIMIT                                              |
| LND028         | INSUFFICIENT AMOUNT                                   |
| LND009         | There seems to be a technical issue. Try again later. |
