---
description: This API enables the User to edit the terminal details.
---

# Update Terminal

{% swagger method="post" path="/mrch-management/v1/termDetail" baseUrl="<domain>" summary="Update Terminal" %}
{% swagger-description %}
Edit and update the terminal details for the given merchant.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="String" required="true" %}
Merchant Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="termId" type="String" required="true" %}
Term id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="termIdRef" type="String" %}
Term id Reference
{% endswagger-parameter %}

{% swagger-parameter in="body" name="termName" type="String" %}
Term name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" type="String" %}
Mobile
{% endswagger-parameter %}

{% swagger-parameter in="body" name="emailId" type="String" %}
Email id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="String" %}
Status
{% endswagger-parameter %}

{% swagger-parameter in="header" type="String" required="true" name="X-API-TOKEN " %}
The token got from the login API
{% endswagger-parameter %}
{% endswagger %}

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/mrch-management/v1/termDetail' \
--header 'X-API-TOKEN: token' \
--header 'X-API-KEY: MOB-APP1-1114' \
--header 'Content-Type: application/json' \
--data-raw '{
    "merchantId":"1001",
    "termId":"1109",
    "termIdRef": "TERMINAL_9",
    "termName":"abcd",
    "mobile":"8789177062",
    "emailId":"k@gmail.com",
    "status":"1"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "merchantId":"1001",
    "termId":"1109",
    "termIdRef": "TERMINAL_9",
    "termName":"abcd",
    "mobile":"8789177062",
    "emailId":"k@gmail.com",
    "status":"1"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json

{
    "resCode": "MER_2000",
    "resDesc": "SUCCESS"
}

```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>MER_2000</td><td>SUCCESS</td></tr><tr><td>MER_5000</td><td>Try Later</td></tr><tr><td>MER_4002</td><td>Merchant Terminal fields missing</td></tr></tbody></table>

## &#x20;
