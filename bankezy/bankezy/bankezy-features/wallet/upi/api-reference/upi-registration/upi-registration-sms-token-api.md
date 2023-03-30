---
description: >-
  This API will start the device binding process and return an SMS token. The
  SMS token will provide the SMS text and the virtual mobile number(VMN) for the
  SMS to be sent from customer device.
---

# UPI Registration SMS Token API



{% swagger method="post" path="" baseUrl="/upi-integration/upi/registration/v1/smstoken" summary="The API will be provide the Text SMS to be send from customer device " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
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

| Response Field     | Field Description                                                          | Data Type                 | Length                   |
| ------------------ | -------------------------------------------------------------------------- | ------------------------- | ------------------------ |
| Status             | SUCCESS, FAILURE status of the API                                         | String                    | Variable, 5–8 characters |
| merchantId         | Unique id for the merchant as passed in request headers                    | String                    | Variable, 5–8 characters |
| merchantChannelId  | Unique id for the merchant channel as passed in request headers            | String                    | Length: 36 characters    |
| merchantCustomerId | Merchant generated unique profile id for customer as passed in the request | String                    | Length: 36 characters    |
| serviceProviders   | Array of VMNs that can be used for device binding for this token           | Array of object           |                          |
| name               | Name of the VMN service provider like Vodafone, Airtel                     | String                    | Variable, 5–8 characters |
| number             | Number of the VMN servie provider                                          | Numeric String            |                          |
| smsContent         | SMS content to be used for device binding for this token                   | String                    | Variable, 5–8 characters |
| expiryTimestamp    | Expiry timestamp for the SMS token                                         | YYYY-MM-DDTHH:MM:SS+05:30 |                          |
| udfParameters      | Udf parameters as passed in the request                                    | String                    | Variable, 5–8 characters |

{% tabs %}
{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'http://localhost:7060/upi-integration/upi/v1/registration/smstoken' \
\--header 'Content-Type: text/plain'
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
--data-raw '{
    "serviceProvider": "Vodafone",
    "udfParameters": ""
}'
```
{% endtab %}

{% tab title="Sample Request" %}
```json
{ 
    "serviceProvider": "Vodafone",
    "udfParameters": ""
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
  "status": "SUCCESS",
  "responseCode": "SUCCESS",
  "responseMessage": "SUCCESS",
  "payload": {
    "merchantId": "TEST",
    "merchantChannelId": "TESTAPP",
    "merchantCustomerId": "test-merchantcustomer-1",
    "serviceProviders": [{
      "name": "Vodafone",
      "number": "09988776655"
    },{
      "name": "Airtel",
      "number": "09876543210"
    }]
    "smsContent": "UPIACT ad56ef90396348bac56099",
    "expiryTimestamp": "2017-06-09T17:57:49+05:30"
  },
  "udfParameters": "{}"
}
```
{% endtab %}
{% endtabs %}

