---
description: This API is used to get public key for pvc.
---

# Get Public Key For PVC API

{% swagger method="post" path="" baseUrl="http://192.168.105.70:8083/onboarding/user/auth/getPublicKeyForPVC/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceUniqueId" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="osType" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="osName" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="osVersion" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceIdType" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceModel" required="true" %}

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

{% tabs %}
{% tab title="Request" %}
```json
{
    "deviceUniqueId" : "869444038443107",
    "osType" : "",
    "osName" : "",
    "osVersion" : "",
    "deviceIdType" : "",
    "deviceModel" : ""
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "rsaPubKey": "MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCRzQgM3frOzWt8RhyruRP8ArCa/Eir8slpySgN6aD2CQpZgPQiNeJTOZjghIE9hWc05RYgTMqJGkGPuwGo+ycYz0+2F9if6PMrlSls5M0Tu71lG7x0+cgqzJtUgxD4PwSOhtNBinak/CimcMKmTmx7+Mb0nPjWtyDeUM/+ACtRfQIDAQAB",
        "keyRef": "2001|3089|[C@5fc133b3",
        "aesKeyForRsa": "UlTQ6Nt73YeET/7/0FlETw=="
    }
}
```
{% endtab %}

{% tab title="Sample Curl  COmmand" %}
```json
curl --location --request POST 'http://192.168.105.70:8083/onboarding/user/auth/getPublicKeyForPVC/v1' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: application/json'
--data-raw '{
    "deviceUniqueId" : "869444038443107",
    "osType" : "",
    "osName" : "",
    "osVersion" : "",
    "deviceIdType" : "",
    "deviceModel" : ""
}'
```
{% endtab %}
{% endtabs %}
