---
description: >-
  This API is used to bind the device to customer. If device binding is not
  completed before the expiry of SMS token, the SMS token will be marked as
  expired.
---

# Device Binding API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/registration/v1/deviceBinding" summary="This API is used to bind the device to customer" %}
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

## Response Details

| Response Field       | Field Description                                         | Data Type   | Length                  |
| -------------------- | --------------------------------------------------------- | ----------- | ----------------------- |
| status               | status of the API                                         | String      | SUCCESS, FAILURE        |
| merchantCustomerId   | Unique id for the merchant as passed in request headers   | String      | Length: 36 characters   |
| customerMobileNumber | Customer mobile number as received from the VMN aggregato |  String     | 12 digits mobile number |
| deviceFingerPrint    | Generated fingerprint for the device used for binding     | String      | Length: 36 characters   |
| udfParameters        | Udf parameters as passed in the request                   | JSON String |                         |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
    "refNumber" : "",
    "mobileNumber" : "9620686057",
    "packageName" : "test.merchant.upi.com",
    "udfParameters" : "",
    "deviceParams" : ""
}
```
{% endtab %}

{% tab title="Second Response" %}
```json
{
  "status": "SUCCESS",
  "responseCode": "SUCCESS",
  "responseMessage": "SUCCESS",
  "payload": {
    "merchantId": "TEST",
    "merchantChannelId": "TESTAPP",
    "merchantCustomerId": "test-merchantcustomer-1",
    "customerMobileNumber": "919988776655",
    "deviceFingerPrint": "d925f3dbcfac7f4531fc0b606cebb7950dac2f0464fe51b53167c4c7a7b5231e"
  },
  "udfParameters": "{}"
} 
```
{% endtab %}

{% tab title="Sample Curl Comand" %}
```json
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
    "refNumber" : "",
    "mobileNumber" : "9620686057",
    "packageName" : "test.merchant.upi.com",
    "udfParameters" : "",
    "deviceParams" : ""
}'
```
{% endtab %}
{% endtabs %}
