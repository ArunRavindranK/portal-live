---
description: Admin user can view the list of Merchants.
---

# Merchant list

{% swagger method="post" path="/mrch-management/v1/merchantList" baseUrl="<domain>" summary="List Merchant" %}
{% swagger-description %}
Get the list of Merchants with the given limit.
{% endswagger-description %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" type="String" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="body" name="start" type="String" required="true" %}
merchant list limit 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="size" type="String" required="true" %}
merchant list limit  size
{% endswagger-parameter %}

{% swagger-parameter in="header" type="String" required="true" name="X-API-TOKEN " %}
The token got from the 

[login API](../../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/common-apis/get-app-token-api.md)


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

curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/mrch-management/v1/merchantList' \
--header 'X-API-KEY: MOB-APP1-1114' \
--header 'X-API-TOKEN: token' \
--header 'Content-Type: application/json' \
--data-raw '{
    "start":"2",
    "size":"2"
}'

```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "start":"2",
    "size":"2"
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
            "merchantId": "1003",
            "merchantName": "TANISHQ",
            "mcc": "5613",
            "mobile": "1234324324",
            "merchantStatus": "1",
            "records": 0
        },
        {
            "merchantId": "1004",
            "merchantName": "RELIANCE",
            "mcc": "5614",
            "mobile": "1234324327",
            "merchantStatus": "1",
            "records": 0
        }
    ]
}
```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>MER_2000</td><td>SUCCESS</td></tr><tr><td>MER_4001</td><td>Merchant Info Not Available</td></tr><tr><td>MER_5000</td><td>Try Later</td></tr></tbody></table>

## &#x20;
