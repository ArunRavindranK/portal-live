---
description: >-
  This API helps us to Generate a Static or Dynamic QR string static and dynamic
  QR. Merchant enters the amount and transaction remarks.
---

# Generate QR



{% swagger method="post" path="/merchant-payments/v1/generateqr'" baseUrl="<domain>" summary="Generate QR" %}
{% swagger-description %}
This api will generate qr for the Merchant payments 
{% endswagger-description %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" type="String" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="body" name="qrFormat" type="String" required="true" %}
QR format
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" type="String" required="true" %}
Transaction type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="purpose" type="String" required="true" %}
Purpose
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mode" type="String" required="true" %}
Mode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="am" type="String" required="true" %}
Transaction amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="qrMedium" required="true" type="String" %}
Qr Medium
{% endswagger-parameter %}

{% swagger-parameter in="body" name="client" required="true" type="String" %}
client
{% endswagger-parameter %}

{% swagger-parameter in="body" name="channel" required="true" type="String" %}
channel
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnSubType" required="true" type="String" %}
Transaction Sub type 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tn" type="String" required="true" %}
Transaction Notes
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tr" type="String" required="true" %}
Transaction Reference
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mam" type="String" required="true" %}
Min amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cu" type="String" required="true" %}
Currency
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN " type="String" required="true" %}
The token got from the login API
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

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/merchant-payments/v1/generateqr' \
--header 'X-API-KEY: MOB-APP1-1114' \--header 'X-API-TOKEN: token' \
--header 'Content-Type: application/json' \
--header 'Cookie: __cfruid=d8c705185ddb428e8ff98f551c807540c4f46117-1673865636; JSESSIONID=DC392599DE2882D53CD7BE62321D73B6; JSESSIONID=FA8665A348AC9F06EAD159DA259BB58F' \
--data-raw '{
    "qrFormat": "06",
    "txnType": "CBDC",
    "purpose": "11",
    "mode": "22",
    "am": 1267,
    "qrMedium": "06"
}'

```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "qrFormat": "06",
    "txnType": "CBDC",
    "purpose": "11",
    "mode": "22",
    "am": 1267,
    "qrMedium": "06"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode":"200",
  "resDesc":"QrCode data successfully generated",
  "data:"DigitalRupee://pay?ver=01&mode=11&purpose=19&pa=merchant1@upi&pn=MERCHANT1&mc=5611&mid=1001&mtid=1&qrMedium=06&pincode=600113&am=100"
  }
```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>MERP_2000</td><td>SUCCESS</td></tr><tr><td>MER_4001</td><td>Merchant information missing,try later</td></tr><tr><td>MER_4001</td><td>Merchant config missing,try later</td></tr><tr><td>MER_4001</td><td>Unable to generate rawstring,contact supervisor for configurations!!</td></tr><tr><td>MER_4001</td><td>Internal server error</td></tr></tbody></table>

## &#x20;
