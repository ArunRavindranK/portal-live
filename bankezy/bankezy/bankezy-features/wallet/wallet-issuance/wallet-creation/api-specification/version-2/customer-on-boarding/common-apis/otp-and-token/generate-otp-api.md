---
description: This API is used to generate OTP
---

# Generate OTP API



{% swagger method="post" path="" baseUrl="<domain>/onboarding/otp/v2/generateOTP" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The response got from the 

[Get Token API](../../../../version-1/customer-on-boarding/common-apis/get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="Content-Type" %}
text/plain
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" required="true" %}
10 digit mobile number is mandatory
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpEventType" required="true" %}
ENROLL
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":{
      "otpRef":"b43cbdfa-dd44-4bdf-99c2-65a657289501",
      "otpVal":"507471",
      "mobile":"7000000002"
   }
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
{% endswagger %}

## Response Details

| Response field | Field description    | Data type |
| -------------- | -------------------- | --------- |
| otpRef         | trace id to find OTP | String    |
| otpVal         | 6 digit otp value    | String    |
| mobile         | user mobile number   | String    |

#### Response Code

| Response Code | Response Description                        |
| ------------- | ------------------------------------------- |
| ONB001        | Mobile number is mandatory                  |
| ONB002        | Invalid Mobile Number                       |
| ONB003        | Mobile Number Length should be %s digit     |
| ONB006        | OTP Event type is mandatory                 |
| ONB004        | Request could not be processed at this time |
| ONB200        | Success                                     |

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request POST '<domain>/onboarding/otp/v2/generateOTP'
\--header 'X-API-TOKEN; token'
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'Content-Type: text/plain'
--data-raw '{ "mobile":"7000000002", "otpEventType":"ENROLL" }'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
   "mobile":"7000000002",
   "otpEventType":"ENROLL"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
   "resCode":ONB200,
   "resDesc":"SUCCESS",
   "data":{
      "otpRef":"b43cbdfa-dd44-4bdf-99c2-65a657289501",
      "otpVal":"507471",
      "mobile":"7000000002"
   }
}
```
{% endtab %}
{% endtabs %}
