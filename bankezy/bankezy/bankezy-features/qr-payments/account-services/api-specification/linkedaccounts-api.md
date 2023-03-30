---
description: >-
  This API is used to take list of Accounts in the Request Body, and links them
  to User's Accounts.
---

# LinkedAccounts API

{% swagger method="post" path="" baseUrl="http://localhost:8911/account/v1/accounts/linkedAccounts" summary="" %}
{% swagger-description %}
Pass ArrayList of Accounts Objects in Request Body. It uses these details and populates UserAccunts, UserAccountDetails tables for a User.

\


Below, Account Object is listed for reference.
{% endswagger-description %}

{% swagger-parameter in="header" name="CUSTOMER-ID" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="AccountId" type="" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="Id" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="Status" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="StatusUpdateDateTime" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="Currency" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="AccountType" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="AccountSubType" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="Nickname" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="OpeningDate" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="Account" %}
AccountIdentification JSON
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

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

<table><thead><tr><th></th><th></th><th data-hidden></th></tr></thead><tbody><tr><td><pre><code>ACT_500
</code></pre></td><td><pre><code>Internal Server Error
</code></pre></td><td></td></tr><tr><td><pre><code>200
</code></pre></td><td><pre><code>SUCCESS
</code></pre></td><td></td></tr><tr><td></td><td></td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample cURL" %}
```json
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/account/v1/accounts/linkedAccounts' \
--header 'CUSTOMER-ID: 23234' \
--header 'X-PROGRAM-ID: 1111' \
--header 'X-API-TOKEN: Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJORVdfVVNFUiIsIlRPS0VOX0VYUElSWSI6OTAwLCJSRUZFUkVOQ0VfSUQiOiI4NDY0OTFkYi02NDBiLTRkNzYtOGI4ZC0xZmM5ZjZjNmIxMzEiLCJBTExPV0VEX0lQUyI6IioiLCJpc3MiOiJpVEowVGxtMWtVV29KYVpOR3lhYWlHaWNYS3pYTUI1cCIsImV4cCI6MTY2NjMwMTg0NiwiUFJPR1JBTV9JRCI6MTExMSwiaWF0IjoxNjY2MjQ3ODQ2fQ.IjhDD0vzDmPpdO3fdtR3yu3UKjiRA5XEzuJudiwcSoiZKxjV7XMDlk5hyZ6jVIphCHc8qfEDBjFN0HzN37wtsw' \
--header 'X-API-KEY: MOB-APP' \
--header 'Content-Type: application/json' \
--data-raw '{
    "account": [
        {
            "id": 8881,
            "accountId": "1005",
            "status": "Enabled",
            "accountType": "sdfsdfsdfds",
            "currency": "GBP",
            "nickname": "spk1",
            "isPrimary": true,
            "isSelected": false,
            "account": [
                {
                    "schemeName": "UK.OBIE.SortCodeAccountNumber",
                    "identification": "10005",
                    "name": "Mr spk1"
                }
            ]
        },
        {
            "id": 2,
            "accountId": "1006",
            "status": "Enabled",
            "accountType": "Personal",
            "currency": "GBP",
            "nickname": "spk2",
            "isPrimary": true,
            "isSelected": false,
            "account": [
                {
                    "schemeName": "UK.OBIE.SortCodeAccountNumber",
                    "identification": "10006",
                    "name": "Mr spk2"
                }
            ]
        }
    ]
}'
```
{% endtab %}

{% tab title="Request Body" %}


```json
{
    "account": [
        {
            "id": 8881,
            "accountId": "1000",
            "status": "Enabled",
            "accountType": "sdfsdfsdfds",
            "currency": "GBP",
            "nickname": "Mani",
            "isPrimary": true,
            "isSelected": false,
            "account": [
                {
                    "schemeName": "UK.OBIE.SortCodeAccountNumber",
                    "identification": "10002",
                    "name": "Mr Kevin"
                }
            ]
        },
        {
            "id": 2,
            "accountId": "1001",
            "status": "Enabled",
            "accountType": "Personal",
            "currency": "GBP",
            "nickname": "Kumar",
            "isPrimary": true,
            "isSelected": false,
            "account": [
                {
                    "schemeName": "UK.OBIE.SortCodeAccountNumber",
                    "identification": "10003",
                    "name": "Mr Uma"
                }
            ]
        }
    ]
}
```


{% endtab %}

{% tab title="Response Body" %}
```
{
    "resCode": 200
}
```
{% endtab %}
{% endtabs %}
