---
description: This api is used to check the eligibility of the customer.
---

# Check Eligibility

{% swagger method="post" path="/v1/txn/bnplEligiblity" baseUrl="<domain>" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" type="String" %}
The token got from the 

[Get Token API](../../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" type="String" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productId" type="String" %}
product id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="double" required="true" %}
Amount to be validated 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" type="String" required="true" %}
mobile number
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

{% swagger-response status="501" description="" %}

{% endswagger-response %}
{% endswagger %}

### _Response_ Details

|             |        |                                    |
| ----------- | ------ | ---------------------------------- |
| resCode     | String | Response code                      |
| resDesc     | String | Response description               |
| eligibility | String | returns eligibile or not eligibile |
| mobile      | String | mobile Number                      |

{% tabs %}
{% tab title="Sample Curl Request" %}
```
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/txn/bnplEligiblity' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: <REPLACE_WITH_TOKEN_FROM_GET_TOKEN_API_RESPONSE>' \
--data-raw '{"amount":12000,
"mobile":"9955031544",
"productId":"323"}'
```
{% endtab %}

{% tab title="Request Example" %}
```
{"amount":12000,
"mobile":"9955031544",
"productId":"323"
```
{% endtab %}

{% tab title="Response Example" %}
```
{
    "resCode": "LND200",
    "resDesc": "SUCCESS",
    "data": {
        "eligibility": "Eligible",
        "mobile": "8699999999"
    }
}
```
{% endtab %}
{% endtabs %}

### Custom Response codes

| Response Code | Response Description                                 |
| ------------- | ---------------------------------------------------- |
| LND200        | Success                                              |
| LND038        | Customer with mobile number not registered.          |
| LND009        | There seems to be a technical issue. Try again later |
| LND025        | Invalid Amount                                       |
| LND005        | Mobile Number is Mandatory                           |
