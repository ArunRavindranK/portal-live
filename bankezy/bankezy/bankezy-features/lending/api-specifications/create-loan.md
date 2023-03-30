---
description: This API is used for creating loan for user transactions in LMS.
---

# Create Loan

{% swagger method="post" path="" baseUrl="/lending/v1/txn/bnpl" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
The token got from the 

[Get Token API](../../market-place/api-specification/get-token-api.md)


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
