---
description: This API can be used to check the status of  Device Binding.
---

# UPI Registration Status Inquiry API



{% swagger method="post" path="" baseUrl="/upi-integration/upi/registration/v2/status" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ssid" required="true" type="List<String>" %}
Identifier of the SIM used to send the SMS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="true" %}
Unique identifier for the device
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

| ResponseCode | ResponseDesc                    |
| ------------ | ------------------------------- |
| UPI200       | SUCCESS                         |
| UPI119       | Please try again after sometime |
|              |                                 |

## Response Details

<table><thead><tr><th width="248">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td></td><td>int </td><td></td></tr><tr><td>resDesc</td><td><code>SUCCESS, FAILURE status of the API</code></td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>isValidateDeviceBinding</td><td>Indicates if user's device is binded or not</td><td>boolean</td><td></td></tr><tr><td>vpaStatus</td><td></td><td>List&#x3C;VpaStatus></td><td></td></tr><tr><td>bankAccountNumber</td><td></td><td>String</td><td>Length: 20 characters</td></tr><tr><td>bankIfsc</td><td>Customer mobile number</td><td>String</td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Request" %}
```json
{
  "ssid" :  ["1c776e05188a0f27c"],   
   "deviceId": "8991000903658589244"
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
  "resCode": 200,
  "resDesc": "SUCCESS",
  "data": {  
    "isIsValidateDeviceBinding": false,
    "bankAccountNumber":"1234",
    "bankIfsc":"HDFC000111",
    "vpaStatus": [{
      "vpa":"99911199.citrus@payu",
      "isPrimaryVpa":1,
      },
      {
      "vpa":"testing@payu",
      "isPrimaryVpa":0,
      }]
    }
} 
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/registration/v2/status' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
  "ssid" :  ["1c776e05188a0f27c"],   
   " deviceId": "8991000903658589244"
}'
```
{% endtab %}
{% endtabs %}
