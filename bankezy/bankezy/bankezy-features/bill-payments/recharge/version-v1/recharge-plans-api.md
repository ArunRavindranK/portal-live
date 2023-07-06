---
description: To provide availiable plans for the given operator and circle combination
---

# Recharge Plans API

{% swagger method="get" path="/retail-service/plans/list/v1" baseUrl="<domain>" summary="To provide availiable plans for the given operator and circle combination" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[Get Token API](../../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="circleId" required="true" %}
Unique identifier of the circle
{% endswagger-parameter %}

{% swagger-parameter in="body" name="operatorPrefix" required="true" %}
Short code indicating the region of the operator
{% endswagger-parameter %}

{% swagger-parameter in="body" name="serviceId" %}
Indicates the type of the service request
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
will be shared upon onboarding api consumers (clients)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
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
{% endswagger %}

## Response Details

<table><thead><tr><th width="176">Response Body</th><th>Data Type</th><th>Field Description</th></tr></thead><tbody><tr><td>statusCode</td><td>int</td><td>status code of transaction</td></tr><tr><td>statusDesc</td><td>String</td><td>Status Description </td></tr><tr><td>category</td><td>String</td><td>Name of the category</td></tr><tr><td>operatorName</td><td>String</td><td>Name of the operator</td></tr><tr><td>operatorId</td><td>String</td><td>Unique identifier for the operator</td></tr><tr><td>circleName</td><td>String</td><td>Region of the operator</td></tr><tr><td>circleId</td><td>int</td><td>Id indicating the region of the operator</td></tr><tr><td>planName</td><td>String</td><td>Description of the plan in detail</td></tr><tr><td>amount</td><td>String</td><td>Transactional amount</td></tr><tr><td>validity</td><td>String</td><td>Validity of the plan</td></tr><tr><td>talkTime</td><td>String</td><td>Talktime associated with the plan</td></tr><tr><td>validityDescription</td><td>String</td><td>Description of the plan</td></tr><tr><td>packageDescription</td><td>String </td><td>Short description of the plan</td></tr><tr><td>status</td><td>int</td><td>Indicates whether the recharge plan is active are not</td></tr></tbody></table>

{% tabs %}
{% tab title="sample curl  Request" %}
```json
curl --location --request POST 'https://app9.pcdev.enstage-sas.com/retail-service/plans/list/v1' \
--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw' \
--header 'X-API-KEY: MOB-APP-2001' \
--data-raw '{
  "circleId": 22,
  "operatorPrefix": "VF",
  "serviceId": 0
}'
```


{% endtab %}

{% tab title="Request Example" %}
```json
{
  "circleId": 22,
  "operatorPrefix": "VF",
  "serviceId": 0
}
```


{% endtab %}

{% tab title="Response Example" %}
```json
{
    "statusCode": 200,
    "statusDesc": "Success",
    "data": [
        {
            "category": "",
            "planDetailsList": [
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "95.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get 50 Local + STD Minutes ,28 Day Validity. No Service Validity.No Outgoing SMS.",
                    "planType": "OTHER PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "COMBO PACK",
                    "amount": "128.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get 10 Local On-net Night Minutes + All Local/National Calls at 2.5 paise/sec + Night minutes benefit available from 23:00 Hrs to 06:00 Hrs + Outgoing SMS - Rs 1/1.5/5 for Local/STD/ISD.",
                    "planType": "COMBO PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "INTERNET PACK",
                    "amount": "98.0",
                    "validity": "21 Days",
                    "talkTime": "0.00",
                    "validityDescription": "21 Days",
                    "packageDescription": "Get 9 GB Data.",
                    "planType": "INTERNET PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "TOPUP PLAN",
                    "amount": "10.0",
                    "validity": "0 Days",
                    "talkTime": "7.47",
                    "validityDescription": "0 Days",
                    "packageDescription": "Get Talktime of Rs. 7.47.",
                    "planType": "TOPUP PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "TOPUP PLAN",
                    "amount": "20.0",
                    "validity": "0 Days",
                    "talkTime": "14.95",
                    "validityDescription": "0 Days",
                    "packageDescription": "Get Talktime of Rs. 14.95.",
                    "planType": "TOPUP PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "TOPUP PLAN",
                    "amount": "30.0",
                    "validity": "0 Days",
                    "talkTime": "22.42",
                    "validityDescription": "0 Days",
                    "packageDescription": "Get Talktime of Rs. 22.42.",
                    "planType": "TOPUP PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "TOPUP PLAN",
                    "amount": "50.0",
                    "validity": "0 Days",
                    "talkTime": "39.37",
                    "validityDescription": "0 Days",
                    "packageDescription": "Get Talktime of RS. 39.37 .",
                    "planType": "TOPUP PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "TOPUP PLAN",
                    "amount": "100.0",
                    "validity": "0 Days",
                    "talkTime": "81.75",
                    "validityDescription": "0 Days",
                    "packageDescription": "Get Talktime of Rs. 81.75.",
                    "planType": "TOPUP PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "TOPUP PLAN",
                    "amount": "500.0",
                    "validity": "0 Days",
                    "talkTime": "423.73",
                    "validityDescription": "0 Days",
                    "packageDescription": "Get Talktime of Rs. 423.73.",
                    "planType": "TOPUP PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "TOPUP PLAN",
                    "amount": "1000.0",
                    "validity": "0 Days",
                    "talkTime": "847.46",
                    "validityDescription": "0 Days",
                    "packageDescription": "Get Talktime of Rs. 4237.29.",
                    "planType": "TOPUP PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "TOPUP PLAN",
                    "amount": "5000.0",
                    "validity": "0 Days",
                    "talkTime": "4237.29",
                    "validityDescription": "0 Days",
                    "packageDescription": "Get Talktime of Rs. 847.46.",
                    "planType": "TOPUP PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "INTERNET PACK",
                    "amount": "19.0",
                    "validity": "24 Hours",
                    "talkTime": "0.00",
                    "validityDescription": "24 Hours",
                    "packageDescription": "Get 1 GB Data .",
                    "planType": "INTERNET PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "COMBO PACK",
                    "amount": "99.0",
                    "validity": "28 Days",
                    "talkTime": "99.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Rs 99 Limited Validity Talktime + 200 MB Data + 1p/sec Voice traffic. No Outgoing SMS.",
                    "planType": "COMBO PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "109.0",
                    "validity": "15 Days",
                    "talkTime": "0.00",
                    "validityDescription": "15 Days",
                    "packageDescription": "Get Unlimited Calls + 200 MB Data. No Outgoing SMS.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "129.0",
                    "validity": "18 Days",
                    "talkTime": "0.00",
                    "validityDescription": "18 Days",
                    "packageDescription": "Get Unlimited Calls + 200 MB Data. No Outgoing SMS.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "149.0",
                    "validity": "21 Days",
                    "talkTime": "0.00",
                    "validityDescription": "21 Days",
                    "packageDescription": "Get Unlimited Calls + 1 GB Data. No Outgoing SMS.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "199.0",
                    "validity": "18 Days",
                    "talkTime": "0.00",
                    "validityDescription": "18 Days",
                    "packageDescription": "Get Unlimited Calls + 1 GB/Day Data + 100 SMS/Day + Vi Movies & TV Basic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "219.0",
                    "validity": "21 Days",
                    "talkTime": "0.00",
                    "validityDescription": "21 Days",
                    "packageDescription": "Get Unlimited Calls + 1 GB/Day Data + 100 SMS/Day + Vi Movies & TV Basic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "249.0",
                    "validity": "21 Days",
                    "talkTime": "0.00",
                    "validityDescription": "21 Days",
                    "packageDescription": "Get Unlimited Calls + 1.5 GB/Day Data + 100 SMS/Day + Vi Movies & TV Basic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "269.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Unlimited Calls + 1 GB/Day Data + 100 SMS/Day + Vi Movies & TV Basic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "299.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Unlimited Calls + 1.5 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "399.0",
                    "validity": "42 Days",
                    "talkTime": "0.00",
                    "validityDescription": "42 Days",
                    "packageDescription": "Get Unlimited Calls + 1.5 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "499.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get 2 GB/Day Data + Unlimited Calls + 100 SMS/Day + 1 year Disney+ Hotstar Mobile subscription + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "599.0",
                    "validity": "70 Days",
                    "talkTime": "0.00",
                    "validityDescription": "70 Days",
                    "packageDescription": "Get Unlimited Calls + 1.5 GB/day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "601.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Unlimited Calls + 3 GB/Day Data + 16 GB Extra Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV VIP access + 1 year Disney+ Hotstar Mobile subscription.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "699.0",
                    "validity": "56 Days",
                    "talkTime": "0.00",
                    "validityDescription": "56 Days",
                    "packageDescription": "Get Unlimited Calls + 3 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV VIP access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "32.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get access to Over 200 Popular Ad-free Games for 28 Days.",
                    "planType": "OTHER PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "42.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Unlimited SMS score alerts for on-going Cricket match and Chance to talk to Sports celebrity (Min 5 event in a month).",
                    "planType": "OTHER PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "43.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Recharge with Contest Pack and get a chance to win cool gratification – Recharge & Gold Vouchers and More, Pack validity 28 Days.",
                    "planType": "OTHER PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "52.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Now Enjoy Live Chat with Bollywood celebrity, (Min 5 event in a month), Pack validity 28 Days.",
                    "planType": "OTHER PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "62.0",
                    "validity": "89 Days",
                    "talkTime": "0.00",
                    "validityDescription": "89 Days",
                    "packageDescription": "Get access to Over 200 Popular Ad-free Games for 89 Days.",
                    "planType": "OTHER PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "72.0",
                    "validity": "89 Days",
                    "talkTime": "0.00",
                    "validityDescription": "89 Days",
                    "packageDescription": "Get Unlimited SMS score alerts for on-going Cricket match and Chance to talk to Sports celebrity (Min 5 event in a month). Pack validity 89 Days.",
                    "planType": "OTHER PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "73.0",
                    "validity": "89 Days",
                    "talkTime": "0.00",
                    "validityDescription": "89 Days",
                    "packageDescription": "Get Recharge with Contest Pack and get a chance to win cool gratification – Recharge & Gold Vouchers and More, Pack validity 89 Days.",
                    "planType": "OTHER PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "103.0",
                    "validity": "89 Days",
                    "talkTime": "0.00",
                    "validityDescription": "89 Days",
                    "packageDescription": "Get Now Enjoy Live Chat with Bollywood celebrity, (Min 5 event in a month), Pack validity 89 Days.",
                    "planType": "OTHER PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "47.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Callertunes With Unlimited Song Change at Rs. 47 for 28 days.",
                    "planType": "OTHER PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "51.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Rs. 1000/Day Hospicare cover. 10 Days at a time, 30 Days/yr + 1 GB Data. No Outgoing SMS. Validity for 28Days. Zero Talktime. No Service validity. For 18-55yrs with sound health in non-hazardous jobs. Insurance as per name in VIL records. TnC.",
                    "planType": "OTHER PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "78.0",
                    "validity": "89 Days",
                    "talkTime": "0.00",
                    "validityDescription": "89 Days",
                    "packageDescription": "Get Callertunes With Unlimited Song Change at Rs. 78 for 89 days.",
                    "planType": "OTHER PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "901.0",
                    "validity": "70 Days",
                    "talkTime": "0.00",
                    "validityDescription": "70 Days",
                    "packageDescription": "Get Unlimited Calls + 3 GB/Day Data + 48 GB EXTRA Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV VIP access + 1 year Disney+ Hotstar Mobile subscription.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "COMBO PACK",
                    "amount": "107.0",
                    "validity": "30 Days",
                    "talkTime": "107.00",
                    "validityDescription": "30 Days",
                    "packageDescription": "Get Rs 107 Limited validity talktime + Calls at 1p/sec + 200 MB Data. No Outgoing SMS.",
                    "planType": "COMBO PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "COMBO PACK",
                    "amount": "111.0",
                    "validity": "31 Days",
                    "talkTime": "111.00",
                    "validityDescription": "31 Days",
                    "packageDescription": "Get Rs 111 Limited validity talktime + Calls at 1p/sec + 200 MB Data. No Outgoing SMS.",
                    "planType": "COMBO PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "COMBO PACK",
                    "amount": "137.0",
                    "validity": "30 Days",
                    "talkTime": "0.00",
                    "validityDescription": "30 Days",
                    "packageDescription": "Get 10 Local On-net Night Minutes + All Local/National Calls at 2.5 paise/sec + Night minutes benefit available from 2300 Hrs to 0600 Hrs + Outgoing SMS - Rs 1/1.5/5 for Local/STD/ISD.",
                    "planType": "COMBO PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "COMBO PACK",
                    "amount": "141.0",
                    "validity": "31 Days",
                    "talkTime": "0.00",
                    "validityDescription": "31 Days",
                    "packageDescription": "Get 10 Local On-net Night Minutes + All Local/National Calls at 2.5 paise/sec + Night minutes benefit available from 2300 Hrs to 0600 Hrs + Outgoing SMS - Rs 1/1.5/5 for Local/STD/ISD",
                    "planType": "COMBO PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "INTERNET PACK",
                    "amount": "58.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get 3 GB Data.",
                    "planType": "INTERNET PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "INTERNET PACK",
                    "amount": "118.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get 12 GB Data.",
                    "planType": "INTERNET PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "INTERNET PACK",
                    "amount": "298.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get 50 GB Data.",
                    "planType": "INTERNET PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "INTERNET PACK",
                    "amount": "418.0",
                    "validity": "56 Days",
                    "talkTime": "0.00",
                    "validityDescription": "56 Days",
                    "packageDescription": "Get 100 GB Data.",
                    "planType": "INTERNET PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "INTERNET PACK",
                    "amount": "999.0",
                    "validity": "365 Days",
                    "talkTime": "0.00",
                    "validityDescription": "365 Days",
                    "packageDescription": "Get 50 GB Data.",
                    "planType": "INTERNET PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "155.0",
                    "validity": "24 Days",
                    "talkTime": "0.00",
                    "validityDescription": "24 Days",
                    "packageDescription": "Get Unlimited Calls + 1 GB Data + 300 SMS.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "179.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Unlimited Calls + 2 GB Data + 300 SMS + Vi Movies & TV Basic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "195.0",
                    "validity": "31 Days",
                    "talkTime": "0.00",
                    "validityDescription": "31 Days",
                    "packageDescription": "Get Unlimited Calls + 2 GB Data + 300 SMS.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "209.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Unlimited Calls + 4 GB Data + 100 SMS/day + Vi Movies & TV Basic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "239.0",
                    "validity": "24 Days",
                    "talkTime": "0.00",
                    "validityDescription": "24 Days",
                    "packageDescription": "Get Unlimited Calls + 1 GB/Day Data + 100 SMS/Day.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "319.0",
                    "validity": "31 Days",
                    "talkTime": "0.00",
                    "validityDescription": "31 Days",
                    "packageDescription": "Get 2 GB/Day Data + Unlimited Calls + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Up to 2 GB of backup Data every month + Vi Movies & TV Classic Access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "327.0",
                    "validity": "30 Days",
                    "talkTime": "0.00",
                    "validityDescription": "30 Days",
                    "packageDescription": "Get Unlimited Calls + 25 GB Data + 100 SMS/Day + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "329.0",
                    "validity": "56 Days",
                    "talkTime": "0.00",
                    "validityDescription": "56 Days",
                    "packageDescription": "Get Unlimited Calls + 4 GB Data + 600 SMS + Vi Movies & TV Basic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "337.0",
                    "validity": "31 Days",
                    "talkTime": "0.00",
                    "validityDescription": "31 Days",
                    "packageDescription": "Get 28 GB Data + Unlimited Calls + 100 SMS/Day + Vi Movies & TV Classic Access",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "359.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Unlimited Calls + 3 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "409.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Unlimited Calls + 3.5 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV VIP access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "459.0",
                    "validity": "84 Days",
                    "talkTime": "0.00",
                    "validityDescription": "84 Days",
                    "packageDescription": "Get Unlimited Calls + 6 GB Data + 1000 SMS + Vi Movies & TV Basic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "475.0",
                    "validity": "28 Days",
                    "talkTime": "0.00",
                    "validityDescription": "28 Days",
                    "packageDescription": "Get Unlimited Calls + 4 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV VIP access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "479.0",
                    "validity": "56 Days",
                    "talkTime": "0.00",
                    "validityDescription": "56 Days",
                    "packageDescription": "Get Unlimited Calls + 1.5 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "537.0",
                    "validity": "60 Days",
                    "talkTime": "0.00",
                    "validityDescription": "60 Days",
                    "packageDescription": "Get Unlimited Calls + 50 GB Data + 100 SMS/Day + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "539.0",
                    "validity": "56 Days",
                    "talkTime": "0.00",
                    "validityDescription": "56 Days",
                    "packageDescription": "Get Unlimited Calls + 2 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "666.0",
                    "validity": "77 Days",
                    "talkTime": "0.00",
                    "validityDescription": "77 Days",
                    "packageDescription": "Get Unlimited Calls + 1.5 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "719.0",
                    "validity": "84 Days",
                    "talkTime": "0.00",
                    "validityDescription": "84 Days",
                    "packageDescription": "Get Unlimited Calls + 1.5 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "839.0",
                    "validity": "84 Days",
                    "talkTime": "0.00",
                    "validityDescription": "84 Days",
                    "packageDescription": "Get Unlimited Calls + 2 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "1066.0",
                    "validity": "84 Days",
                    "talkTime": "0.00",
                    "validityDescription": "84 Days",
                    "packageDescription": "Get 2 GB/Day Data + Unlimited Calls + 100 SMS/Day + 1 year Disney+ Hotstar Mobile subscription + Enjoy Night data without limits from 12am to 6am + Weekend data rollover + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "1449.0",
                    "validity": "180 Days",
                    "talkTime": "0.00",
                    "validityDescription": "180 Days",
                    "packageDescription": "Get Unlimited Calls + 1.5 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "1799.0",
                    "validity": "365 Days",
                    "talkTime": "0.00",
                    "validityDescription": "365 Days",
                    "packageDescription": "Get Unlimited Calls + 24 GB Data + 3600 SMS + Vi Movies & TV Basic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "2899.0",
                    "validity": "365 Days",
                    "talkTime": "0.00",
                    "validityDescription": "365 Days",
                    "packageDescription": "Get Unlimited Calls + 1.5 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV Classic access.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "UNLIMITED PACK",
                    "amount": "3099.0",
                    "validity": "365 Days",
                    "talkTime": "0.00",
                    "validityDescription": "365 Days",
                    "packageDescription": "Get Unlimited Calls + 2 GB/Day Data + 100 SMS/Day + Enjoy Night data without limits from 12am to 6am + Weekend Data Rollover + Vi Movies & TV VIP access + 1 year Disney+ Hotstar Mobile subscription.",
                    "planType": "UNLIMITED PACK",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "26.0",
                    "validity": "1 Day",
                    "talkTime": "0.00",
                    "validityDescription": "1 Day",
                    "packageDescription": "Get 1 platinum game credit. You can use this to download 1 platinum game. Platinum game credit will expire after 3 days.",
                    "planType": "OTHER PLAN",
                    "status": 1
                },
                {
                    "operatorName": "VODAFONE",
                    "operatorId": "VF",
                    "circleName": "KOLKATA",
                    "circleId": 22,
                    "planName": "OTHER PLAN",
                    "amount": "56.0",
                    "validity": "30 Days",
                    "talkTime": "0.00",
                    "validityDescription": "30 Days",
                    "packageDescription": "Get 30 gold game credits. You can use this to download 30 gold games. Gold game credits will expire after 30 days. To play gold games you have to have a active gold games pack. This is not a subscription service.",
                    "planType": "OTHER PLAN",
                    "status": 1
                }
            ]
        }
    ]
}son
```


{% endtab %}
{% endtabs %}
