---
description: This API can be used to fetch the VPA Details.
---

# UPI Lookup API



{% swagger method="post" path="" baseUrl="/upi-integration/upi/registration/v1/status" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ssid" required="true" %}
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

## Response Details

<table><thead><tr><th width="248">Response Field</th><th>Field Description</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>vpaStatus</td><td></td><td>List&#x3C;VpaStatus></td><td>Variable</td></tr><tr><td>vpa</td><td>data inside vpaStatus pojo - vpa handle</td><td>String</td><td>Variable</td></tr><tr><td>isIsPrimary</td><td>data inside vpaStatus pojo - 0 - it's not primary vpa                  1 - it's a primary vpa</td><td>Integer</td><td>1</td></tr><tr><td>isIsValidateDeviceBinding</td><td>vpa handle</td><td>boolean</td><td>true or false</td></tr><tr><td>bankAccountNumber</td><td>customer bank account number</td><td>Sting</td><td>12 digit</td></tr><tr><td>bankIfsc</td><td>bank unique IFSC code</td><td>String</td><td></td></tr></tbody></table>



{% tabs %}
{% tab title="Sample Request" %}
<pre class="language-json"><code class="lang-json"><strong>{
</strong><strong>    "ssid" : [],
</strong><strong>    "deviceId": ""
</strong><strong>}
</strong></code></pre>
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
curl --location 'http://localhost:7060/upi-integration/upi/registration/v1/status' \
--header 'X-API-TOKEN:  replace-with-actual-token' \
--header 'X-API-KEY:  MOB-APP-2001' \
--header 'Content-Type: application/json' \
--data '{
    "ssid" : [],
    "deviceId": ""
}'
```
{% endtab %}
{% endtabs %}
