---
description: >-
  This API will start the device binding process and return an SMS token. The
  SMS token will provide the SMS text and the virtual mobile number(VMN) for the
  SMS to be sent from customer device.
---

# UPI Registration SMS Token API



{% swagger method="post" path="" baseUrl="/upi-integration/upi/registration/smstoken/v1" summary="The API will be provide the Text SMS to be send from customer device " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="serviceProvider" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" required="false" %}

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

## Response Details

<table><thead><tr><th width="209">Response Field</th><th width="204">Field Description</th><th>Data Type</th><th width="125">Length</th></tr></thead><tbody><tr><td>resCode</td><td>SUCCESS, FAILURE status of the API</td><td>int</td><td></td></tr><tr><td>resDesc</td><td></td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>refId</td><td>Unique auto generated id to record user registration</td><td>BigInteger</td><td></td></tr><tr><td>smsContent</td><td>SMS content to be passed to the service provider to bind the device</td><td>String</td><td></td></tr><tr><td>serviceProviders</td><td>Array of VMNs that can be used for device binding for this token</td><td>Array of Service Provider object</td><td></td></tr></tbody></table>

| Response Field     | Field Description                              | Data Type |
| ------------------ | ---------------------------------------------- | --------- |
| ServiceProvider    |                                                |           |
|             name   | Name of  the  service provider configured      | String    |
|             number | Number of  the  service provider to send SMS   | String    |

{% tabs %}
{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'http://localhost:7060/upi-integration/upi/v1/registration/smstoken' \
\--header 'Content-Type: text/plain'
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
--data-raw '{
    "serviceProvider":"T-Mobile"
    "udfParameters": ""
}'
```
{% endtab %}

{% tab title="Sample Request" %}
```json
{
 "serviceProvider":"T-Mobile"
 }
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
    "resCode": "200",
    "resDesc": "SUCCESS",
    "data": {
        "refId": "540",
        "smsContent": "UATPAYUUPI ppmrU0Y3MBFFsPZtyln0duJ2T1hjejWuw&1fQ",
        "serviceProviders": [
            {
                "number": "09266801939",
                "name": "vodafone"
            }
        ]
    }
}
```
{% endtab %}
{% endtabs %}

