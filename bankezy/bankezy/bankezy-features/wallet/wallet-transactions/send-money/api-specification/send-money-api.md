---
description: >-
  Api Supports Transfer Money from Bankezy wallet to another wallet, client has
  to send all recipient details like mobile,name,address etc in API
---

# Send Money API

{% swagger method="post" path="" baseUrl="<domain>/wallet/sendmoney/api/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="Int" required="true" %}
Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productType" type="String" required="true" %}
Product Type(wallet type ex: RW)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientAddressLine1" type="String" required="true" %}
Recipient Address Line1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientCity" type="String" required="true" %}
Recipient City
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientCountry" type="String" required="true" %}
Recipient Country
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientCountrySubdivision" type="String" required="true" %}
Recipient Country Subdivision
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientCustomerId" type="Int" required="true" %}
Recipient Customer Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientEmail" type="String" required="true" %}
Recipient Email
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientFirstName" type="String" required="true" %}
Recipient FirstName
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientLastName" type="String" required="true" %}
Recipient LastName
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientMiddleName" type="String" required="true" %}
Recipient MiddleName
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientMobileNo" type="String" required="true" %}
Recipient MobileNo
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientNationality" type="String" required="true" %}
Recipient Nationality
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientPostalCode" type="String" required="true" %}
Recipient PostalCode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientWalletId" type="Int" required="true" %}
​Recipient WalletId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="remarks" type="String" required="true" %}
​Remarks
{% endswagger-parameter %}

{% swagger-parameter in="body" name="rrn" type="String" required="true" %}
​RRN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="senderWalletId" type="String" required="true" %}
​Sender WalletId
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
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

## Custom response codes

| Response code  | Response description                                                                                                                                                                                                                                                                                                                                                                                 |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ​2             | Sender wallet card not found (or) impl id not found (or) card not found (or) Failure (or) prepaid response is null                                                                                                                                                                                                                                                                                   |
| 3              | Internal server error                                                                                                                                                                                                                                                                                                                                                                                |
| ​20            | Request is empty                                                                                                                                                                                                                                                                                                                                                                                     |
| 26             | Customer id is empty                                                                                                                                                                                                                                                                                                                                                                                 |
| 36             | rrn is empty                                                                                                                                                                                                                                                                                                                                                                                         |
| 37             | Amount is zero                                                                                                                                                                                                                                                                                                                                                                                       |
| 38             | Wallet id is zero                                                                                                                                                                                                                                                                                                                                                                                    |
| 41             | ​Recipient first name is empty                                                                                                                                                                                                                                                                                                                                                                       |
| 42             | Recipient last name is empty                                                                                                                                                                                                                                                                                                                                                                         |
| 43             | Recipient address line1 is empty                                                                                                                                                                                                                                                                                                                                                                     |
| ​44            | Re​cipient city is empty                                                                                                                                                                                                                                                                                                                                                                             |
| 45             | ​Recipient country is empty                                                                                                                                                                                                                                                                                                                                                                          |
| 46             | Recipient country subdivision is empty                                                                                                                                                                                                                                                                                                                                                               |
| 47             | Recipient nationality is empty                                                                                                                                                                                                                                                                                                                                                                       |
| 48             | ​Recipient postal code is empty                                                                                                                                                                                                                                                                                                                                                                      |
| 150            | Sender user account details not available for this mobile number (or) sender user id mismatch for this mobile number (or) The recipient is not a registered Bankezy wallet user.                                                                                                                                                                                                                     |
| 250            | Debit funds is disabled for this card (or) credit funds is disabled for this card                                                                                                                                                                                                                                                                                                                    |
| 300            | Our max amount per transaction limit is Rs %s. Please enter a smaller amount. (or) Your remaining limit is Rs %s for this month. Please enter a smaller amount. (or) Your remaining limit is Rs %s for today. Please enter a smaller amount. (or) You are not allowed any more transactions this month. Please retry next month. (or) You are not allowed any more transactions today. Please retry. |
| <p>350<br></p> | Recipient card number not found                                                                                                                                                                                                                                                                                                                                                                      |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/sendmoney/api/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw '{ "amount": "100", "productType": "RW", "recipientAddressLine1": "string", "recipientCity": "string", "recipientCountry": "India", "recipientCountrySubdivision": "Karnataka", "recipientCustomerId": "29", "recipientEmail": "Nithya@wibmo.com", "recipientFirstName": "Nithya", "recipientLastName": "Kaimal", "recipientMiddleName": "string", "recipientMobileNo": "7019055325", "recipientNationality": "India", "recipientPostalCode": "560091", "recipientWalletId": 13, "remarks": "string", "rrn": "202108131219532033kJ56qM1", "senderWalletId": "1" }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "amount": "100",
  "productType": "RW",
  "recipientAddressLine1": "MG Road",
  "recipientCity": "Bengaluru",
  "recipientCountry": "India",
  "recipientCountrySubdivision": "Karnataka",
  "recipientCustomerId": "29",
  "recipientEmail": "Nithya@wibmo.com",
  "recipientFirstName": "Nithya",
  "recipientLastName": "Kaimal",
  "recipientMiddleName": "string",
  "recipientMobileNo": "7019055325",
  "recipientNationality": "India",
  "recipientPostalCode": "560091",
  "recipientWalletId": 13,
  "remarks": "test",
  "rrn": "202108131219532033kJ56qM1",
  "senderWalletId": "1"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "money transferred successfully!",
  "data": {
    "txnId": "202207251520045369rS6",
    "amount": 100,
    "availableBal": 79298,
    "senderMobileNo": "5555533333",
    "recipientMobileNo": "7867854632",
    "remarks": "test",
    "txnDate": 1658762404536
  }
}
```
{% endtab %}
{% endtabs %}
