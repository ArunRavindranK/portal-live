---
description: >-
  This API will be used to list all the VPAs that were blocked so far by the
  customer it supports pagination.
---

# Blocked VPA List API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/accountmanagement/v1/vpa/blockedvpalist" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" required="true" name="X-API-TOKEN" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pageno" required="true" %}
Page number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="PageSize" required="true" %}
page size
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

| Response Field | Field Description                | Data Type              |
| -------------- | -------------------------------- | ---------------------- |
| accountNumber  | user identification number       | String                 |
| id             | urn                              | int                    |
| vpa            | vpa                              | String                 |
| blockedVpa     | vpa of the account               | String                 |
| blockedVpaName |                                  | name of the vpa if any |
| updatedTs      | last updated time of the recored | long                   |
| createdTs      | time when record is created      | long                   |



{% tabs %}
{% tab title="Sample Request" %}
```json
{
  "pageno" :5,
  "PageSize":5
}
```
{% endtab %}

{% tab title="Second Tab" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": [
        {
            "id": 5,
            "accountNumber": "2381",
            "vpa": null,
            "blockedVpa": "8010111183.bankezy@payu",
            "blockedVpaName": null,
            "updatedTs": null,
            "createdTs": 1657613380000
        },
        {
            "id": 1,
            "accountNumber": "2381",
            "vpa": null,
            "blockedVpa": "8892239833.bankezy@payu",
            "blockedVpaName": null,
            "updatedTs": null,
            "createdTs": 1657611087000
        },
        {
            "id": 4,
            "accountNumber": "2381",
            "vpa": null,
            "blockedVpa": "9988776655.bankezy@payu",
            "blockedVpaName": null,
            "updatedTs": null,
            "createdTs": 1657613339000
        }
    ]
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'http://localhost:7060/upi-integration/upi/accountmanagement/v1/vpa/blockedvpalist' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
  "pageno" :5,
  "PageSize":5
}'
```
{% endtab %}
{% endtabs %}
