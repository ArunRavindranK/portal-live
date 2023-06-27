# Device validation API

This API is used to identidy whether app force update is required or not also this api tells user is using same device or new device.  If the user is using new device then based on KYC level it will return authentication mode

{% swagger method="post" path="" baseUrl="<domain>/onboarding/user/deviceValidation/v1" summary="" %}
{% swagger-description %}
This API is used to identify if app force update is required and if user is using different device then based on KYC level, this API will return authentication mode
{% endswagger-description %}

{% swagger-parameter in="body" name="appVersion" required="true" %}
Application version currently user is using
{% endswagger-parameter %}

{% swagger-parameter in="body" name="osType" required="true" %}
Type of the OS either Android or iOS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="true" %}
Device unique id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[Get Token API](../../../../../../../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "authenticationMode": 1,
        "appUpdateRequired": false
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

## Response Details

| Response Fields    | Field description                | Data type |
| ------------------ | -------------------------------- | --------- |
| authenticationMode | user credential screen           | Integer   |
| appUpdateRequired  | app force update required or not | Boolean   |

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request POST 'http://localhost:10000/onboarding/user/deviceValidation/v1' \
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0.._RA3z-Y4pkwPgXze.pMpkY7bSU8NhOTjcStl725tvHk88oF3ZV78VqVy-piPXpTKTYOW0BbBTaerdl0PGWBc51At218RFQ-aD-sNrmABVpW8Mz5y-8-r-AqL6sqJe_v4_J6iXRRNdQBAUKdljP8R9Gq_uSkZFCD99cBbbSrUoWHWY-7CcS3Uxbl6248EIaPj2XEFi1kQcCjT36ACwrnPZaFD7XeTtBw.SMEtkiIyesQYBwE_9QZBew'
\--header 'Content-Type: text/plain'
\--data-raw '{
    "appVersion": "2.09.00.00",
    "osType": "Android",
    "deviceId":"anid:AloZHNC6ehWfiK4lgVoNIsq3wRGpIe5y8sGJn/ey8Ws=:1ffe"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "appVersion": "2.09.00.00",
    "osType": "Android",
    "deviceId":"anid:AloZHNC6ehWfiK4lgVoNIsq3wRGpIe5y8sGJn/ey8Ws=:1ffe"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "authenticationMode": 1,
        "appUpdateRequired": false
    }
}
```
{% endtab %}
{% endtabs %}
