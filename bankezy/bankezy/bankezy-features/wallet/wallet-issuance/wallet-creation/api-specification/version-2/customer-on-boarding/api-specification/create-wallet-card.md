---
description: Create Card API
---

# Create Wallet Card

​​BankEzy wallet card can be issued to end users after completing their min KYC/eKYC. Banks/Fintechs/NBFCs/Merchants can issue closed loop wallet without KYC as well. For open loop or semi closed wallet, performing KYC is mandatory. Wallet card is a PPI instrument whose limits are defined by the KYC level of the wallet. Limits can also be modified within the threshold limits set by RBI. APIs to manage limits will be covered in Wallet Management section.

{% swagger method="post" path="" baseUrl=" <domain>/wallet/v2/create/api" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="loadAmt" type="int" required="true" %}
Amount to be loaded 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="user" type="JSON" %}
JSON of account, address and profile 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="account" type="JSON" required="true" %}
Contains currency
{% endswagger-parameter %}

{% swagger-parameter in="body" name="currency" required="true" type="String" %}
Currency code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" type="JSON" required="true" %}
JSON of addressline, citycode, country and zipcode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="citycode" type="String" required="true" %}
City code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="country" type="String" required="true" %}
Country code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="zipcode" type="String" required="true" %}
Zipcode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="addressline" type="String" required="true" %}
address details
{% endswagger-parameter %}

{% swagger-parameter in="body" name="profile" type="JSON" required="true" %}
JSON of dob,email,firstname,gender,lastname

and middlename
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the 

[login API](../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="dob" type="String" required="true" %}
Date of birth
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="String" required="true" %}
Email address
{% endswagger-parameter %}

{% swagger-parameter in="body" name="firstName" type="String" required="true" %}
First name of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gender" type="String" required="true" %}
Gender of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lastName" type="String" required="true" %}
Last Name of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="middleName" type="String" required="true" %}
Middle Name of the user
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Body contains JSON of data, error message, resp code, resp desc" %}
```javascript
{
  "data": {},
  "errorMessage": "string",
  "resCode": 0,
  "resDesc": "string"
}


//resCode - resDesc
//1 -> card created successfully
//2 -> impl id not found
//3 -> internal server error
//5 -> card is present already
//6 -> Unknown Product Type
//20 -> request is empty
//21 -> product type is empty
//24 -> Bad Request!!! user info is missing
//25 -> account info is missing
//26 -> customer id is empty
//27 -> kyc level is empty
//30 -> profile info is missing
//31 -> first name is empty
//33 -> email id is empty
//34 -> invalid date format
//35 -> gender is empty
//40 -> address info is missing
//42 -> addresslinee is empty
//43 -> city code is empty
//44 -> zip code is empty
//45 -> country code is empty
//200-> OK
//201-> Created
```
{% endswagger-response %}

{% swagger-response status="201: Created" description="" %}
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

{% swagger-response status="403: Forbidden" description="" %}
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
{% endswagger %}

## Response Details

| Response field | Field description                            | Data type |
| -------------- | -------------------------------------------- | --------- |
| customerId     | customer account number                      | String    |
| name           | name of the customer                         | String    |
| walletId       | Wallet id for a customer wallet from prepaid | Integer   |
| mobile         | customer mobile number                       | String    |
| cardNumber     | wallet card number                           | String    |
| cardExpiry     | expiry date for a wallet card                | String    |

## Custom response code

| Response code | Response description                |
| ------------- | ----------------------------------- |
| WAL34         | impl id not found                   |
| WAL35         | internal server error               |
| WAL36         | card is present already             |
| WAL37         | Unknown Product Type                |
| WAL38         | request is empty                    |
| WAL39         | product type is empty               |
| WAL40         | Bad Request!!! user info is missing |
| WAL41         | account info is missing             |
| WAL42         | kyc level is empty                  |
| WAL01         | customer id is empty                |
| WAL44         | first name is empty                 |
| WAL45         | email id is empty                   |
| WAL46         | invalid date format                 |
| WAL47         | gender is empty                     |
| WAL48         | addresslinee is empty               |
| WAL49         | city code is empty                  |
| WAL50         | zip code is empty                   |
| WAL51         | country code is empty               |
| WAL52         | profile info is missing             |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/create/api/v1'
\--header 'Content-Type:text/plain'
\--header 'X-API-TOKEN:token'
\--header 'X-API-KEY:MOB-APP-2001'
\--data-raw '{ "loadAmt": 0, "productType": "RW", "user": { "account": { "currency": "string" }, "address": { "addressLine": "string", "cityCode": "string", "country": "string", "zipCode": "string" }, "profile": { "dob": "12-10-2020", "email": "string", "firstName": "string", "gender": "M", "lastName": "string", "middleName": "string" } } }'

```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "loadAmt": 100,
  "productType": "RW",
  "user": {
    "account": {
      "currency": "INR"
    },
    "address": {
      "addressLine": "Wibmo Inc, MG Road",
      "cityCode": "7878888",
      "country": "India",
      "zipCode": "560091"
    },
    "profile": {
      "dob": "01-01-1989",
      "email": "abhinav.aradhya@wibmo.com",
      "firstName": "Abhinav",
      "gender": "M",
      "lastName": "Aradhya",
      "middleName": ""
    }
  }
}
```
{% endtab %}

{% tab title="Response sample" %}
{% code overflow="wrap" %}
```json
{
    "resCode": "WAL33",
    "resDesc": "card created successfully",
    "data": {
        "customerId": "1815",
        "name": "Raja Ram",
        "walletId": 601,
        "mobile": "2222222299",
        "cardNumber": "4123XXXXXXXX0404",
        "cardExpiry": "072021"
    }
}
```
{% endcode %}
{% endtab %}
{% endtabs %}





| Custom Response code | Response description                |
| -------------------- | ----------------------------------- |
| 1                    | Card created successfully           |
| 2                    | impl id not found                   |
| 3                    | internal server error               |
| 5                    | card is present already             |
| 6                    | Unknown Product Type                |
| 20                   | request is empty                    |
| 21                   | product type is empty               |
| 24                   | Bad Request!!! user info is missing |
| 25                   | account info is missing             |
| 26                   | customer id is empty                |
| 27                   | kyc level is empty                  |
| 30                   | profile info is missing             |
| 31                   | first name is empty                 |
| 33                   | email id is empty                   |
| 34                   | invalid date format                 |
| 35                   | gender is empty                     |
| 40                   | address info is missing             |
| 42                   | addresslinee is empty               |
| 43                   | city code is empty                  |
| 44                   | zip code is empty                   |
| 45                   | country code is empty               |
| 200                  | OK                                  |
| 201                  | Created                             |
