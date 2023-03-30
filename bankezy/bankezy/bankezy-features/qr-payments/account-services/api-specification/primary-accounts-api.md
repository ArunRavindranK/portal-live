---
description: This API is used to set an account as the Primary Account for a User.
---

# Primary Accounts API



{% swagger method="post" path="" baseUrl="http://localhost:8911/account/v1/accounts/primaryAccounts" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" type="String" %}
program id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="CUSTOMER-ID" required="true" %}
customer id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="AccountId" required="true" type="String" %}
Account id for new Primary Account
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Nickname" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="Currency" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="AccountType" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="Status" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="OpeningDate" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="StatusUpdateDateTime" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="Account" type="Json" %}
user_account_details Json
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Sucess, Updated User's Primary Account" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Bad Request, AccountId/ CustomerId Header/ ProgramId must be Present" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="402" description="Bad Request, Invalid AccountId in RequestBody" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="501: Not Implemented" description="Server Error, Failed to map request body to UserAccounts" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="502" description="Server Error, Failure in DB Connection" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

<table><thead><tr><th></th><th></th><th data-hidden></th></tr></thead><tbody><tr><td><pre><code>ACT_400
</code></pre></td><td><pre><code>BadRequest
</code></pre></td><td></td></tr><tr><td><pre><code>ACT_501
</code></pre></td><td><pre><code>Failed to map request body to UserAccounts
</code></pre></td><td></td></tr><tr><td><pre><code>200
</code></pre></td><td><pre><code>SUCCESS
</code></pre></td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Curl" %}
```
curl --location --request POST 'http://localhost:8911/account/v1/accounts/primaryAccounts' \
--header 'CUSTOMER-ID: 23234' \
--header 'X-PROGRAM-ID: 1111' \
--header 'Content-Type: application/json' \
--header 'Cookie: JSESSIONID=71BB2E2CE1F6F7806746A3B4435671C6' \
--data-raw '{
    "AccountId": "1001",
    "Nickname": "Household",
    "Currency": "GBP",
    "AccountType": "Personal",
    "Status": "Enabled",
    "OpeningDate": "2022-10-10T03:57:27.000+00:00",
    "StatusUpdateDateTime": null,
    "Account": [
        {
            "id": 6,
            "accountId": 3079779791941468106,
            "schemeName": "UK.OBIE.SortCodeAccountNumber",
            "accountIdentifier": "80200110203348",
            "sortCode": "ddfdff",
            "name": "Mr Kevin"
        }
    ]
}'
```
{% endtab %}

{% tab title="Request Body" %}
```json
{
    "AccountId": "1001",
    "Nickname": "Household",
    "Currency": "GBP",
    "AccountType": "Personal",
    "Status": "Enabled",
    "OpeningDate": "2022-10-10T03:57:27.000+00:00",
    "StatusUpdateDateTime": null,
    "Account": [
        {
            "id": 6,
            "accountId": 3079779791941468106,
            "schemeName": "UK.OBIE.SortCodeAccountNumber",
            "accountIdentifier": "80200110203348",
            "sortCode": "ddfdff",
            "name": "Mr Kevin"
        }
    ]
}
```
{% endtab %}

{% tab title="Response Body" %}
```json
{
    "resCode": 200,
    "resDesc": "Updated User's Primary Account"
}
```
{% endtab %}
{% endtabs %}
