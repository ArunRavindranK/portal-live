---
description: >-
  The API is used fetch transaction limit and fee config from Fee master
  configuration.
coverY: 0
---

# Fetch Fees API

Following are the features supported:

Supports Daily/Weekly/Monthly transaction limit configuration & fee limit configuration for different transaction types like P2P,P2M







{% swagger method="post" path="" baseUrl="admin/prog-attribute/fetch/configuration/v1" summary="" %}
{% swagger-description %}
Parse and validate the QR string passed in the request. In case of validation error in raw string, application will return invalid exception
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" type="String" %}
MOB-APP
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" type="String" %}
The token got from the 

[login API](../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/common-apis/get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="rawString" type="String" required="true" %}
raw QR string
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" %}
text/json
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="SUCCESS" %}
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

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}



| Error code | Description                |
| ---------- | -------------------------- |
| 200        | Success                    |
| 100        | Please try after some time |
| 500        | Internet Server Error      |
| 100        | Execution Failure          |



{% tabs %}
{% tab title="Sample Curl" %}
```html
curl --location GET 'https://user4.pcdev.enstage-sas.com/kong/admin/prog-attribute/fetch/configuration/v1?txnType=P2B&condition=ALL&X-API-KEY=MOB-APP-2001' \
--header 'X-PROGRAM-ID: 1111' \
--header 'X-API-KEY: MOB-APP-2001' \
--header 'Cookie: __cfruid=a1edd96201bb7f3f42cf6c452dff0a446f5c476e-1687345454; JSESSIONID=B42F80CB930F1CEFFF665F559B7FE7AD'
```
{% endtab %}

{% tab title="Request Body" %}
```json
```
{% endtab %}

{% tab title="Response Body" %}
```json
{
    "resCode": 200,
    "resDesc": "Success",
    "data": {
        "coolingPeriod": null,
        "limitMaster": {
            "txnType": "P2P",
            "perTxnAmt": 1000000,
            "limit": [
                {
                    "window": "DAILY",
                    "amountLimit": 5000000,
                    "countLimit": 100
                },
                {
                    "window": "MONTHLY",
                    "amountLimit": 10000000,
                    "countLimit": 100
                }
            ]
        },
        "feeMaster": {
            "txnType": "P2P",
            "feePercentage": 2,
            "gst": null
        }
    }
}
```
{% endtab %}
{% endtabs %}

