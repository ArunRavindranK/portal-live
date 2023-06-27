---
description: >-
  This Api helps to return last transaction details. Last transaction details
  are saved as facourite transaction.
---

# Fetch favourite transaction



{% swagger method="get" path="" baseUrl="<domain>/merchant/user/favourite/payment/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" type="long" required="true" %}
customer registered unique number
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
tenant identification number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" required="true" %}
This is required to know the  favourite payment method for the merchant
{% endswagger-parameter %}

{% swagger-parameter in="body" name="categoryId" %}
This is required to know the favourite payment method for the merchant category
{% endswagger-parameter %}
{% endswagger %}

{% tabs %}
{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'http://localhost:2442/merchant/user/favourite/payment/v1' \
--header 'X-ACCOUNT-NUMBER: 665' \
--header 'X-PROGRAM-ID: 1111' \
--header 'Content-Type: application/json' \
--header 'Cookie: JSESSIONID=B63987D7CC61C57412E093A30F68E176' \
--data-raw '{
    "merchantId":81516121,
    "categoryId":0
}'
```
{% endtab %}

{% tab title="Request" %}
```json5
{
    "merchantId":81516121,
    "categoryId":0
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "merchantId": 81516121,
        "categoryId": 0,
        "accountNumber": 665,
        "paymentDetails": {
            "refId": "810",
            "cardAssociationId": "V",
            "aliasName": "Rakesh Biswal",
            "nameOnCard": "Rakesh Biswal",
            "cardType": "Credit",
            "cardMask": "**** **** **** 3153",
            "paymentMode": "LC",
            "bankName": "HDFC"
        }
    }
}
```
{% endtab %}
{% endtabs %}
