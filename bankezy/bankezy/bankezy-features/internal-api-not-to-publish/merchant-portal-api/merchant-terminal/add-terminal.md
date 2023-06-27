---
description: This API enables the user to add a Terminal for the Merchant
---

# Add Terminal

{% swagger method="post" path="/mrch-management/v1/term" baseUrl="<domain>" summary="Add Terminal" %}
{% swagger-description %}
This api is used to  add the Terminal for the given merchantid.
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
The token got from the 

[login API](../../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/common-apis/get-app-token-api.md)


{% endswagger-parameter %}
{% endswagger %}

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/mrch-management/v1/term' \
--header 'X-API-TOKEN: token' \
--header 'X-API-KEY: MOB-APP1-1114' \
--header 'Content-Type: application/json' \
--data-raw '{
    "merchantId":"1008",
    "termId":"1113",
    "termIdRef": "TERMINAL_7",
    "termName":"abcd",
    "mobile":"8789178062",
    "emailId":"kaa@gmail.com",
    "status":"1"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "merchantId":"1008",
    "termId":"1113",
    "termIdRef": "TERMINAL_7",
    "termName":"abcd",
    "mobile":"8789178062",
    "emailId":"kaa@gmail.com",
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

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>MER_2000</td><td>SUCCESS</td></tr><tr><td>MER_4007</td><td>Duplicate Terminal Data</td></tr><tr><td>MER_5000</td><td>Try Later</td></tr><tr><td>MER_4002</td><td>Merchant Terminal fields missing</td></tr></tbody></table>

## &#x20;
