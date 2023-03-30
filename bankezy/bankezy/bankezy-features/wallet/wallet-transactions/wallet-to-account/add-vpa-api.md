---
description: >-
  This API creates an alias to an existing vpa. All the accounts liked to
  customerPrimaryVpa will be linked to customerVpa
---

# Add VPA API

{% swagger method="post" path="" baseUrl="/upi-integration/upi/account/v1/addvpa" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobileNumber" required="true" %}
Mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParams" required="true" %}
Stringified JSON for udf parameters
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

| Response Field       | Field Description                                                          | Data Type   | Length                   |
| -------------------- | -------------------------------------------------------------------------- | ----------- | ------------------------ |
| status               | SUCCESS, FAILURE status of the API                                         | String      | Variable, 5–8 characters |
| merchantId           | Unique id for the merchant as passed in request headers                    | String      | Variable, 5–8 characters |
| merchantChannelId    | Unique id for the merchant channel as passed in request headers            | String      | Length: 36 characters    |
| merchantCustomerId   | Merchant generated unique profile id for customer as passed in the request | String      | Length: 36 characters    |
| customerMobileNumber | Customer mobile number                                                     | String      | 12 digits mobile number  |
| vpaAccounts          | Details of the active linked vpa account mappings                          |  array      | VpaAccount               |
| udfParameters        | Udf parameters as passed in the request                                    | JSON string |                          |
|                      |                                                                            |             |                          |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
    "mobileNumbe" : "9620686057",
   "udfParams"  : ""
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
    "status": "SUCCESS",
  "responseCode": "SUCCESS",
  "payload": {
    "merchantId": "TEST",
    "merchantChannelId": "TESTAPP",
    "merchantCustomerId": "test-merchantcustomer-1",
    "customerMobileNumber": "919988776655",
     "vpaAccounts": [{
      "account": {
        "bankCode": "607153",
        "bankName": "PPIPROVIDER",
        "maskedAccountNumber": "XXXX8796",
        "mpinLength": "6",
        "mpinSet": "true",
        "otpLength": "6",
        "atmPinLength": "4",
        "type": "PPIWALLET",
        "ifsc": "PPI00011110",
        "name": "Ram Singh",
        "bankAccountUniqueId": "6adc62db0fcb2d2b8950cc0b4925d1f145df58c3e374e1c3e155b57c12a5c0bf"
      },
      "vpa": "vpa2@handle",
      "isDefault": "true"
    }]
  },
  "udfParameters": "{}"
}


```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'http://localhost:7060/upi-integration/upi/transaction//v1/link/vpa' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{
    "mobileNumbe" : "9620686057",
   "udfParams"  : ""
}

'
```
{% endtab %}
{% endtabs %}
