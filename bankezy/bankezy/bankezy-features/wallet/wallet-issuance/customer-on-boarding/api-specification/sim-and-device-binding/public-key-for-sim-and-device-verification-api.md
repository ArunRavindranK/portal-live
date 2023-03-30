---
description: >-
  This API is used to generate RSA key for performing Sim and device validation
  process.
---

# Public Key for SIM and Device verification API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/user/auth/getPublicKeyForPVC/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../authentication-and-authorization/login-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceUniqueId" required="true" %}
Unique id to identify the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="osType" %}
Indicates the OS type as either Android / iOS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="osName" %}
Type of OS either Android or iOS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="osVersion" %}
Version of the OS Example :10
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceIdType" %}
Example : 3
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceModel" %}
Model of the device
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "rsaPubKey": "MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCNxq6NA+0DCT8r2yje5WNP9zqrkYj+MFA6HaQq+q3kO/MnHSj0z+t8/r5fr4Lh7Mi0ObTA4Lp4BnyPMeOQ43c6QfJpCTrp9SVZ1+yIzlPwL/HEz9GqZfTdFHEgQlTPvQ00tNK4ouV01EUmVS2D0OBdSct0LERlXXfMMU8BTgIkEwIDAQAB",
        "keyRef": "1111|665|[C@41a21021",
        "aesKeyForRsa": "BIYTA4IyvoLdhRlYhgAYew=="
    }
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

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request POST 'http://localhost:8083/onboarding/user/auth/getPublicKeyForPVC/v1' \
--header 'X-API-TOKEN: token' \
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'Content-Type:text/plain'
--data-raw '{
    "deviceIdType": "3",
    "deviceModel": "Android SDK built for x86",
    "deviceUniqueId": "anid:I0zQZF/190IPXOdkfmA22iEoI/V5o2djXxLdlHmVVjA=:ff0a",
    "osName": "Android",
    "osType": "Android",
    "osVersion": "REL"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json5
{
    "deviceIdType": "3",
    "deviceModel": "Android SDK built for x86",
    "deviceUniqueId": "anid:I0zQZF/190IPXOdkfmA22iEoI/V5o2djXxLdlHmVVjA=:ff0a",
    "osName": "Android",
    "osType": "Android",
    "osVersion": "REL"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "rsaPubKey": "MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCNxq6NA+0DCT8r2yje5WNP9zqrkYj+MFA6HaQq+q3kO/MnHSj0z+t8/r5fr4Lh7Mi0ObTA4Lp4BnyPMeOQ43c6QfJpCTrp9SVZ1+yIzlPwL/HEz9GqZfTdFHEgQlTPvQ00tNK4ouV01EUmVS2D0OBdSct0LERlXXfMMU8BTgIkEwIDAQAB",
        "keyRef": "1111|665|[C@41a21021",
        "aesKeyForRsa": "BIYTA4IyvoLdhRlYhgAYew=="
    }
}
```
{% endtab %}
{% endtabs %}
