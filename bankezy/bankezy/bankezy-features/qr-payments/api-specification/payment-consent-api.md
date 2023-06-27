---
description: >-
  This API is used by App to initiate the consent request for the payment
  transaction. On successful transaction initiation, OTP validation happens if
  authentication is enabled.
---

# Payment Consent API

Features supported by this API:

1. Supports transaction consent request for P2P (Person to person), P2M(Person to Merchant) and P2B(Person to Biller).
2. Open Banking API Standards are followed.





{% swagger method="post" path=" " baseUrl="/v1/payment/consent" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" type="String" %}
MOB-APP-1111
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" type="String" %}
The token got from the 

[login API](../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/common-apis/get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="Amount" required="true" type="String" %}
Transaction Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Scheme Name" type="String" %}
Creditor Account Scheme name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Identification" type="String" required="true" %}
Creditor Account Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Name" type="String" %}
Creditor Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Scheme Name" type="String" %}
Debtor Account Scheme name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Identification" type="String" required="true" %}
Debtor Account Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Name" type="String" %}
Debtor Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Country Code" %}
Country Code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmt" %}
Transaction Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ChargeBearer" %}
Fee Bearer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Type" %}
Fee Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Amount" %}
Fee amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnDesc" %}
Transaction desc
{% endswagger-parameter %}

{% swagger-parameter in="body" name="TotalTxnAmt" %}
Total txn amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="TxnType" required="true" %}
transaction type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Currency" %}
Currency Name
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="SUCCESS" %}
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

<table><thead><tr><th></th><th></th><th data-hidden></th></tr></thead><tbody><tr><td><pre><code>PMT_100
</code></pre></td><td><pre><code>ONBOARDING SERVICE FAILED
</code></pre></td><td></td></tr><tr><td><pre><code>PMT_100
</code></pre></td><td><pre><code>Request Validation Failed
</code></pre></td><td></td></tr><tr><td><pre><code>PMT_50
</code></pre></td><td><pre><code>NOTIFICATION SERVICE FAILED
</code></pre></td><td></td></tr><tr><td><pre><code>PMT_500
</code></pre></td><td><pre><code>Internal Server Error
</code></pre></td><td></td></tr><tr><td>200</td><td>Success</td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Curl" %}
```
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/payments/v1/payment/consent' \
--header 'Content-Type: application/json' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJDTElFTlRfQVBQX1NESyIsIlRPS0VOX0VYUElSWSI6OTAwLCJSRUZFUkVOQ0VfSUQiOiJiMjU3MWFhOS0zYzQ2LTRmNTItODMxNC00ZTNiMDEzMmQ4YzciLCJDTElFTlRfSU5GTyI6IntcImZpcnN0TmFtZVwiOlwiUHJlbSBLdW1hclwiLFwic2RrQXBpS2V5XCI6XCJNT0ItQVBQLTIwMDFcIixcImxhc3ROYW1lXCI6bnVsbCxcImFjY291bnROdW1iZXJcIjoxMjM0NTY4MDQ2LFwiaXNkQ29kZVwiOjAsXCJtb2JpbGVOdW1iZXJcIjo2MzAzOTM4ODI4LFwiZG9iXCI6MCxcImVtYWlsXCI6XCJwcmVta3VtYXJzODgyOEBnbWFpbC5jb21cIixcInNka1B1YmxpY0tleVwiOlwiZXlKcmRIa2lPaUpGUXlJc0ltTnlkaUk2SWxBdE1qVTJJaXdpZUNJNklrdEpYMjR4Vm00dFVEWkhWREJMZW5oTGNVc3dTa1kwY1U1blFXTkRTazl1Y1VjM1dVdDNWR3A1VUZFaUxDSjVJam9pYld4VU9XZHlNMlY1WmtZelZtVkZlVFkwWHpkd056RjVTSEU1V1hSVGNtSnVMV2RyY1hwU2MyVlBkeUo5XCIsXCJyZWZlcmVuY2VJZFwiOm51bGwsXCJkYXRhXCI6bnVsbH0iLCJBTExPV0VEX0lQUyI6IioiLCJpc3MiOiJnZ2RUeUx3ZW92ZUtyRlFzeDNuY3NmZ0RrdjhBdEZBeiIsIlVTRVJfSUQiOjEyMzQ1NjgwNDYsIkxPR0lOX0hJU1RPUllfSUQiOiJiMjU3MWFhOS0zYzQ2LTRmNTItODMxNC00ZTNiMDEzMmQ4YzciLCJYLUFDQ09VTlQtTlVNQkVSIjoxMjM0NTY4MDQ2LCJleHAiOjE2NzAxMjg2NjIsIlBST0dSQU1fSUQiOjExMTEsImlhdCI6MTY3MDA3NDY2Mn0.kWCzOJI59zB-bIF-wTwSt8iAYn9uqp2RLHSplGlr1gDbV43TSiMCmHxyKvqzdAykxhhHRdCOXteg14g4hJi6Qg' \
--header 'Cookie: JSESSIONID=76E34EE8ED81BB6CF077A4C8877BC74E' \
--data-raw '{
    "Initiation": {
        "Charges":{
            "Amount":0.0
        },
        "Country": {
            "CountryCode": "+91"
        },
        "CreditorAccount": {
            "Identification": "5300456987135246320",
            "Name": "Mr spk1",
            "SchemeName": "SortCodeAccountNumber1"
        },
        "DebtorAccount": {
            "Identification": "5300456987135246321",
            "Name": "Mr spk2",
            "SchemeName": "SortCodeAccountNumber2"
        },
        "InstructedAmount": {
            "Amount": "10000.0",
            "Currency": "INR"
        },
        "SupplementaryData": {
            "txnType": "P2P"
        }
    }
}'
```
{% endtab %}

{% tab title="Request Body" %}
```json
{
    "Initiation": {
        "Charges":{
            "Amount":0.0
        },
        "Country": {
            "CountryCode": "+91"
        },
        "CreditorAccount": {
            "Identification": "5300456987135246320",
            "Name": "Mr spk1",
            "SchemeName": "SortCodeAccountNumber1"
        },
        "DebtorAccount": {
            "Identification": "5300456987135246321",
            "Name": "Mr spk2",
            "SchemeName": "SortCodeAccountNumber2"
        },
        "InstructedAmount": {
            "Amount": "10000.0",
            "Currency": "INR"
        },
        "SupplementaryData": {
            "txnType": "P2P"
        }
    }
}
```
{% endtab %}

{% tab title="Response Body" %}
```json
{
    "resCode":200,
    "resDesc":SUCCESS,
    "data":{
        "Initiation": {
            "InstructedAmount": {
                "Amount": 10000.0,
                "Currency": "INR"
            },
            "DebtorAccount": {
                "SchemeName": "SortCodeAccountNumber2",
                "Identification": "5300456987135246321",
                "Name": "Mr spk2"
            },
            "CreditorAccount": {
                "SchemeName": "SortCodeAccountNumber1",
                "Identification": "5300456987135246320",
                "Name": "Mr spk1"
            },
            "Charges": {
                "ChargeBearer": null,
                "Type": null,
                "Amount": 200.0
            },
            "Country": {
                "CountryCode": "+91"
            },
            "SupplementaryData": {
                "txnId": "2022120210010010199",
                "txnDate": "1669962523119",
                "txnType": "P2P",
                "txnStatus": "success",
                "referenceNo": "2022120210010010199",
                "authorizationId": "67822244",
                "approvalCode": "67822244"
            }
        }
    }
}
```
{% endtab %}
{% endtabs %}
