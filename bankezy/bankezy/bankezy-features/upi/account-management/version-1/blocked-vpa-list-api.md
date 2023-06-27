# Blocked VPA list API

{% swagger method="post" path="" baseUrl="http://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/accountmanagement/v1/vpa/blockedvpalist" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pageno" required="true" type="int" %}
page number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pageSize" type="int" required="true" %}
size of total page
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

| Response code | Response description  |
| ------------- | --------------------- |
| UPI24         | Failure to fetch list |

{% tabs %}
{% tab title="Sample CURL request" %}
```json
curl --location 'http://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/transaction/v2/sendMoney' \
--header 'x-program-id: 2001' \
--header 'x-account-number: 3199' \
--header 'Content-Type: application/json' \
--data-raw '{
  "pageno": 1,
  "pageSize": 2
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
  "pageno": 1,
  "pageSize": 2
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
    "resCode": UPI200",
    "resDesc": "SUCCESS",
    "data": [
        {
            "id": 2,
            "accountNumber": "123",
            "vpa": null,
            "blockedVpa": "test3@payu.co",
            "blockedVpaName": "test3"
            "updatedTs": null,
            "createdTs": null
        },
        {
            "id": 104,
            "accountNumber": "123",
            "vpa": null,
            "blockedVpa": "test2@payu.co",
            "blockedVpaName": "test2"
            "updatedTs": null,
            "createdTs": null
        },
        {
            "id": 105,
            "accountNumber": "123",
            "vpa": null,
            "blockedVpa": "test1@payu.co",
            "blockedVpaName": "test1"
            "updatedTs": null,
            "createdTs": null
        }
    ]
}
```
{% endtab %}
{% endtabs %}
