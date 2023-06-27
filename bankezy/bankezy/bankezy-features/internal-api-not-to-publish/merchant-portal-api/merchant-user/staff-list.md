---
description: >-
  This API enables the user to get the list of staff/users associated with the
  Merchant
---

# Staff List

{% swagger method="post" path="/mrch-management/v1/userList" baseUrl="<domain>" summary="List of Users" %}
{% swagger-description %}
This api gets the list of users associated with the Merchant and Terminal
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

{% swagger-parameter in="header" name="X-API-TOKEN " type="String" required="true" %}
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
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/mrch-management/v1/userList' \
--header 'X-API-KEY: MOB-APP1-1114' \
--header 'X-API-TOKEN: token' \
--header 'Content-Type: application/json' \
--data-raw '{
    "merchantId":"1003",
    "termId":"3"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "merchantId":"1003",
    "termId":"3"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "MER_2000",
    "resDesc": "SUCCESS",
    "data": [
        {
            "userId": 3,
            "merchantId": "1003",
            "termId": 3,
            "accountNumber": "1813",
            "mobile": "9448859870",
            "emailId": "user2@wibmo.com",
            "status": "1",
            "userAlert": {
                "sms": "1",
                "email": "1",
                "push": "1",
                "sticky": "0",
                "voiceAlert": "1",
                "speaker": "0"
            }
        },
        {
            "userId": 59,
            "merchantId": "1003",
            "termId": 3,
            "accountNumber": "9876543",
            "mobile": "9876546546",
            "emailId": "J@Y",
            "status": "1",
            "userAlert": {
                "sms": "1",
                "email": "1",
                "push": "1",
                "sticky": "1",
                "voiceAlert": "1",
                "speaker": "1"
            }
        }
    ]
}
```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>MER_2000</td><td>SUCCESS</td></tr><tr><td>MER_4001</td><td>Merchant Info Not Available</td></tr><tr><td>MER_5000</td><td>Try_later</td></tr></tbody></table>

## &#x20;
