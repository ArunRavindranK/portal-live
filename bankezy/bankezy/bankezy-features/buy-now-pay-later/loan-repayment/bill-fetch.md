---
description: >-
  This API list down the Bill details for the user. It gets the last billed
  amount, billing period and due date for the user.
---

# Bill Fetch

{% swagger method="get" path="/lending/v1/bill" baseUrl="<domain>" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
Token got from Validate Token API
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

{% swagger-response status="401: Unauthorized" description="" %}
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

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location --request GET 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/bill' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: <REPLACE_WITH_TOKEN_FROM_VALIDATE_TOKEN_API_RESPONSE>'
```
{% endtab %}

{% tab title="Response Example" %}
```json
{
    "resCode": "LND_200",
    "resDesc": "SUCCESS",
    "data": {
        "availableLimit": 93500,
        "name": "Ankit Prakash",
        "bill": {
            "startDate": 1640131200000,
            "endDate": 1663804800000,
            "dueDate": 0,
            "amount": 234400,
            "minimumAmountDue": 23300,
            "interest": null,
            "processingFee": null
        }
    }
}
```
{% endtab %}
{% endtabs %}

### Response Details

| Response Body            | Data Type | Field Description             |
| ------------------------ | --------- | ----------------------------- |
| availableLimit           | Integer   | Available Limit for Customer  |
| name                     | String    | Customer name                 |
| outstandingAmt           | Double    | outstanding amount to be paid |
| spentAmt                 | Double    | Spent amount                  |
| nextDueDate              | Long      | next due date to pay the bill |
| cycleStartDate           | Long      | cycle start date in ms        |
| cycleEndDate             | Long      | cycle end date in ms          |
| bill.billId              | Long      | Bill Id                       |
| bill.startDate           | Long      | bill start date in ms         |
| bill.endDate             | Long      | bill end date in ms           |
| bill.dueDate             | Long      | bill due date in ms           |
| bill.amount              | Integer   | bill amount to be paid        |
| bill.minimumAmountDue    | Integer   | minimum Amount due to be paid |
| bill.interest            | String    | interest amount               |
| bill.processingFee       | String    | processing fee                |
| bill.dailyInterestAmount | Integer   | daily interest Amount         |
| resCode                  | String    | Response Code                 |
| resDesc                  | String    | Response Description          |

### Custom Response Code

| Response Codes | Response Description                                  |
| -------------- | ----------------------------------------------------- |
| LND029         | NOT FOUND                                             |
| LND200         | SUCCESS                                               |
| LND009         | There seems to be a technical issue. Try again later. |
