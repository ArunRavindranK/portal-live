---
description: This API gets the list of terminals associated with the merchant.
---

# Terminals list

{% swagger method="post" path="/mrch-management/v1/termList" baseUrl="<domain>" summary="Terminal List" %}
{% swagger-description %}
This API gets the list of terminals associated with the selected merchant.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="String" required="true" %}
MerchantId
{% endswagger-parameter %}

{% swagger-parameter in="header" type="String" required="true" name="X-API-TOKEN " %}
The token got from the 

[login API](../../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/common-apis/get-app-token-api.md)


{% endswagger-parameter %}
{% endswagger %}

{% tabs %}
{% tab title="Sample curl command" %}
```json
Mandatory FieldMissing Mandatory Fieldurl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/mrch-management/v1/termList' \
--header 'X-API-TOKEN: token' \
--header 'X-API-KEY: MOB-APP1-1114' \
--header 'Content-Type: application/json' \
--data-raw '{"merchantId":"1001"}'
```
{% endtab %}

{% tab title="Request sample" %}
```json

{"merchantId":"1001"}

```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "MER_2000",
    "resDesc": "SUCCESS",
    "data": [
        {
            "id": 1,
            "merchantId": "1001",
            "termId": "1101",
            "termIdRef": "TERMINAL 1",
            "termName": "Terminanal 1101",
            "mobile": "8754429068",
            "emailId": "praveena.j@wibmo.com",
            "termStatus": "1"
        },
        {
            "id": 5,
            "merchantId": "1001",
            "termId": "1101",
            "termIdRef": "TERMINAL 1",
            "termName": "Terminanal 1101",
            "mobile": "8754429068",
            "emailId": "praveena.j@wibmo.com",
            "termStatus": "1"
        },
        {
            "id": 7,
            "merchantId": "1001",
            "termId": "1109",
            "termIdRef": "TERMINAL_9",
            "termName": "abcd",
            "mobile": "8789177062",
            "emailId": "k@gmail.com",
            "termStatus": "1"
        },
        {
            "id": 12,
            "merchantId": "1001",
            "termId": "54321",
            "termIdRef": "Term Ref",
            "termName": "Term Name",
            "mobile": "8765676543",
            "emailId": "k@s.bubu",
            "termStatus": "0"
        },
        {
            "id": 13,
            "merchantId": "1001",
            "termId": "98756",
            "termIdRef": "Term Ref 2 ",
            "termName": "Term Name 2",
            "mobile": "6543543276",
            "emailId": "y@t",
            "termStatus": "1"
        },
        {
            "id": 17,
            "merchantId": "1001",
            "termId": "term 1",
            "termIdRef": "term ref ref",
            "termName": "term name",
            "mobile": "9764546546",
            "emailId": "k@gt",
            "termStatus": "1"
        },
        {
            "id": 18,
            "merchantId": "1001",
            "termId": "1023",
            "termIdRef": "Term Ref 1023",
            "termName": "Terminal name 1023",
            "mobile": "9876543213",
            "emailId": "k@g",
            "termStatus": "1"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>MER_2000</td><td>SUCCESS</td></tr><tr><td>MER_4001</td><td>Missing Mandatory Field</td></tr><tr><td>MER_5000</td><td>Try Later</td></tr><tr><td>MER_4002</td><td>Merchant Terminal fields missing</td></tr></tbody></table>

## &#x20;
