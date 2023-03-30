---
description: >-
  If user want to enable or disable device lock i.e biometric authentication,
  this api is required
---

# Enable disable Device Lock API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/user/enableDisableDeviceLock/v1" summary="" %}
{% swagger-description %}
This API is used to enable or diable device lock after login
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the

[login API](login-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="true" %}
Device unique id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="signInMode" required="true" %}
signInMode 1 - Pin based mode

signInMode 2 - Device based mode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="enable" required="true" %}
0 - disable

1 - enable
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pin" required="true" %}
If SignInMode is 1 (i.e) Pin based then 4 digit pin should be given. If SignInMode is 2 (i.e) Device based then device id should be encrypted by using

[public key](../biometric-authentication/public-key-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="keyRef" required="true" %}
Key ref is mandatory only for

[biometric authentication](../biometric-authentication/public-key-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "SUCCESS"
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
curl --location --request POST 'http://localhost:10000/onboarding/user/enableDisableDeviceLock/v1' \
\--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw' \
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Cookie: JSESSIONID=C0D114845B4EC3A92A840A1B862E96F4' \
\--data-raw '{
    "deviceId":"tdid:zoqDZXDF59W+5yuhCodFoDGCGXTo8uHJkVRhLTOxk6o=:7971",
    "signInMode":"2",
    "enable":"0",
    "pin":"hello",
    "keyRef":"DEC_KEY|202112s3IjT1"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "deviceId":"tdid:zoqDZXDF59W+5yuhCodFoDGCGXTo8uHJkVRhLTOxk6o=:7971",
    "signInMode":"2",
    "enable":"0",
    "pin":"hello",
    "keyRef":"DEC_KEY|202112s3IjT1"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS"
}
```
{% endtab %}
{% endtabs %}
