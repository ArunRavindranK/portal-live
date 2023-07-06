---
description: This api gives the status for the provided txn id.
---

# Check transaction Status

{% swagger method="post" path="/v1/txn/bnpltxnStatus" baseUrl="<domain>" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" type="String" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" type="String" %}
The token got from the 

[Get Token API](../../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnId" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="Integer" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="productId" type="Integer" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}

{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="" %}

{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Sample Curl Request" %}
```
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/txn/bnpltxnStatus' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: <REPLACE_WITH_TOKEN_FROM_GET_TOKEN_API_RESPONSE>' \
--data-raw '{"txnId":"202306160641519215kP78vS5",
"merchantId":76,
"productId":323}'
```
{% endtab %}

{% tab title="Sample Request" %}
```
{"txnId":"202306160641519215kP78vS5",
"merchantId":76,
"productId":323}
```
{% endtab %}

{% tab title="Sample Response" %}
```
{
    "resCode": "LND200",
    "resDesc": "SUCCESS",
    "data": {
        "txnDate": "2023-06-16 12:11:51",
        "txnStatus": "SUCCESS",
        "merchantId": 76,
        "merchantName": null,
        "productId": 323,
        "txnAmount": 500.0,
        "txnId": "202306160641519215kP78vS5",
        "lmsTxnReferenceId": "WIBM00100964"
    }
}
```
{% endtab %}
{% endtabs %}

### Response Details

| Response Body     | Data Type | Field Description    |
| ----------------- | --------- | -------------------- |
| resCode           | String    | Response Code        |
| resDesc           | String    | Response Description |
| txnDate           | String    | Transaction date     |
| txnStatus         | String    | Transaction status   |
| merchantId        | Integer   | Merchant Id          |
| merchantName      | String    | Merchant Name        |
| productId         | Integer   | product Id           |
| txnAmount         | double    | Transaction Amount   |
| txnId             | String    | Transaction Id       |
| lmsTxnReferenceId | String    | Lms refernce Id      |

### Custom Response Code

| Response Code  | Response Description                                  |
| -------------- | ----------------------------------------------------- |
| LND200         | Success                                               |
| LND039         | No data found                                         |
| LND009         | There seems to be a technical issue. Try again later. |
| LND040         | TxnId is mandatory                                    |
| LND008         | Merchant Id is mandatory                              |
