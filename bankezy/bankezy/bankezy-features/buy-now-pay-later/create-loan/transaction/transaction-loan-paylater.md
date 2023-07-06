---
description: >-
  This API is used for creating loan for user purchases. A purchase involves the
  acquisition of goods or services in exchange for a payment in credit.
---

# Transaction  / Loan - PayLater

{% swagger method="post" path="/lending/v1/txn/bnpl" baseUrl="<domain>" summary="" %}
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

{% swagger-parameter in="body" name="otpRefNum" type="String" %}
Otp Ref num
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpNum" type="String" %}
Otp Num
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
curl --location 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/txn/bnpl' --header 'X-API-KEY: MOB-APP' --header 'X-API-TOKEN: Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJORVdfVVNFUiIsIlRPS0VOX0VYUElSWSI6MTUsIlgtQVBJLVZFUlNJT04iOiJ2MSIsIlJFRkVSRU5DRV9JRCI6ImZhZDRkMTkyLWMyNjAtNDUyMy05YTQzLTVlMGQwMWI1NDgzZiIsImFjY2VwdC1sYW5ndWFnZSI6ImVuLVVTIiwiQUxMT1dFRF9JUFMiOiIqIiwiaXNzIjoiaVRKMFRsbTFrVVdvSmFaTkd5YWFpR2ljWEt6WE1CNXAiLCJleHAiOjE2ODQ4NDUzNzAsIlBST0dSQU1fSUQiOjExMTEsImlhdCI6MTY4NDg0NDQ3MH0.CnKBRm8iTQTNhIeWN2Z_Ifm1pxlb6H3fr6RhHMChJb7cKVs2OYzUPFzZPgzRJHFGF-EV8AGNzDKTWTbu_6b8Rw' --header 'Content-Type: application/json' --data '{
  "amount": 500,
  "merchantId": 76,
  "productId": 323,
  "otpNum": "752918",
  "otpRefNum": "89aaa3a4-186e-4f74-8a75-9d34de715426"
}'
```
{% endtab %}

{% tab title="Request Example" %}
```json
{ 
    "amount": 20.00, 
    "merchantId": 0, 
    "productId": 2 ,
    "otpRefNum":"dfdkfsdkkfsd",
    "otpNum":"383883"
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
| LND033         | Unable to Create Loan Transaction                     |
| LND034         | INVALID OTP                                           |
| LND200         | SUCCESS                                               |
