---
description: >-
  This callback API will be called by SMS vendor in order to verify the payload
  received by them.
---

# Validate Payload API



{% swagger method="post" path="" baseUrl="<domain>/onboarding/user/auth/validatePayLoad/v1" summary="" %}
{% swagger-description %}
This is the sequential API for sim and device binding. API. This API will be invoked by the SMS Vendor. Below are the previous steps

Generate Public Key. [Learn More](broken-reference)

Save Encrypted payload. [Learn More](save-encrypted-payload-api.md)
{% endswagger-description %}

{% swagger-parameter in="header" name="X-BASIC-AUTH" required="true" %}
Base 64 encoded (api key : secret). api key and secret will shared offline.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="senderNumber" required="true" %}
mobile number of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="smsbody" required="true" %}
SMS Body 
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" type="String" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="circleid" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="timestamp" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="longcode" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="keyword" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="subkeyword" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="carrierid" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
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
curl --location --request POST 'https://api-pz1.pc.enstage-sas.com/onboarding/user/auth/validatePayLoad/v1' \
\--header 'X-API-TOKEN: Token'
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'Content-Type: text/plain'
\--data-raw '{
    "senderNumber": "8050880123",
    "smsbody": "QA:1111:202204BsS3BMOev1:1111|7234|[C@633d27b5"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "senderNumber": "8050880123",
    "smsbody": "QA:1111:202204BsS3BMOev1:1111|7234|[C@633d27b5",
    "shortcode": "878007",
    "provider": "Airtel",
    "carrierid": "Karnataka",
    "timestamp": "25-02-2022 4: 42 PM"
}
```
{% endtab %}
{% endtabs %}

