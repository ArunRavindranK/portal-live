---
description: >-
  This API will be invoked by Gateway Server to process credit payment request
  for the qr payment transaction.
---

# Payment - Receive Money



{% swagger method="post" path=" " baseUrl="/ v1/payment/payout" summary="" %}
{% swagger-description %}
· Invoke Account MS limit consumption validation api to validate the consumption limit and credit payment is processed.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" type="String" %}
MOB-APP-1111
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" type="String" %}
Token got from the 

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

{% swagger-parameter in="body" name="Identification" type="String" %}
Creditor Account Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Name" type="String" %}
Creditor Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Scheme Name" type="String" %}
Debtor Account Scheme name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Identification" type="String" %}
Debtor Account Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Name" type="String" %}
Debtor Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Country Code" type="String" %}
Country Code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmt" type="String" %}
Transaction Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ChargeBearer" type="String" %}
Fee Bearer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Type" type="String" %}
Fee Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Amount" type="String" %}
Fee amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnDesc" type="String" %}
Transaction desc
{% endswagger-parameter %}

{% swagger-parameter in="body" name="TotalTxnAmt" type="String" %}
Total txn amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="TxnType" type="String" %}
Transaction Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Currency" type="String" %}
Currency Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="AcquiredId" type="String" %}
Acquirer Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="String" %}
Merchant Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refId" type="String" %}
Reference Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mcc" type="String" %}
Merchant category code
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
</code></pre></td><td><pre><code>ACCOUNT SERVICE FAILED
</code></pre></td><td></td></tr><tr><td><pre><code>PMT_500
</code></pre></td><td><pre><code>Internal Server Error
</code></pre></td><td></td></tr><tr><td><pre><code>200
</code></pre></td><td><pre><code>SUCCESS
</code></pre></td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Curl" %}
```html
curl --location --request POST 'http://localhost:2442/payments/v1/payment/payout' \
--header 'x-program-id: 1111' \
--header 'x-account-number: 1234567890' \
--header 'Content-Type: application/json' \
--header 'Cookie: JSESSIONID=DC209CA95695FE68449B2899AE44ABDA' \
--data-raw '{
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
}'
```
{% endtab %}

{% tab title="Request Body" %}
```json
{
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
```
{% endtab %}

{% tab title="Response Body" %}
```json
{
    "resCode":"200",
    "resDesc":"SUCCESS"
}
```
{% endtab %}
{% endtabs %}
