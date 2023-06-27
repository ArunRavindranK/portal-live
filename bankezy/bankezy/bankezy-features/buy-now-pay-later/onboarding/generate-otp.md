---
description: This API is used to generate the OTP, a step before user onboarding journey.
---

# Generate OTP

{% swagger method="post" path="/lending/v1/otp" baseUrl="<domain>" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" type="String" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" type="String" %}
The token got from the 

[Get Token API](../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" required="true" type="String" %}
User mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" required="true" type="String" %}
User email ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" required="true" type="String" %}
Merchant ID
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

### Response Details

| Response Body | Data Type | Field Description    |
| ------------- | --------- | -------------------- |
| resCode       | String    | Response Code        |
| resDesc       | String    | Response Description |
| refId         | String    | Reference Id         |
| eventId       | Integer   | Event Id             |
| otpValue      | String    | OTP Value            |

{% tabs %}
{% tab title="Sample Curl Request" %}
```
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/otp' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: <REPLACE_WITH_TOKEN_FROM_GET_TOKEN_API_RESPONSE>' \
--data-raw '{
  "mobile": "9709876543",
  "email": "style@gmail.com",
  "merchantId": "1234"
}'
```
{% endtab %}

{% tab title="Request Example" %}
```json
{ 
    "mobile": "9709876543", 
    "email": "style@gmail.com",
    "merchantId": "1234" 
}
```
{% endtab %}

{% tab title="Response Example" %}
```json
{ 
"resCode": 200, 
"resDesc": "OTP_SENT",
"data": { 
          "refId": "f0fbb54c-859e-46e3-8d85-7ea4c7048861",
          "eventId": 1001
 } 
}
```


{% endtab %}
{% endtabs %}

### Custom ResponseCodes

| ResponseCode | Response description                                  |
| ------------ | ----------------------------------------------------- |
| LND005       | Mobile number is mandatory                            |
| LND006       | Invalid mobile number                                 |
| LND007       | Email address is mandatory                            |
| LND008       | Merchant Id is mandatory.                             |
| LND001       | OTP sent to the registered number                     |
| LND009       | There seems to be a technical issue. Try again later. |
