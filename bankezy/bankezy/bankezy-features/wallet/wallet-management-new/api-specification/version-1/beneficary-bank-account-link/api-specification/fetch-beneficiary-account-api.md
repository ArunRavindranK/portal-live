---
description: Fetch Benificiary Account(s)
---

# Fetch Beneficiary Account API

{% swagger method="post" path="" baseUrl="<domain>/wallet/ac/fetchbeneficiary/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" required="true" name="X-API-TOKEN  " %}
​The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accReq" type="Boolean" required="true" %}
​accReq
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vpaReq" type="Boolean" required="true" %}
vpaReq
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" %}
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

## Custom response codes

| Code | Description                         |
| ---- | ----------------------------------- |
| 150  | ​Beneficiary Accounts not available |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
​curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/ac/fetchbeneficiary/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw '{ "accReq": true, "vpaReq": true }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "accReq": true,
  "vpaReq": true
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "Beneficiary Accounts fetched successfully",
  "data": [
    {
      "id": 42,
      "customerId": "2022",
      "accountNumber": null,
      "accountName": null,
      "ifscCode": null,
      "bankName": null,
      "accountType": null,
      "branchName": null,
      "vpa": "8892239811@bankezy"
    },
    {
      "id": 78,
      "customerId": "2022",
      "accountNumber": "0587277770835643",
      "accountName": "Abhinav",
      "ifscCode": "QEANUSGBRZ3C1UJ",
      "bankName": "jUNZzBxLOynGRmUz",
      "accountType": "qTOKhfEo",
      "branchName": "zFASSbpybfwAWCCscpqKsTYVi",
      "vpa": null
    },
    {
      "id": 79,
      "customerId": "2022",
      "accountNumber": "5629375757368492",
      "accountName": "Abhinav",
      "ifscCode": "IJG25PLYXD36DDO",
      "bankName": "niTjwajIdvjSaddr",
      "accountType": "MfgNpJEy",
      "branchName": "YRYUNdEagQwpZimFOIZXTiQXQ",
      "vpa": null
    }
  ]
}
```
{% endtab %}
{% endtabs %}
