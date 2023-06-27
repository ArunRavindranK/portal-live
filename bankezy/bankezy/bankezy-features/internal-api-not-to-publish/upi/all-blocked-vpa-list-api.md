---
description: >-
  This API will be used to list all the VPAs that were blocked so far by the
  customer.
---

# All Blocked VPA List API

{% swagger method="get" path="" baseUrl="/upi-integration/upi/accountmanagement/v1/vpa/fetchallblockedvpalist" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" required="true" name="X-API-TOKEN" %}
MOB-APP-2001
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

| Response Field | Field Description                     | Data Type |
| -------------- | ------------------------------------- | --------- |
| id             |                                       | Integer   |
| vpa            | Vpa handle                            | String    |
| blockedVpaName | name of the vpa account holder if any | String    |
| accountNumber  | User unique identification number     | String    |
| blockedVpa     | vpa handle of the blocked account     | String    |
| updatedTs      | record updated time                   | long      |
| createdTs      | account created time                  | long      |

{% tabs %}
{% tab title="Sample Response" %}
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
curl --location 'http://localhost:7060/upi-integration/upi/accountmanagement/v1/vpa/fetchallblockedvpalist' \
--header 'X-API-TOKEN:  replace-with-actual-token' \
--header 'X-API-KEY:  MOB-APP-2001'
```
{% endtab %}
{% endtabs %}
