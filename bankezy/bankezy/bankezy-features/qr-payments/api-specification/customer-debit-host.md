---
description: The API is intended to submit the payment request for processing
---

# Customer Debit- Host



{% swagger method="post" path="" baseUrl="<domain>/ v1/payment/payment" summary="" %}
{% swagger-description %}
· If Second factor authentication is enabled, Validate the OTP.

· Validate the Transaction & Amount Limit status from cache. If validation status not found in cache, return validation not completed Error.

· Invoke Account service debit Api via rest call to perform debit transaction

· If debit process is success, Invoke Gateway Transaction Service →> perform Credit method to send the credit request to the Gateway.

· If credit process is failure, Invoke Account service refund api to perform Refund Process.

· On completion of process payment, Remove the cache validation object from cache.
{% endswagger-description %}

{% swagger-parameter in="header" name="x-program-id" required="true" type="String" %}
program id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-account-number" required="true" type="String" %}
customer id
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
transaction type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Currency" type="String" %}
Currency Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpRefno" type="String" %}
Otp Ref no
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpVal" type="String" %}
Otp value
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

<table><thead><tr><th></th><th></th><th data-hidden></th></tr></thead><tbody><tr><td><pre><code>PS_100
</code></pre></td><td><pre><code>Transaction failed, try later
</code></pre></td><td></td></tr><tr><td><pre><code>PS_101
</code></pre></td><td><pre><code>Validation failure, try later
</code></pre></td><td></td></tr><tr><td><pre><code>PS_102
</code></pre></td><td><pre><code>Please enter valid otp
</code></pre></td><td></td></tr><tr><td><pre><code>500
</code></pre></td><td><pre><code>Internal server error
</code></pre></td><td></td></tr><tr><td>200</td><td>Success</td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Curl" %}
```
curl --location --request POST 'http://localhost:2442/payments/v1/payment/payment' \
--header 'x-program-id: 1111' \
--header 'x-account-number: 1234567890' \
--header 'X-EMAIL: premkumars8828@gmail.com' \
--header 'X-MOBILE: 6303938828' \
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
            "txnDate": "1669962508118",
            "otpVal": "624066",
            "otpRefNo": "b55f4e25-a2ed-4d15-b3a4-341f99639a3e",
            "txnType": "P2P",
            "txnStatus": "SUCCESS",
            "invoiceNum": "",
            "isSFAEnabled": true
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
            "txnDate": "1669962508118",
            "otpVal": "624066",
            "otpRefNo": "b55f4e25-a2ed-4d15-b3a4-341f99639a3e",
            "txnType": "P2P",
            "txnStatus": "SUCCESS",
            "invoiceNum": "",
            "isSFAEnabled": true
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
