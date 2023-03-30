---
description: >-
  To save device details for supporting Push Notification along with consent
  taken for specific permissions
---

# Save Device Details API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/userDevice/saveDeviceDetails/v1 " summary="" %}
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

{% swagger-parameter in="body" name="appVersion" required="false" %}
Current version of the application
{% endswagger-parameter %}

{% swagger-parameter in="body" name="clientIp" required="false" %}
Client Ip. Example : 12
{% endswagger-parameter %}

{% swagger-parameter in="body" name="consentName" required="false" %}
Example : whatsapp
{% endswagger-parameter %}

{% swagger-parameter in="body" name="consentStatus" required="false" %}
Consent is active or not Example : 1 - active 0 - non active
{% endswagger-parameter %}

{% swagger-parameter in="body" required="false" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="true" %}
Device unique id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceType" required="true" %}
Value fetched from Fetch Client Rules API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fcmId" required="true" %}
Google firebase id for push notification.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gpsAccuracy" required="false" %}
GPS location of the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gpsLatitude" required="false" %}
GPS location of the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gpsLongitude" required="false" %}
GPS location of the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="osType" required="true" %}
Type of OS either Android or iOS
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="false" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "resCode":200,
   "resDesc":"SUCCESS"
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
```json
curl --location --request POST 'http://localhost:8083/onboarding/userDevice/saveDeviceDetails/v1' \
\--header 'X-API-TOKEN: token'
\--header 'X-API-KEY:MOB-APP-2001'
\--data-raw '{
   "appVersion":"",
   "clientIp":"",
   "consentName":"Whatsapp",
   "consentStatus":"1",
   "deviceId":"anid:7vpswUwL4EiBjHgqVgTYmoadZSjS4Ffb2xJ8lv69Muc=:fe89",
   "deviceType":"1",
   "fcmId":"eyJhbGciOiJFUzI1NiIsInR5cCI6IkpXVCJ9.eyJhcHBJZCI6IjE6NDc4MzMwOTY1MTQwOmFuZHJvaWQ6NTUxMGQxMGNiM2ZmYjcyZjc0Zjg4MSIsImV4cCI6MTY0NTUwNjQ0NSwiZmlkIjoiZUtMWUVBd2lTNHVfdEJma3J4blBjTCIsInByb2plY3ROdW1iZXIiOjQ3ODMzMDk2NTE0MH0.AB2LPV8wRQIgaRQ06walCsIIlg98E6TEH1MXtlzASbU6Ythn19UBeZ0CIQD992mOVqAjzYXkI7XF_C1aUrLvqXV0MJ9Eu23W5kHJjA",
   "gpsAccuracy":"20.0",
   "gpsLatitude":"37.421998333333335",
   "gpsLongitude":"-122.08400000000002",
   "osType":"Android"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
   "appVersion":"",
   "clientIp":"",
   "consentName":"Whatsapp",
   "consentStatus":"1",
   "deviceId":"anid:7vpswUwL4EiBjHgqVgTYmoadZSjS4Ffb2xJ8lv69Muc=:fe89",
   "deviceType":"1",
   "fcmId":"eyJhbGciOiJFUzI1NiIsInR5cCI6IkpXVCJ9.eyJhcHBJZCI6IjE6NDc4MzMwOTY1MTQwOmFuZHJvaWQ6NTUxMGQxMGNiM2ZmYjcyZjc0Zjg4MSIsImV4cCI6MTY0NTUwNjQ0NSwiZmlkIjoiZUtMWUVBd2lTNHVfdEJma3J4blBjTCIsInByb2plY3ROdW1iZXIiOjQ3ODMzMDk2NTE0MH0.AB2LPV8wRQIgaRQ06walCsIIlg98E6TEH1MXtlzASbU6Ythn19UBeZ0CIQD992mOVqAjzYXkI7XF_C1aUrLvqXV0MJ9Eu23W5kHJjA",
   "gpsAccuracy":"20.0",
   "gpsLatitude":"37.421998333333335",
   "gpsLongitude":"-122.08400000000002",
   "osType":"Android"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
   "resCode":200,
   "resDesc":"SUCCESS"
}
```
{% endtab %}
{% endtabs %}
