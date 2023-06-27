---
description: To Update any details about the user
---

# Update User Profile



{% swagger method="post" path="" baseUrl="<domain>/onboarding/userProfile/v2/updatedUser" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accounts" type="JSON" required="true" %}
Accounts
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accounts" type="String" required="true" %}
Accounts
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accountNumber" type="String" required="true" %}
Account Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accountType" type="String" required="true" %}
​Account Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankName" type="String" required="true" %}
Bank Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="branch" type="String" required="true" %}
Branch
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ifscCode" type="String" required="true" %}
​IFSCCode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nickName" type="String" required="true" %}
​Nick Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pin" type="Boolean" required="true" %}
Pin
{% endswagger-parameter %}

{% swagger-parameter in="body" name="primary" type="Boolean" required="true" %}
Primary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vpa" type="String" required="true" %}
vpa
{% endswagger-parameter %}

{% swagger-parameter in="body" name="category" type="String" required="true" %}
Category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="linkedCardInfo" type="JSON" required="true" %}
LinkedCard Info
{% endswagger-parameter %}

{% swagger-parameter in="body" name="addedSource" type="String" required="true" %}
Added Source
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankName" type="String" required="true" %}
Bank Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardAssociation" type="String" required="true" %}
​CardAssociation
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardExpiryMM" type="String" required="true" %}
CardExpiryMM
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardExpiryYYYY" type="String" required="true" %}
Card ExpiryYYYY
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardNumber" type="String" required="true" %}
Card Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardType" type="String" required="true" %}
​Card Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardUnion" type="String" required="true" %}
Card Union
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" type="String" required="true" %}
CountryCode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nameOnCard" type="String" required="true" %}
NameOnCard
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nickName" type="String" required="true" %}
NickName
{% endswagger-parameter %}

{% swagger-parameter in="body" name="onUs" type="Int" required="true" %}
onUs
{% endswagger-parameter %}

{% swagger-parameter in="body" name="primary" type="Boolean" required="true" %}
Primary
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="201: Created" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="204: No Content" description="" %}
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

{% swagger-response status="403: Forbidden" description="" %}
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

## Custom response codes

| Code   | Description                |
| ------ | -------------------------- |
| ONB032 | DOB Mandatory              |
| ONB033 | Email id is mandatory      |
| ONB034 | Email id format is invalid |
| ONB030 | Failure                    |
| ONB200 | SUCCESS                    |

### **Response Details**

<table><thead><tr><th width="163">Response Field</th><th width="222">Field Desc</th><th width="150">Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>Response Code</td><td>String</td><td></td></tr><tr><td>resDesc</td><td>SUCCESS, FAILURE status of the API</td><td>String</td><td>Variable, 5–8 characters</td></tr></tbody></table>

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'http://192.168.105.70:8083/onboarding/userProfile/v2/updatedUser' \
--header 'X-PROGRAM-ID: 1111' \
--header 'X-ACCOUNT-NUMBER: 404' \
--header 'Content-Type: application/json' \
--data-raw '{
  "dateOfBirth": "03/07/1994",
    "emailId": "xyz@gmail.com",
    "preferredLanguage": "EN"
    
}'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}


```json
{
  "dateOfBirth": "03/07/1994",
    "emailId": "xyz@gmail.com",
    "preferredLanguage": "EN"
    
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": "ONB200",
  "resDesc": "SUCCESS"
}
```
{% endtab %}
{% endtabs %}
