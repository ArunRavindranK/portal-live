---
description: Update Card Holder Profile
---

# Update Card Holder Profile

​

{% swagger method="put" path="" baseUrl="<domain>/wallet/wallet/internal/v1/cardHolderProfile" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="aadhaarNumber" required="true" type="String" %}
​Aadhaar Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accountNumber" required="true" type="String" %}
​Account Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" required="true" type="String" %}
Address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="city" required="true" type="String" %}
City
{% endswagger-parameter %}

{% swagger-parameter in="body" name="country" required="true" type="String" %}
​Country
{% endswagger-parameter %}

{% swagger-parameter in="body" name="dob" required="true" type="String" %}
Dob
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" required="true" type="String" %}
​Email
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" type="String" %}
The token got from the 

[login API](https://teams.microsoft.com/o/p6zvZh1r7XYNx0PmyEsS/s/CwdILEPBOX4lLKCKMZGB/~/changes/1N4jHPuBZcVMjqkduW8F/bankezy/bankezy/bankezy-features/wallet/wallet-issuance/customer-on-boarding/api-reference/authentication-and-authorization/login-api)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="firstName" required="true" type="String" %}
First Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="kycLevel" required="true" type="String" %}
​KYC Level
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lastName" required="true" type="String" %}
Last Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" required="true" type="String" %}
​Mobile
{% endswagger-parameter %}

{% swagger-parameter in="body" name="state" required="true" type="String" %}
state
{% endswagger-parameter %}

{% swagger-parameter in="body" name="zipCode" required="true" type="String" %}
​zipCode
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

{% swagger-response status="204: No Content" description="" %}
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
{% endswagger %}

| Response Code | Response Description |
| ------------- | -------------------- |
| 150           | Failure              |

{% tabs %}
{% tab title="Sample curl command" %}
curl --location --request PUT '[https://payment1.pcdev.enstage-sas.com/wallet/internal/v1/cardHolderProfile'\\](https://payment1.pcdev.enstage-sas.com/wallet/internal/v1/cardHolderProfile'/)\
\\--header 'Content-Type: text/plain'

\\--header 'X-API-KEY: MOB-APP-2001'\
\\--header 'X-API-TOKEN:token'\
\\--data-raw '{\
&#x20; "aadhaarNumber": "string",\
&#x20; "accountNumber": "string",\
&#x20; "address": "string",\
&#x20; "city": "string",\
&#x20; "country": "string",\
&#x20; "dob": "string",\
&#x20; "email": "string",\
&#x20; "firstName": "string",\
&#x20; "kycLevel": 0,\
&#x20; "lastName": "string",\
&#x20; "mobile": "string",\
&#x20; "state": "string",\
&#x20; "zipCode": "string"\
}'
{% endtab %}

{% tab title="Request" %}


```
 '{
  "aadhaarNumber": "string",
  "accountNumber": "string",
  "address": "string",
  "city": "string",
  "country": "string",
  "dob": "string",
  "email": "string",
  "firstName": "string",
  "kycLevel": 0,
  "lastName": "string",
  "mobile": "string",
  "state": "string",
  "zipCode": "string"
}'
```
{% endtab %}

{% tab title="Response" %}
200 -> success

| <p><br></p> |
| ----------- |


{% endtab %}
{% endtabs %}
