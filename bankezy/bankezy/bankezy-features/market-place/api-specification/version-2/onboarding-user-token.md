---
description: >-
  For any given user, this API will generate the user token and share it back
  with partner app. This token needs to be passed to the BankEzy SDK for any
  future communication.
---

# OnBoarding User Token

{% swagger method="post" path="" baseUrl="/onboarding/user/token" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="sdkPublicKey" required="true" %}
Public key shared by BankEzy SDK to client app
{% endswagger-parameter %}

{% swagger-parameter in="body" name="firstname " required="true" %}
First Name of customer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sdkPublicKey" %}
ApiKey provided by bankEzy to allow requests from sdk (provided during the onboarding)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="text/plain" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="lastName" %}
Last Name of customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accountNumber" %}
Unique to number to identify customer. Max 19 digits 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobileNumber" %}
Customer Mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" %}
Verified Email Address of customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="" %}
Gender of the customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="" %}
Country code of customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="" %}
Customer preferred language
{% endswagger-parameter %}

{% swagger-parameter in="body" name="" type="" %}
Any extra info to be required to pass
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}

{% endswagger-response %}
{% endswagger %}

## Response Body

| Response Body   | Data Type | Field Description    |
| --------------- | --------- | -------------------- |
| resCode         | Int       | Response Code        |
| resDesc         | String    | Response Description |
| token           | String    | Token value          |
| expiry          | Int       | Expiry Time of token |
| ServerPublicKey | String    | server public key    |



{% tabs %}
{% tab title="Sample curl request" %}


```json
curl --location --request POST 'http://payment1.pcdev.enstage-sas.com/onboarding/user/token' \
--header 'X-API-KEY: MOB-APP-1111' \
--header 'Content-Type: application/json' \
--data-raw '{
    "firstName": "firstName",
    "sdkPublicKey": "",
    "sdkApiKey": "api-key",
    "lastName": "lastName",
    "accountNumber": 123456788,
    "mobileNumber": 9999999999,
    "email": "mail@test.com",
    "gender": "Female",
    "zipCode": "603103",
    "preferredLanguage": "en",
    "data": {
        "custom_attribute1": "custom data"
    },
    "dob": 15051988,
    "kycLevel": "1"
}'
```
{% endtab %}

{% tab title="Token request sample" %}
```json
{
    "firstName": "firstName",
    "sdkPublicKey": "",
    "sdkApiKey": "api-key",
    "lastName": "lastName",
    "accountNumber": 123456788,
    "mobileNumber": 9999999999,
    "email": "mail@test.com",
    "gender": "Female",
    "zipCode": "603103",
    "preferredLanguage": "en",
    "data": {
        "custom_attribute1": "custom data"
    },
    "dob": 15051988,
    "kycLevel": "1"
}
```
{% endtab %}

{% tab title="Token response sample" %}


```json
{
    "resCode": 200,
    "resDesc": "Full Onboarding Success",
    "data": {
        "resCode": 100,
        "resDesc": "Success",
        "token": "Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJDTElFTlRfQVBQX1NESyIsIlRPS0VOX0VYUElSWSI6MzAsIlJFRkVSRU5DRV9JRCI6IjE1ZDI1NTVkLWM5MDctNDg3MC05ZGU5LTI2ZDE5MzYzODA0ZCIsIkNMSUVOVF9JTkZPIjoie1wiZmlyc3ROYW1lXCI6XCJoZW1hXCIsXCJzZGtBcGlLZXlcIjpcIkFNVUwtQVBQXCIsXCJsYXN0TmFtZVwiOm51bGwsXCJhY2NvdW50TnVtYmVyXCI6NDAsXCJpc2RDb2RlXCI6MCxcIm1vYmlsZU51bWJlclwiOjk1MzU0MzYzODAsXCJkb2JcIjoxOTgwMDYxMCxcImVtYWlsXCI6bnVsbCxcInNka1B1YmxpY0tleVwiOlwiZXlKcmRIa2lPaUpGUXlJc0ltTnlkaUk2SWxBdE1qVTJJaXdpZUNJNklrMVhjVFpNTUdoMmJVMHhaV3A0VlRKdlRrbEdWRGRrVVd4MVJqRnBWbVJ4U0RjMU4yaHphVUZ2VFdzaUxDSjVJam9pTXpneWJEWnRObEpLYUVGVFEzUjJSMlJNZVZaTGVrbGpiV0Z1UW5RM1h6UTVWMHg1UVZCV01VNDFNQ0o5XCIsXCJyZWZlcmVuY2VJZFwiOm51bGwsXCJkYXRhXCI6bnVsbH0iLCJBTExPV0VEX0lQUyI6IioiLCJpc3MiOiJRVTFWVEY5Q1FVNUxSVnBaWDBsT1ZFVkhVa0ZVU1U5TyIsIlVTRVJfSUQiOjQwLCJMT0dJTl9ISVNUT1JZX0lEIjoiMTVkMjU1NWQtYzkwNy00ODcwLTlkZTktMjZkMTkzNjM4MDRkIiwiWC1BQ0NPVU5ULU5VTUJFUiI6NDAsImV4cCI6MTY4NDc0ODE1MywiUFJPR1JBTV9JRCI6MjAwMiwiaWF0IjoxNjg0NzQ2MzUzfQ.E_AWbeMOC9hkUqDEpYeSVnffsmP-7AqnYjPmUfE4cXKmb6oc1a5RHKuzkWSd9p0SbG1UupMT6Zh09XgGXbxU4w",
        "expiry": 1684748153591,
        "serverPublicKey": "eyJrdHkiOiJFQyIsImNydiI6IlAtMjU2IiwieCI6InMxeUgtcUZkM1piTnJJQTRnMFpxNU9xNHQwTWxxRzFteVU2UFd6U1owTmciLCJ5IjoiMU8yR1oxb3NOWW5xb21nOXpWVTFfTW5hRTdyR1NQajRmQnRxbzFYem0yYyJ9"
    }
}
```
{% endtab %}
{% endtabs %}
