---
description: User entered OTP is verified with the server.
---

# Verify Aadhaar OTP API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/ekyc/v2/aadhaar/verify/otp" summary="" %}
{% swagger-description %}
verifying otp which is sent to aadhar linked mobile number. Bankezy will send request to vendor to verify OTP
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="traceId" required="true" %}
TraceId from 

[verify Aadhar API](../../../../../version-1/customer-on-boarding/api-specification/non-bank-customer-kyc-process/ekyc-process/verify-aadhar-api.md)

 response
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otp" required="true" %}
Otp received from user mobile
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "Success",
    "data": {
        "name": "abcdef",
        "gender": "M",
        "dob": "2000-02-02",
        "fatherName": "sgfhdjfjfj",
        "address": {
            "combinedAddress": "sdgdfhdhdfjfgjfjfj jtutjtgjfgj",
            "splitAddress": {
                "country": "India",
                "district": "Banglaore",
                "houseNumber": "#38",
                "landmark": null,
                "location": "Marathalli",
                "pincode": "577444",
                "postOffice": "Marathalli",
                "state": "Karnataka",
                "street": "Rajaji Nagara",
                "subdistrict": "Marathalli",
                "vtcName": "Marathalli"
            }
        },
        "aadharNumber": "XXXX XXXX 7090"
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

| Response Field | Field Description       | Data Type |
| -------------- | ----------------------- | --------- |
| otp            | otp entered by the used | Integer   |
| traceId        | original otp trace id   | String    |

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request POST 'http://localhost:8083/onboarding/ekyc/v1/aadhaar/verify/otp' \
\--header 'Content-Type: text/plain'
\--header 'X-ACCOUNT-NUMBER: 312'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Cookie: JSESSIONID=C0D114845B4EC3A92A840A1B862E96F4' \
--data-raw '{
"otp": 817919,
"traceId": "4e932354-e57d-4e67-80f2-6b669ed906cd"
}
'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
"otp": 817919,
"traceId": "4e932354-e57d-4e67-80f2-6b669ed906cd"
}

```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "ONB200",
    "resDesc": "Success",
    "data": {
        "name": "abcdef",
        "gender": "M",
        "dob": "2000-02-02",
        "fatherName": "sgfhdjfjfj",
        "address": {
            "combinedAddress": "sdgdfhdhdfjfgjfjfj jtutjtgjfgj",
            "splitAddress": {
                "country": "India",
                "district": "Banglaore",
                "houseNumber": "#38",
                "landmark": null,
                "location": "Marathalli",
                "pincode": "577444",
                "postOffice": "Marathalli",
                "state": "Karnataka",
                "street": "Rajaji Nagara",
                "subdistrict": "Marathalli",
                "vtcName": "Marathalli"
            }
        },
        "aadharNumber": "XXXX XXXX 7090"
    }
}
```
{% endtab %}
{% endtabs %}

