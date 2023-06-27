---
description: >-
  This API helps the user to enable/disable the specific notification with
  respect to text, speech etc
---

# Enable Notification

{% swagger method="post" path="/mrch-management/v1/notifyupdate" baseUrl="<domain>" summary="Enable/Disable Notification" %}
{% swagger-description %}
This api is used to update the notification option required.
{% endswagger-description %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" type="String" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sms" %}
Enable/Disable Sms


{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" %}
Enable/Disable Email
{% endswagger-parameter %}

{% swagger-parameter in="body" name="push" %}
Enable/Disable  Push
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sticky" %}
Enable/Disable Sticky Notes
{% endswagger-parameter %}

{% swagger-parameter in="body" name="voice " %}
Enable/Disable Voice alert
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="speaker" type="String" required="false" %}
Enable/Disable Speaker
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

curl --location --request POST 'http://user4.pcdev.enstage-sas.com/kong/mrch-management/v1/notifyupdate' \
--header 'X-API-KEY: MOB-APP1-1114' \
--header 'X-API-TOKEN: token' \
--header 'Content-Type: application/json' \
--data-raw '{

"sms" : "1"

}'

```
{% endtab %}

{% tab title="Request sample" %}
```json
{

"sms" : "1"

}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "MER_2000",
    "resDesc": "SUCCESS"
}
```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>MER_2000</td><td>SUCCESS</td></tr><tr><td>MER_4001</td><td>Unable to update notification settings</td></tr><tr><td>MER_5000</td><td>Try Later</td></tr></tbody></table>

## &#x20;
