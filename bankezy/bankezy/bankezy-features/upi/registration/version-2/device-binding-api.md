---
description: >-
  This API is used to bind the device to customer. If device binding is not
  completed before the expiry of SMS token, the SMS token will be marked as
  expired.
---

# Device Binding API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/registration/v2/deviceBinding" summary="This API is used to bind the device to customer" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="refNumber" type="BigInteger" %}
Reference Number
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="mobileNumber" %}
Mobile Number of the customer
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="packageName" %}
Package name of the UPI application
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="udfParameters" %}
Stringified JSON for udf parameters
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="deviceId" %}
Unique identifier for the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="manufacturer" required="true" %}
Manufacturer of the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="model" required="true" %}
Model of the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="version" required="true" %}
Version of the operating system on the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="os" required="true" %}
Operating system running on the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ssid" required="true" %}
Identifier of the SIM used to send the SMS
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

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

#### Response Details

<table><thead><tr><th width="238">Response Field</th><th width="205">Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>status of the API</td><td>int</td><td></td></tr><tr><td>resDesc</td><td></td><td>String</td><td>SUCCESS, FAILURE</td></tr><tr><td>refNumber</td><td></td><td>BigInteger</td><td></td></tr><tr><td>status</td><td></td><td>String</td><td></td></tr></tbody></table>

#### Response code

| ResponseCode | ResponseDesc                                          |
| ------------ | ----------------------------------------------------- |
| UPI04        | Device binding success                                |
| UPI05        | Device Bining failed due to SMS token expired         |
| UPI06        | Creating VPA and linking account                      |
| UPI07        | Server error. Please try after sometime               |
| UPI08        | Invalid sms content                                   |
| UPI09        | Device Binding failed. Please use valid mobile number |
| UPI100       | FAILURE                                               |

## Response Details

<table><thead><tr><th width="238">Response Field</th><th width="205">Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>status of the API</td><td>int</td><td></td></tr><tr><td>resDesc</td><td></td><td>String</td><td>SUCCESS, FAILURE</td></tr><tr><td>refNumber</td><td></td><td>BigInteger</td><td></td></tr><tr><td>status</td><td></td><td>String</td><td></td></tr></tbody></table>



{% tabs %}
{% tab title="Sample Request" %}
```json
{
    "deviceParams": {
        "os": "Android",
        "deviceId": "810b328ca8e7c4c3",
        "manufacturer": "Google",
        "version": "11",
        "ssid": "1810b328ca8e7c4c3",
        "model": "sdk_gphone_x86"
    },
    "packageName": "com.wibmo.wibmo_banking.bankezy.dev",
    "refNumber": "541",
    "mobileNumber": "9566115998"
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
    "resCode": "203",
    "resDesc": "Device binding success",
    "data": {
        "refNumber": "1",
        "status": "Device binding success"
    }
}
```
{% endtab %}

{% tab title="Sample Curl Comand" %}
```json
curl --location 'http://localhost:7060/upi-integration/upi/registration/v2/deviceBinding' \
--header 'X-API-TOKEN: token' \
--header 'X-API-KEY: MOB-APP-2001' \
--header 'Content-Type: application/json' \
--data '{
    "deviceParams": {
        "os": "Android",
        "deviceId": "810b328ca8e7c4c3",
        "manufacturer": "Google",
        "version": "11",
        "ssid": "1810b328ca8e7c4c3",
        "model": "sdk_gphone_x86"
    },
    "packageName": "com.wibmo.wibmo_banking.bankezy.dev",
    "refNumber": "541",
    "mobileNumber": "9566115998"
}'
```
{% endtab %}
{% endtabs %}
