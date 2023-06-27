---
description: Add Beneficiary Account
---

# Add Beneficiary API



{% swagger method="post" path="" baseUrl="<domain>/wallet/ac/v2/addbeneficiary" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="accountName" %}
Account Name 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accountNumber" %}
​Account Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accountType" %}
Account Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankName" %}
Bank Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="branchName" %}
Branch Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ifscCode" %}
IFSC Code  
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN  " %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
MOB-APP-2001
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
{% endswagger %}

## Custom response codes

| Code   | Description                             |
| ------ | --------------------------------------- |
| WAL139 | Beneficiary Accounts addition failed    |
| WAL138 | Beneficiary Accounts added successfully |

### Response Details

<table><thead><tr><th width="153">Response Field</th><th>Field Desc</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td></td><td>String</td><td></td></tr><tr><td>resDesc</td><td>SUCCESS, FAILURE status of the API</td><td>String</td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
​curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/ac/v2/addbeneficiary'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:replace_with_basic_auth_to_be_built_by_client' --data-raw '{ "accountName": "Abhinav", "accountNumber": "0041487199714541", "accountType": "gOLHJnSU", "bankName": "HcMXiqmLASmqJvEz", "branchName": "rCyiggGMerWeFTOOkEPAZQfsz", "ifscCode": "EYQRY44ZTTK86MS" }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "accountName": "Abhinav",
  "accountNumber": "0041487199714541",
  "accountType": "gOLHJnSU",
  "bankName": "HcMXiqmLASmqJvEz",
  "branchName": "rCyiggGMerWeFTOOkEPAZQfsz",
  "ifscCode": "EYQRY44ZTTK86MS"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": "WAL138",
  "resDesc": "Beneficiary Accounts added successfully"
}
```
{% endtab %}
{% endtabs %}
