---
description: >-
  This Api is used to confirm CKYC information provided in response to Onboard
  User API.
---

# Confirm CKYC

{% swagger method="post" path="/lending/v1/onboard/confirm" baseUrl="<domain>" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
The token got from the 

[Get Token API](../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="String" required="true" %}
Name of the user 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gender" type="String" required="true" %}
Gender from M/F/O
{% endswagger-parameter %}

{% swagger-parameter in="body" name="dob" type="String" required="true" %}
Date of birth 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pan" type="String" required="true" %}
PAN number of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" required="true" type="JSON" %}
User Address Details
{% endswagger-parameter %}

{% swagger-parameter in="body" name="line1" type="String" required="true" %}
Street Address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="line2" type="String" required="true" %}
Apartment/Flat Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="line3" type="String" %}
Landmark
{% endswagger-parameter %}

{% swagger-parameter in="body" name="city" type="String" required="true" %}
City
{% endswagger-parameter %}

{% swagger-parameter in="body" name="dist" type="String" required="true" %}
District
{% endswagger-parameter %}

{% swagger-parameter in="body" name="state" type="String" required="true" %}
State 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="country" type="String" required="true" %}
Country
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pincode" type="String" required="true" %}
Pincode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fullAddress" type="String" %}
Complete residential address
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

| Response Body | Data Type | Field Description    |
| ------------- | --------- | -------------------- |
| resCode       | String    | Response Code        |
| resDesc       | String    | Response Description |
|               |           |                      |

{% tabs %}
{% tab title="Sample Curl Request" %}
<pre><code>curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/onboard/confirm' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: &#x3C;REPLACE_WITH_TOKEN_FROM_GET_TOKEN_API_RESPONSE>' \
<strong>--data-raw '{
</strong>  "name": "ANKIT PRAKASH SHARMA",
  "gender": "M",
  "dob": "18-03-1990",
  "pan": "CFWPK195F",
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
}'
</code></pre>
{% endtab %}

{% tab title="Request Example" %}
```json
{
"name": "ANKIT PRAKASH SHARMA", 
"gender": "M", 
"dob": "18-03-1990", 
"pan": "CFWPK195F", 
"address": { 
               "line1": "171/D FIRST FLOOR 28TH A MAIN", 
               "line2": "6TH CROSS HSR LAYOUT SECTOR 1",
               "line3": "HSR POLICE STATION", 
               "city": "BANGLORE", 
               "dist": "Bangalore", 
               "state": "KA", 
               "country": "IN", 
               "pincode": "560102", 
               "fullAddress": "171/D FIRST FLOOR 28TH A MAIN,6TH     CROSS HSR LAYOUT SECTOR 1,HSR POLICE STATION,BANGLORE,Bangalore,KA,IN,560102" 
 } 
}
```
{% endtab %}

{% tab title="Response Example" %}
```json
{ 
"resCode": 200, 
"resDesc": "SETUP_LIMIT" 
}
```
{% endtab %}
{% endtabs %}

### Custom Response Code

| Response Code | Response Description                                  |
| ------------- | ----------------------------------------------------- |
| LND021        | Mandatory inputs are missing.                         |
| LND004        | SETUP LIMIT                                           |
| LND009        | There seems to be a technical issue. Try again later. |
