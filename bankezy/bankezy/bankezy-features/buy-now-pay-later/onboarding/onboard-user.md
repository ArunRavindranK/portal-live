---
description: >-
  This API is used for onboarding a new user. Based in input, first PAN
  validation is performed, upon successful validation, CKYC is performed and
  provides CKYC information for user acceptance.
---

# Onboard User



{% swagger method="post" path="lending/v1/onboard" baseUrl="<domain>/" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
The token got from the 

[Get Token API](../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="dob" type="String" required="true" %}
Date of birth
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gender" type="String" required="true" %}
Gender from M/F/O
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refNo" type="String" required="true" %}
Reference Number got from 

[Generate OTP API](generate-otp.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="String" required="true" %}
Name of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pan" type="String" required="true" %}
PAN Number of User
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

### Response Details

| Response Body                    | Data Type | Field Description        |
| -------------------------------- | --------- | ------------------------ |
| resCode                          | String    | Response Code            |
| resDesc                          | String    | Response Description     |
| ckycNumber                       | String    | ckyc number              |
| personalInfo.name                | String    | Name                     |
| personalInfo.gender              | String    | gender                   |
| personalInfo.dob                 | String    | date of birth            |
| personalInfo.pan                 | String    | pan number               |
| personalInfo.fathersName         | String    | father name              |
| personalInfo.address.line1       | String    | address line1            |
| personalInfo.address.line2       | String    | address line2            |
| personalInfo.address.line3       | String    | address line3            |
| personalInfo.address.dist        | String    | district                 |
| personalInfo.address.state       | String    | state                    |
| personalInfo.address.country     | String    | country                  |
| personalInfo.address.pinCode     | String    | pinCode                  |
| personalInfo.address.fullAddress | String    | Full Address             |
| Token                            | String    | Token for passing to api |
| Expiry                           | String    | Expiry time              |

{% tabs %}
{% tab title="Sample Curl Request" %}
<pre><code>curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/onboard' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: &#x3C;REPLACE_WITH_TOKEN_FROM_GET_TOKEN_API_RESPONSE>' \
<strong>--data-raw '{
</strong>  "dob": "06-06-1999",
  "gender": "M",
  "refNo": "&#x3C;REPLACE_WITH_REFID_FROM_GENERATE_OTP_API_RESPONSE>",
  "name": "Milind",
  "pan": "ABCDE1234F"
}'
</code></pre>
{% endtab %}

{% tab title="Request Example" %}
```json
{ 
    "dob": "06-06-1999", 
    "gender": "M", 
    "refNo": "<REPLACE_WITH_REFID_FROM_GENERATE_OTP_API_RESPONSE>", 
    "name": "Milind K", 
    "pan": "ABCDE1234F" 
}
```


{% endtab %}

{% tab title="Response Example" %}
```json
{ 
"resCode": 200, 
"resDesc": "CONFIRM_CKYC", 
"data": { 
         "ckycNumber": "40091637199907", 
         "personalInfo": { 
                               "name": "ANKIT PRAKASH SHARMA", 
                               "gender": "M", 
                               "dob": "18-03-1990", 
                               "pan": "CFWPK1905F", 
                               "fathersName": "JAI PRAKASH SHARMA", 
                               "address": { 
                                    "line1": "171/D FIRST FLOOR 28TH A MAIN", 
                                    "line2": "6TH CROSS HSR LAYOUT SECTOR 1", 
                                    "line3": "HSR POLICE STATION", 
                                    "city": "BANGLORE", 
                                    "dist": "Bangalore", 
                                    "state": "KA", 
                                    "country": "IN",
                                    "pincode": "560102", 
                                    "fullAddress": "171/D FIRST FLOOR 28TH A MAIN,6TH CROSS HSR LAYOUT SECTOR 1,HSR POLICE STATION,BANGLORE,Bangalore,KA,IN,560102" 
                                } 
            } 
  } 
}
```


{% endtab %}
{% endtabs %}

### Custom Response Codes

| Response Code | Response Description                                                                                                       |
| ------------- | -------------------------------------------------------------------------------------------------------------------------- |
| LND014        | DOB is mandatory.                                                                                                          |
| LND015        | PAN is mandatory.                                                                                                          |
| LND016        | Entered PAN is invalid. Please try again with a different PAN.                                                             |
| LND017        | Full Name is mandatory.                                                                                                    |
| LND011        | MISSING REF NO                                                                                                             |
| LND012        | INVALID REF NO                                                                                                             |
| LND013        | OTP entered is not correct. Try again with the correct OTP to continue.                                                    |
| LND004        | SETUP LIMIT                                                                                                                |
| LND018        | We couldn't check your eligibility for Zipcredit Paylater. Please validate the details you had entered or try again later. |
| LND009        | There seems to be a technical issue. Try again later.                                                                      |
| LND003        | CONFIRM CKYC                                                                                                               |
| LND019        | ASK AADHAAR                                                                                                                |
