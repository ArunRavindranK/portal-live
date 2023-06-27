---
description: >-
  This api checks the availability of the VPA and also provides suggestion if
  the vpa is not available.
---

# Verify VPA API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/transaction/v2/verifyVpa" summary="This api checks the availability of the VPA and also provides suggestion if the vpa is not available" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
program id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" required="false" %}
account number for api call
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vpa" required="true" %}
vpa to verify
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" %}
udfparametres for request
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

## Custom response code

| Response code | Response description                                 |
| ------------- | ---------------------------------------------------- |
| UPI113        | Invalid vpa.                                         |
| UPI114        | Expired vpa.                                         |
| UPI115        | Transaction not permitted to the vpa by PSP.         |
| UPI116        | Vpa restricted by the customer.                      |
| UPI117        | PSP is not registered i.e invalid vpa handle suffix. |
| UPI118        | Any other reason.                                    |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
 "vpa":"7914717873@payu",
 "udfParameters":""
 }
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
    "resCode": "UPI112",
    "resDesc": "Vpa is Verified",
    "data": {
        "merchantId": "TEST",
        "merchantChannelId": "TEST",
        "gatewayTransactionId": "12345768",
        "gatewayResponseStatus": "SUCCESS",
        "gatewayResponseCode": "200",
        "gatewayResponseMessage": "VPA IS AVAILABLE",
        "vpa": "7914717873@payu",
        "name": null,
        "ifsc": null,
        "iin": null,
        "isMerchant": null,
        "isMerchantVerified": null,
        "mcc": null,
        "merchantType": null,
        "udfParameters": null,
        "wibmoRespCode": 200,
        "wibmoResDesc": null,
        "wibmoErrorMessage": null,
        "mandateSupported": false
    }
}
```
{% endtab %}

{% tab title="Sample Curl Command " %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/transaction/v2/verifyVpa' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
 "vpa":"7914717873@payu",
 "udfParameters":"{}"
 }'
```
{% endtab %}
{% endtabs %}
