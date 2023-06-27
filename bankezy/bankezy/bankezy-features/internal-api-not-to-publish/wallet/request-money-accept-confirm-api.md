---
description: >-
  Request Money Accept confirm API: It applies only for UPI-UPI transfer mode,
  if users accepts the payment.
---

# Request Money Accept confirm API



{% swagger method="post" path="" baseUrl="<domain>/wallet/rm/accept/confirm/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="appName" type="String" required="true" %}
​Application Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="capability" type="String" required="true" %}
​Capability
{% endswagger-parameter %}

{% swagger-parameter in="body" name="credentialDataCode" type="String" required="true" %}
​Credenrial Data code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="credentialDataKi" type="String" required="true" %}
​Credential Data Ki
{% endswagger-parameter %}

{% swagger-parameter in="body" name="credentialDataValue" type="String" required="true" %}
Credential Data Value
{% endswagger-parameter %}

{% swagger-parameter in="body" name="credentialSubType" type="String" required="true" %}
Credential Sub Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="credentialType" type="String" required="true" %}
Credential Type 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="  deviceId" type="String" required="true" %}
Device ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name=" deviceName" type="String" required="true" %}
​Device Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceType" type="String" required="true" %}
Device Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="geoCode" type="String" required="true" %}
Geo Code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ip" type="String" required="true" %}
IP Address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="location" type="String" required="true" %}
​Location
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobileNo" type="String" required="true" %}
Mobile Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="msgHash" type="String" required="true" %}
Message Hash
{% endswagger-parameter %}

{% swagger-parameter in="body" name="npciTxnId" type="String" required="true" %}
NPCI Transaction ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="os" type="String" required="true" %}
​OS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pspId" type="String" required="true" %}
​PSP ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="reqPspRefNo" type="String" required="true" %}
​Requirement Psp Reference Number 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="simId" type="String" required="true" %}
SIM ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="token" type="String" required="true" %}
​Token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="upiTxnRefNo" type="String" required="true" %}
UPI Transaction Reference Number
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
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
{% endswagger %}

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/rm/accept/confirm/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw '{ "appName": "string", "capability": "string", "credentialDataCode": "string", "credentialDataKi": "string", "credentialDataValue": "string", "credentialSubType": "string", "credentialType": "string", "deviceId": "string", "deviceName": "string", "deviceType": "string", "geoCode": "string", "ip": "string", "location": "string", "mobileNo": "string", "msgHash": "string", "npciTxnId": "string", "os": "string", "pspId": "string", "reqPspRefNo": "string", "simId": "string", "token": "string", "upiTxnRefNo": "string" }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}


```json
{
  "appName": "string",
  "capability": "string",
  "credentialDataCode": "string",
  "credentialDataKi": "string",
  "credentialDataValue": "string",
  "credentialSubType": "string",
  "credentialType": "string",
  "deviceId": "string",
  "deviceName": "string",
  "deviceType": "string",
  "geoCode": "string",
  "ip": "string",
  "location": "string",
  "mobileNo": "string",
  "msgHash": "string",
  "npciTxnId": "string",
  "os": "string",
  "pspId": "string",
  "reqPspRefNo": "string",
  "simId": "string",
  "token": "string",
  "upiTxnRefNo": "string"
}
```
{% endtab %}

{% tab title="Response" %}
```jsdoc
```
{% endtab %}
{% endtabs %}
