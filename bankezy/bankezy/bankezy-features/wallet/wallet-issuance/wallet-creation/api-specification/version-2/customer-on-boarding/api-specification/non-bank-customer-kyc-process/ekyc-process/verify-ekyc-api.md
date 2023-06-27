---
description: API to verify the entered Aadhar details.
---

# Verify EKYC API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/ekyc/v2/aadhaar/userConfirmation" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" required="true" %}
Name as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gender" required="true" %}
Gender as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="dob" required="true" %}
Dob as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fatherName" required="true" %}
Father name as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" required="true" %}
Address as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address.combinedAddress" required="true" %}
Address as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address.splitAddress.country" required="true" %}
Address as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address.splitAddress.district" required="true" %}
Address as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address.splitAddress.houseNumber" required="true" %}
Address as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address.splitAddress.landmark" required="true" %}
Address as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address.splitAddress.location" required="true" %}
Address as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address.splitAddress.pincode" required="true" %}
Address as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address.splitAddress.postOffice" required="true" %}
aAddress as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address.splitAddress.state" required="true" %}
Address as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address.splitAddress.street" required="true" %}
Address as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address.splitAddress.subdistrict" required="true" %}
Address as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address.splitAddress.vtcName" required="true" %}
Address as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="aadharNumber" required="true" %}
Address as per Aadhar document
{% endswagger-parameter %}

{% swagger-parameter in="body" name="traceId" required="true" %}
This value fro previous api 
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "code": "200",
        "message": "EKYC Completed",
        "kycLevel": "100",
        "displayMessage": "E-KYC successfully completed."
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

| Response Field | Field Description             | Data Type |
| -------------- | ----------------------------- | --------- |
| code           | response code                 | String    |
| message        | response description          | String    |
| kycLevel       | kyc level                     | String    |
| displayMessage | detailed response description | String    |

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request POST 'http://localhost:8083/onboarding/ekyc/v1/aadhaar/userConfirmation' \
\--header 'X-API-TOKEN : token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
\--header 'Cookie: JSESSIONID=C0D114845B4EC3A92A840A1B862E96F4'
\--data-raw '{
    "name": " G",
    "gender": "M",
    "dob": "545",
    "fatherName": " D P",
    "address": {
        "combinedAddress": "#38, Raghavendra",
        "splitAddress": {
            "country": "India",
            "district": "Shimoga",
            "houseNumber": "#38",
            "landmark": null,
            "location": "Soppugudde",
            "pincode": "7777",
            "postOffice": "TTT",
            "state": "Karnataka",
            "street": "Raghavendra Ext 12th Cross",
            "subdistrict": "Thirthahalli",
            "vtcName": "Tirthahalli"
        }
    },
    "aadharNumber": "XXXX XXXX 7090",
    "traceId" : "52c0679e-088a-4510-a189-a399bc67ae07"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "name": " G",
    "gender": "M",
    "dob": "545",
    "fatherName": " D P",
    "address": {
        "combinedAddress": "#38, Raghavendra",
        "splitAddress": {
            "country": "India",
            "district": "Shimoga",
            "houseNumber": "#38",
            "landmark": null,
            "location": "Soppugudde",
            "pincode": "7777",
            "postOffice": "TTT",
            "state": "Karnataka",
            "street": "Raghavendra Ext 12th Cross",
            "subdistrict": "Thirthahalli",
            "vtcName": "Tirthahalli"
        }
    },
    "aadharNumber": "XXXX XXXX 7090",
    "traceId" : "52c0679e-088a-4510-a189-a399bc67ae07"

}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "ONB200",
    "resDesc": "SUCCESS",
    "data": {
        "code": "200",
        "message": "EKYC Completed",
        "kycLevel": "100",
        "displayMessage": "E-KYC successfully completed."
    }
}
```
{% endtab %}
{% endtabs %}
