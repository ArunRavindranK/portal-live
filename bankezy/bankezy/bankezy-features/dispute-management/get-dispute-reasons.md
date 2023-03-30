# Get Dispute Reasons

User can select a transaction and register that as a complaint. With this API , The Dispute Reason code applicable for the transaction ( based on transaction channel) will be retrieved and displayed to User

{% swagger method="get" path="/reasons" baseUrl="/dispute-management/v1" summary="Get the Defined Dispute Reason for the payment Channel" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="channelType" required="true" %}
Payment Channel
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
Tenant ID
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful Response" %}
```javascript
{"resDesc": "SUCCESS",
    "data": [
        {
            "reasonCode": "BBPS001",
            "reasonDesc": "Transaction Successful, account not updated"
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

| Response Body   | Data Type |                                  |
| --------------- | --------- | -------------------------------- |
| resCode         | Int       | Response Code                    |
| resDesc         | String    | Description of Response          |
| Data.reasonCode | String    | Reason code For Complaint        |
| Data.reasonDesc | String    | Reason Description for complaint |

{% tabs %}
{% tab title=" Sample curl Request" %}
```json
curl --location --request POST 'http://localhost:7080/dispute-management/v1/reasons' \
--header 'X-PROGRAM-ID: 1111' \
--header 'Content-Type: application/json' \
--header 'Cookie: JSESSIONID=D4B7F328303F61FF87006C4BCE043A07' \
--data-raw '{
    "channelType":"NONBBPS"
}'
```
{% endtab %}

{% tab title="Request Sample " %}


```
request:
{
"channelType":"BBPS"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
response:
	{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": [
        {
            "reasonCode": "BBPS001",
            "reasonDesc": "Transaction Successful, account not updated"
        },
        {
            "reasonCode": "BBPS002",
            "reasonDesc": "Amount deducted, biller account credited but transaction ID not received"
        },
        {
            "reasonCode": "BBPS003",
            "reasonDesc": "Amount deducted, biller account not credited & transaction ID not received"
        },
        {
            "reasonCode": "BBPS004",
            "reasonDesc": "Amount deducted multiple times"
        },
        {
            "reasonCode": "BBPS005",
            "reasonDesc": "Double payment updated"
        },
        {
            "reasonCode": "BBPS006",
            "reasonDesc": "Erroneously paid in wrong account"
        },
        {
            "reasonCode": "BBPS007",
            "reasonDesc": "Others, provide details in description"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
