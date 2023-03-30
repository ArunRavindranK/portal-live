---
description: >-
  This API helps to generate RSA key.  By using this key user device unique id
  will be encrypted and used for bio metric authentication.
---

# Public Key for Biometric API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/user/getPublicKey/v1 " summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../common-apis/get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" %}
text/plain
{% endswagger-parameter %}

{% swagger-parameter in="body" name="authFactorType" required="true" %}
Type of authentication. Since it is from mobile app it should 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="true" %}
Device unique id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="osType" required="true" %}
Indicates the OS type as either Android / iOS
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":{
      "keyRef":"DEC_KEY|202202UYgapi",
      "publicKey":"MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCKDv1HziZ5Ut8YCO8rACSZdi6DopRbSgr2r8oiTZC9gJCZkMt6yx4BXnZ8FCkr0JpanLOnNGFYvMm2Kfy82u/9zScnOoj8hMhCupNO4aPrH42fMXeX2nO0pBNoB5a7nGMI36DhuXRVDROkJptzWICUuL90twdyXIxlE+TPtvP8zQIDAQAB"
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
{% tab title="Sample Curl Request" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'http://localhost:8083/onboarding/user/getPublicKey/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'X-API-TOKEN:TOKEN'
--data-raw '{ "deviceId":"anid:AloZHNC6ehWfiK4lgVoNIsq3wRGpIe5y8sGJn/ey8Ws=:1ffe", "osType":"android", "authFactorType":"1" }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
   "authFactorType":"2",
   "deviceId":"anid:7vpswUwL4EiBjHgqVgTYmoadZSjS4Ffb2xJ8lv69Muc=:fe89",
   "osType":"android"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "keyRef": "DEC_KEY|202204tkWHsv_1111_665_anid:AloZHNC6ehWfiK4lgVoNIsq3wRGpIe5y8sGJn/ey8Ws=:1ffe",
        "publicKey": "MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCXvvklWJ0zMP4itM6nlGeDw/qAMUM0F2iZdbnl9We/n5JOpEgKg68RJIu4rVxC8wSu89lzNR7k67dZUEzUjptaFS9rih6vcZL9wkMBfQhfErp/N5qHS6TTOaDly81/WUXFlckQ5iDujN/icNnHm75AWbXsDdyXx/TYTGuwscdb6wIDAQAB"
    }
}
```
{% endtab %}
{% endtabs %}
