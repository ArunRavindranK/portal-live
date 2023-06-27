---
description: >-
  This Api is used for managing/fetching user linked accounts for QR payments.
  API provides following features.
---

# Fetch Accounts API



1. By Passing type as "All", Api is used to fetch list of available user accounts from CBS Partner and display list of Available accounts & linked accounts to amend user linked accounts.
2. By Passing type as "Linked" ,To fetch list of user linked accounts for QR Payments.&#x20;

<figure><img src="../../../../../../.gitbook/assets/fetchAccounts flow diagram.png" alt=""><figcaption></figcaption></figure>

{% swagger method="post" path=" " baseUrl="account/v1/accounts/{type}" summary="To fetch user linked accounts & all accounts to amend linked accounts. " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" type="String" %}
MOB-APP-1111
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" type="String" %}
token got from the 

[login API](../../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/common-apis/get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="path" name="accountType" required="true" %}
values: [all / linked]
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Sucess, Updated User's Primary Account" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="INTERNAL ERROR" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

<table><thead><tr><th></th><th></th><th data-hidden></th></tr></thead><tbody><tr><td><pre><code>ACT_100
</code></pre></td><td><pre><code>No linked accounts found
</code></pre></td><td></td></tr><tr><td><pre><code>ACT_500
</code></pre></td><td><pre><code>Internal Server Error
</code></pre></td><td></td></tr><tr><td><pre><code>200
</code></pre></td><td><pre><code>SUCCESS
</code></pre></td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Curl" %}
```
curl --location --request POST 'http://localhost:9911/account/v1/accounts/all' \

--header 'X-PROGRAM-ID: 1111' \

--header 'CUSTOMER-ID: 23234' \

--header 'Cookie: JSESSIONID=6F063A9B1955C044C4A9B0C922DE7976' \
```
{% endtab %}

{% tab title="Response Body" %}
```json
{
    "resCode": 200,
    "resDesc": "success",
    "data": {
        "Account": [
            {
                "id": null,
                "accountId": "56565",
                "status": "Enabled",
                "accountType": null,
                "currency": "GBP",
                "nickName": "Bills",
                "isPrimary": true,
                "isSelected": null,
                "account": [
                    {
                        "schemeName": "UK.OBIE.SortCodeAccountNumber",
                        "identification": "80200110203345",
                        "name": "Mr Kevin"
                    }
                ]
            },
            {
                "id": null,
                "accountId": "565656",
                "status": "Enabled",
                "accountType": null,
                "currency": "GBP",
                "nickName": "Household",
                "isPrimary": true,
                "isSelected": null,
                "account": [
                    {
                        "schemeName": "UK.OBIE.SortCodeAccountNumber",
                        "identification": "80200110203348",
                        "name": "Mr Kevin"
                    }
                ]
            },
            {
                "id": 21,
                "accountId": "1000",
                "status": "Enabled",
                "accountType": null,
                "currency": "GBP",
                "nickName": null,
                "isPrimary": true,
                "isSelected": null,
                "account": [
                    {
                        "schemeName": "UK.OBIE.SortCodeAccountNumber",
                        "identification": "10002",
                        "name": "Mr Kevin"
                    }
                ]
            },
            {
                "id": 22,
                "accountId": "1001",
                "status": "Enabled",
                "accountType": null,
                "currency": "GBP",
                "nickName": null,
                "isPrimary": true,
                "isSelected": null,
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
}
```
{% endtab %}
{% endtabs %}
