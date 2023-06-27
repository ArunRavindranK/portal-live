# Get OTP API

{% swagger method="post" path="" baseUrl="/onboarding/otp/v2/getOTP" summary="" %}
{% swagger-description %}
This API is used to get the OTP
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The response got from the 

[Get Token A](../../../../../../../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpRef" required="true" %}
reference value for the OTP
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "resCode": 200,
        "resDesc": "SUCCESS",
        "resendAttemptsLeft": 2,
        "expireAt": 1651464042000,
        "otpValue": "818643"
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

| Response field     | Field description                                          | Data type |
| ------------------ | ---------------------------------------------------------- | --------- |
| resCode            | response code                                              | Integer   |
| resDesc            | response description                                       | String    |
| resentAttemptsLeft | indicates how much time this API can be invoked to get OTP | Integer   |
| expiryAt           | otp expity time                                            | Long      |
| otpValue           | OTP value                                                  | String    |

#### Response Code

| Response Code | Response Description                        |
| ------------- | ------------------------------------------- |
| ONB001        | Mobile number is mandatory                  |
| ONB002        | Invalid Mobile Number                       |
| ONB003        | Mobile Number Length should be %s digit     |
| ONB042        | Country is mandatory.                       |
| ONB043        | Invalid country code                        |
| ONB006        | OTP Event Type is mandatory.                |
| ONB007        | Otp Ref is mandatory.                       |
| ONB004        | Request could not be processed at this time |
| ONB200        | Success                                     |

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request POST '<domain>/onboarding/otp/v2/getOTP' \
\--header 'X-API-TOKEN;' \
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'Content-Type: text/plain' \
\--data-raw '{
   "otpRef":"b43cbdfa-dd44-4bdf-99c2-65a657289501"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
   "otpRef":"b43cbdfa-dd44-4bdf-99c2-65a657289501"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": ONB200,
    "resDesc": "SUCCESS",
    "data": {
        "resCode": 200,
        "resDesc": "SUCCESS",
        "resendAttemptsLeft": 2,
        "expireAt": 1651464042000,
        "otpValue": "818643"
    }
}
```
{% endtab %}
{% endtabs %}
