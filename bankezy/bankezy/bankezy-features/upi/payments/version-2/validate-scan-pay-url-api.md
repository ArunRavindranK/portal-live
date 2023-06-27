# Validate scan pay url API

{% swagger method="post" path="" baseUrl="<domain>/upi-integration/upi/transaction/v2/validateUrl" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="url" required="true" %}
url
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" required="true" %}
user definded parameters
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

## Custom response codes

| Response code | Response description                    |
| ------------- | --------------------------------------- |
| UPI29         | UPI Vendor Not Found                    |
| UPI504        | Server timeout or Gateway Timeout error |
| UPI100        | FAILURE                                 |

{% tabs %}
{% tab title="Sample CURL request" %}
```
curl --location 'http://bankezy-azure.pcdev.enstage-sas.comupi-integration/upi/transaction/v2/validateUrl' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: <user-proper-tokem>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "url": "upi://pay?pa=test@mypsp&pn=3dqc8tkr2kb&tn=SignedIntentTesting&am=&mam=null&cu=INR&tr=UPITestHelper1&mode=00&orgid=158002&sign=MEUCIQDfuE08NavtqTAeOW+WBwDuFBUa83KGipzmyWeOOQZd8wIgFfRY6jwtty0WleXUT2Ir4jnfHpa59K4ZB8SVsd+R6JE=",
    "udfParameters": "{}"
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
    "url": "upi://pay?pa=test@mypsp&pn=3dqc8tkr2kb&tn=SignedIntentTesting&am=&mam=null&cu=INR&tr=UPITestHelper1&mode=00&orgid=158002&sign=MEUCIQDfuE08NavtqTAeOW+WBwDuFBUa83KGipzmyWeOOQZd8wIgFfRY6jwtty0WleXUT2Ir4jnfHpa59K4ZB8SVsd+R6JE=",
    "udfParameters": "{}"
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{   
"resCode": 200,   
"errorMessage": "SUCCESS"
}
```
{% endtab %}
{% endtabs %}
