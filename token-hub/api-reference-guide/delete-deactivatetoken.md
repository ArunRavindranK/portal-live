# Delete / DeactivateToken

Card holder can delete token from the merchant website/app. This API is used by the merchants / payment aggregators to deactivate the token.

{% swagger method="post" path="" baseUrl="/tokenVault/v1/token/delete" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

Sample Request

{% tabs %}
{% tab title="Curl" %}
```
curl --location --request POST 'http://<sandbox>/tokenVault/v1/token/delete' \
--header 'Content-Type: application/json' \
--header 'X-Auth-Token: ' \
--header 'clientId: ' \
--header 'clientApiUser: ' \
--header 'clientApiKey: ' \
--data-raw '{
    "tokenReferenceId": "MC000014413895e6490faae1a680ef77af7b",
    "causedBy": "CARDHOLDER",
    "reason": "Lost/Stolen Device",
    "reasonCode": "SUSPECTED_FRAUD",
    "cardType": "V"
}'
```
{% endtab %}

{% tab title="Response" %}
```
{
    "statusCode": "TK0000",
    "errorDesc": null,
    "status": "Success",
    "msg": null,
    "transactionId": null,
    "tokenReferenceId": "MC000014413895e6490faae1a680ef77af7b",
    "tokenStatus": "DEACTIVATED"
}
```
{% endtab %}
{% endtabs %}
