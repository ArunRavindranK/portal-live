---
description: This API is used for onboarding a new user.
---

# Onboard User

{% swagger method="post" path="" baseUrl="/lending/v1/onboard" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
The token got from the 

[Get Token API](../../market-place/api-specification/get-token-api.md)


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
