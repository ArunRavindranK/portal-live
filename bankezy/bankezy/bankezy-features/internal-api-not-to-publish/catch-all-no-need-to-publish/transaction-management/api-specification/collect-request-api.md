---
description: >-
  Request Money Accept confirm API: It applies only for UPI-UPI transfer mode,
  if users accepts the payment.
---

# Collect Request API



{% swagger method="post" path="v1/incoming" baseUrl="<domain>/collectrequest/" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="txnId" type="String" required="true" %}
UPI Transaction Reference Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerVpa" required="true" %}
payer VPA for upi transaction
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeVpa" required="true" %}
payee VPA for upi transaction
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeName" %}
payee Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerName" %}
payer Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" %}
txn amount for collect request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="currency" %}
currency  for collect request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="approvalStatus" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="remarks" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" required="true" %}
wallet Id for collect money
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnDate" %}
transaction date of the collect request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" type="Map" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
Program Id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" required="true" %}

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
{% endswagger %}

#### Response Fields

| Response Fields | Field Description                               | Data Type | Length |
| --------------- | ----------------------------------------------- | --------- | ------ |
| resCode         | response code of the API(200,500 etc)           | int       |        |
| resDesc         | response desc of the API(SUCCESS, FAILURE, etc) | String    |        |
| data            |                                                 | Object    |        |

| Response Fields   | Fields Description                 | Data Type                | Length |
| ----------------- | ---------------------------------- | ------------------------ | ------ |
| Object            |                                    |                          |        |
| txnId             | unque id for the transaction       | String                   |        |
| payerVpa          | payer name of the transaction      | String                   |        |
| payeeName         | payee name of the transaction      | String                   |        |
| txnMode           | mode of the transaction            | String                   |        |
| txnAmount         | trnasaction amount                 | String                   |        |
| approvalStatus    | approval status of the transaction | String                   |        |
| txnDesc           | transactiondescription             | String                   |        |
| wibmoRespCode     | api error response code            | int                      |        |
| wibmoResDesc      | api error description              | String                   |        |
| wibmoErrorMessage | api error message                  | String                   |        |
| currency          | trnasaction currency               | String                   |        |
| walletId          |                                    | String                   |        |
| txnDate           | transaction date                   | long                     |        |
| remarks           | remarks of the transaction         | String                   |        |
| refUrl            |                                    | String                   |        |
| trackingTxnStatus | list of Transaction status objecs  | List\<TrackingTxnStatus> |        |

| Response Field       | Field Description              | Data Type  | Length |
| -------------------- | ------------------------------ | ---------- | ------ |
| TrackingTxnStatus    |                                |            |        |
| id                   |                                | long       |        |
| txnNumber            | transaction number             | String     |        |
| txnStatusName        | status name of the transaction | String     |        |
| txnStatusDescription | description of the transaction | String     |        |
| createAt             | transaction created time       | Time stamp |        |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/collectrequest/v1/incoming' \
\--header 'X-PROGRAM-ID: 2001'
\--header 'X-LIMIT: 5'
\--header 'X-LAST-PROCESSED-ID: 10'
\--header 'Content-Type: text/plain'
--data-raw '{
    "txnId": "2023032329394944",
        "payerVpa": "Test@Vpa",
        "payeeVpa": null,
        "payeeName": null,
        "payerName": null,
        "txnAmount": "200",
        "currency": "INR",
        "approvalStatus": null,
        "remarks": null,
        "walletId": "321",
        "txnDate": 0,
        "udfParameters": null
}'
```
{% endcode %}
{% endtab %}

{% tab title="Sample Request" %}
```json
{
        "txnId": "2023032329394944",
        "payerVpa": "Test@Vpa",
        "payeeVpa": null,
        "payeeName": null,
        "payerName": null,
        "txnAmount": "200",
        "currency": "INR",
        "approvalStatus": null,
        "remarks": null,
        "walletId": "321",
        "txnDate": 0,
        "udfParameters": null
    }
```

```json
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
         "txnId": "2023032329394944",
        "payerVpa": "Test@VPA",
        "payeeVpa": null,
        "payeeName": null,
        "txnMode": null,
        "txnAmount": null,
        "approvalStatus": null,
        "txnDesc": null,
        "wibmoRespCode": 0,
        "wibmoResDesc": null,
        "wibmoErrorMessage": null,
        "currency": null,
        "walletId": null,
        "txnDate": 0,
        "remarks": null,
        "refUrl": null,
        "trackingTxnStatus": [
            {
                "id": 0,
                "txnNumber": null,
                "txnStatusName": null,
                "txnStatusDescription": null,
                "createAt": null
            }
        ]
    }
}
```
{% endtab %}
{% endtabs %}
