---
description: This API enables the user to add Staff/user associated with the merchant
---

# Add staff

{% swagger method="post" path="/mrch-management/v1/user" baseUrl="<domain>" summary="Add the user associated with the Merchant" %}
{% swagger-description %}
This api used to add the merchant staff/user
{% endswagger-description %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" type="String" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="String" required="true" %}
Merchant id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="termId" type="String" required="true" %}
Merchant term id 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accountNumber" type="String" required="true" %}
Account number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" type="String" required="true" %}
Mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="emailId" type="String" required="true" %}
Email Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="String" required="true" %}
Status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userAlert.sms" type="String" %}
Useralert SMS

eg: "1" 0r "0"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userAlert.email" type="String" %}
UserAlert email

eg: "1" 0r "0"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userAlert.push" type="String" %}
UserAlert push

eg: "1" 0r "0"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userAlert.sticky" type="String" %}
UserAlert  sticky

eg: "1" 0r "0"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userAlert.voiceAlert" type="String" %}
UserAlert  voiceAlert

eg: "1" 0r "0"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userAlert.speaker" type="String" %}
UserAlert  speaker

eg: "1" 0r "0"
{% endswagger-parameter %}

{% swagger-parameter in="header" type="String" required="true" name="X-API-TOKEN " %}
The token got from the login API
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

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/mrch-management/v1/user' \
--header 'X-API-KEY: MOB-APP1-1114' \
--header 'X-API-TOKEN: token' \
--header 'Content-Type: application/json' \
--data-raw '{
    "merchantId":"1008",
    "termId":"11",
    "accountNumber":"1817",
    "mobile":"123456789",
    "emailId":"user7@wibmo.com",
    "status":"1",
    "userAlert":{
        "sms":"1",
        "email":"1",
        "push":"0",
        "sticky":"0",
        "voiceAlert":"0",
        "speaker":"1"
    }
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "merchantId":"1008",
    "termId":"11",
    "accountNumber":"1817",
    "mobile":"123456789",
    "emailId":"user7@wibmo.com",
    "status":"1",
    "userAlert":{
        "sms":"1",
        "email":"1",
        "push":"0",
        "sticky":"0",
        "voiceAlert":"0",
        "speaker":"1"
    }
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "MER_2000",
    "resDesc": "SUCCESS",
    "data": "1008"
}
```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>MER_2000</td><td>SUCCESS</td></tr><tr><td>MER_4005</td><td>Merchant validation error</td></tr><tr><td>MER_5000</td><td>Try Later</td></tr><tr><td>MER_4002</td><td>Merchant User details cannot be added</td></tr></tbody></table>

## &#x20;
