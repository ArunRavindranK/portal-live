# Search Account API

{% swagger method="post" path="" baseUrl="<domain>/wallet/v2/searchaccounts" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" type="String" required="true" %}
​mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productType" type="Int" required="false" %}
product type
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="201: Created" description="" %}
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

## Custom response code

| Response code | Response description                               |
| ------------- | -------------------------------------------------- |
| WAL30         | Card Not found                                     |
| WAL14         | INTERNAL ERROR                                     |
| WAL39         | product type is empty                              |
| WAL29         | Mobile# or Customer Id is Mandatory                |
| WAL166        | wallet card and VPA details retrieved successfully |
| WAL167        | Error in fetching customer vpa details             |
| WAL195        | Vpa is not present or unable to fetch              |

{% tabs %}
{% tab title="Sample CURL request" %}
```json
curl --location 'http://localhost:7060/
/wallet/v2/searchaccounts' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: replace-proper-token' \
--header 'Content-Type: application/json' \
--data '{
    "mobile":"12345657800"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "mobile":"12345657800"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": "WAL200",
  "resDesc": "Success",
  "data": {
    "isWalletAvailable":true,
    "recipientName":"test1",
    "vpaDetails":[
      {
        "vpa":"1234567890@payu.co",
        "isPrimaryVpa":"true"
      },
      {
        "vpa":"1234567890-1@payu.co",
        "isPrimaryVpa":"false"
      }
    ]
  }
}

```
{% endtab %}
{% endtabs %}
