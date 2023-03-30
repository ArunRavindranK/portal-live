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

| Response Field                        | Field Description                                           | Data Type | Length                   |
| ------------------------------------- | ----------------------------------------------------------- | --------- | ------------------------ |
| status                                | SUCCESS, FAILURE status of the API                          | String    | Variable, 5–8 characters |
| vpa                                   | vpa handle                                                  | String    | Variable                 |
| <pre><code>isPrimaryVpa
</code></pre> | <p>0 - It's not primary vap <br><br>1 - It's primay vpa</p> | Integer   | Length: 1                |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
  
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
  "status": "SUCCESS",
  "resCode": "200",
  "resDesc": "VPA details fetched successfully",
  "data": [{
    "vpa":"99911199.citrus@payu",
    "isPrimaryVpa":1,
    },
    {
    "vpa":"testing@payu",
    "isPrimaryVpa":0,
    }]
} 
```
{% endtab %}

{% tab title="Sample Curl Command" %}
<pre class="language-json"><code class="lang-json">curl --location --request POST 'http://https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/lookup/v1/search' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
<strong>\--header 'X-MOBILE-NUMBER': 99911199
</strong>\--header 'Content-Type: text/plain'
--data-raw '{
}'
</code></pre>
{% endtab %}
{% endtabs %}
