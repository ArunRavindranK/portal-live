---
description: >-
  This API is used to update the user current device details. This API will be
  called only when user uses new device.
---

# Update Device Details API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/userDevice/updateDeviceDetails/v1 " summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](login-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="true" %}
Unique device identifier
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceModel" %}
Model of the user device 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fcmId" required="true" %}
Mentioned as per document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="clientIp" %}
Client's IP address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="appVersion" type="int" %}
Version of the BankEzy Application
{% endswagger-parameter %}

{% swagger-parameter in="body" name="osType" %}
Device of the OS either Android or iOS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="osVersion" %}
Version of the OS Example : 10
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceMake" %}
Maker name of the device Eg: Samsung
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceType" type="int" %}
Type of device. Example : 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="netOpertaor" %}
Operator name Example : bnn
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gpsLatitude" type="float" %}
gps location of  the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gpsAccuracy" type="float" %}
gps location of the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gpsLongitude" type="float" %}
gps location of the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="zipCode" %}
zip code of the device
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
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
curl --location --request POST 'http://localhost:8083/onboarding/userDevice/updateDeviceDetails/v1' \
\--header 'X-API-TOKEN: token'
\--header 'X-API-KEY: MOB-APP-2001'
\--data-raw '{
    "deviceId":"anid:AloZHNC6ehWfiK4lgVoNIsq3wRGpIe5y8sGJn/ey8Ws=:1ffe",
    "deviceModel":"",
    "fcmId":"eyJhbGciOiJFUzI1NiIsInR5cCI6IkpXVCJ9.eyJhcHBJZCI6IjE6NDc4MzMwOTY1MTQwOmFuZHJvaWQ6ZWY4OGFlOGU5YWNiM2EzODc0Zjg4MSIsImV4cCI6MTY0ODAxMTYyOCwiZmlkIjoiZFd3T0dDcUhSSzJta2toVS0wdVJHQyIsInByb2plY3ROdW1iZXIiOjQ3ODMzMDk2NTE0MH0.AB2LPV8wRQIhALxTLWiIb-fNzMkhSxGIORhkkTzjEsE0FMcOVc5qF5I2AiAdV-EyFtq_54GMQjTE1eahsqNUuBLo60tXA4dGfc2JAA",
    "clientIp":"",
    "appVersion":0,
    "osType":"Android",
    "osVersion":"",
    "deviceMake":"",
    "deviceType":"1",
    "netOpertaor":"",
    "gpsAccuracy":"0.000000",
    "gpsLatitude":"0.000000",
    "gpsLongitude":"0.000000",
    "zipCode":""
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "deviceId":"anid:AloZHNC6ehWfiK4lgVoNIsq3wRGpIe5y8sGJn/ey8Ws=:1ffe",
    "deviceModel":"",
    "fcmId":"eyJhbGciOiJFUzI1NiIsInR5cCI6IkpXVCJ9.eyJhcHBJZCI6IjE6NDc4MzMwOTY1MTQwOmFuZHJvaWQ6ZWY4OGFlOGU5YWNiM2EzODc0Zjg4MSIsImV4cCI6MTY0ODAxMTYyOCwiZmlkIjoiZFd3T0dDcUhSSzJta2toVS0wdVJHQyIsInByb2plY3ROdW1iZXIiOjQ3ODMzMDk2NTE0MH0.AB2LPV8wRQIhALxTLWiIb-fNzMkhSxGIORhkkTzjEsE0FMcOVc5qF5I2AiAdV-EyFtq_54GMQjTE1eahsqNUuBLo60tXA4dGfc2JAA",
    "clientIp":"",
    "appVersion":0,
    "osType":"Android",
    "osVersion":"",
    "deviceMake":"",
    "deviceType":"1",
    "netOpertaor":"",
    "gpsAccuracy":"0.000000",
    "gpsLatitude":"0.000000",
    "gpsLongitude":"0.000000",
    "zipCode":""
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
