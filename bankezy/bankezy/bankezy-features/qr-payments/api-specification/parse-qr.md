---
description: >-
  The API is intended to read and validate the QR string. Parse and validate the
  QR string according to the configuration
---

# Parse QR



{% swagger method="post" path="   " baseUrl="<domain> /qrTxn/v1/qr-detail" summary="" %}
{% swagger-description %}
A QR String is passed in the request body, the qr parser identifies the QR format and validate the QR. In case of validation error in raw string, application will return invalid exception
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" type="String" %}
MOB-APP
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" type="String" %}
The token got from the 

[login API](../../wallet/wallet-issuance/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../wallet/wallet-issuance/customer-on-boarding/common-apis/get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="rawString" type="String" required="true" %}
raw QR string
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" %}
text/json
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

| Error code | Description         |
| ---------- | ------------------- |
| 200        | Success             |
| 100        | Invalid input value |
| 101        | Parser not found    |

{% tabs %}
{% tab title="Sample Curl" %}
```html
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/qrTxn/v1/qr-detail' \
--header 'X-API-TOKEN: Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJDTElFTlRfQVBQX1NESyIsIlRPS0VOX0VYUElSWSI6OTAwLCJSRUZFUkVOQ0VfSUQiOiIwMjNhZjQxOC0zODc2LTRmNDEtYmMzZS02NDUyMGI3NzExY2EiLCJDTElFTlRfSU5GTyI6IntcImZpcnN0TmFtZVwiOlwiUHJlbSBLdW1hclwiLFwic2RrQXBpS2V5XCI6XCJNT0ItQVBQLTIwMDFcIixcImxhc3ROYW1lXCI6bnVsbCxcImFjY291bnROdW1iZXJcIjoxMjM0NTY4MDQ2LFwiaXNkQ29kZVwiOjAsXCJtb2JpbGVOdW1iZXJcIjo2MzAzOTM4ODI4LFwiZG9iXCI6MCxcImVtYWlsXCI6XCJwcmVta3VtYXJzODgyOEBnbWFpbC5jb21cIixcInNka1B1YmxpY0tleVwiOlwiZXlKcmRIa2lPaUpGUXlJc0ltTnlkaUk2SWxBdE1qVTJJaXdpZUNJNklrdEpYMjR4Vm00dFVEWkhWREJMZW5oTGNVc3dTa1kwY1U1blFXTkRTazl1Y1VjM1dVdDNWR3A1VUZFaUxDSjVJam9pYld4VU9XZHlNMlY1WmtZelZtVkZlVFkwWHpkd056RjVTSEU1V1hSVGNtSnVMV2RyY1hwU2MyVlBkeUo5XCIsXCJyZWZlcmVuY2VJZFwiOm51bGwsXCJkYXRhXCI6bnVsbH0iLCJBTExPV0VEX0lQUyI6IioiLCJpc3MiOiJnZ2RUeUx3ZW92ZUtyRlFzeDNuY3NmZ0RrdjhBdEZBeiIsIlVTRVJfSUQiOjEyMzQ1NjgwNDYsIkxPR0lOX0hJU1RPUllfSUQiOiIwMjNhZjQxOC0zODc2LTRmNDEtYmMzZS02NDUyMGI3NzExY2EiLCJYLUFDQ09VTlQtTlVNQkVSIjoxMjM0NTY4MDQ2LCJleHAiOjE2NzAwNDM3ODQsIlBST0dSQU1fSUQiOjExMTEsImlhdCI6MTY2OTk4OTc4NH0.LY0SBt30t0kI3n74p4Ltp6Xdxe4LHpzpozQEUmxEmSBmOiCsC0CByf5hePWDnvMnVc--aUkg6MAk6vjDEwHRMg' \
--header 'X-API-KEY: MOB-APP' \
--header 'Content-Type: application/json' \
--header 'Cookie: JSESSIONID=CDEFC72D62F3986D4B3084A3C59EFC30; JSESSIONID=76E34EE8ED81BB6CF077A4C8877BC74E' \
--data-raw '{
    "rawString": "00020101021127850012com.p2pqrpay0111CHBKPHMMXXX0208999644030315998001234567890041953004569871352463215204601653036085802PH5912JUANDELACRUZ6011Mandaluyong621705062110000803***6304B610"
}'
```
{% endtab %}

{% tab title="Request Body" %}
```json
{
    "rawString": "00020101021127850012com.p2pqrpay0111CHBKPHMMXXX0208999644030315998001234567890041953004569871352463215204601653036085802PH5912JUANDELACRUZ6011Mandaluyong621705062110000803***6304B610"
}
```
{% endtab %}

{% tab title="Response Body" %}
```json
{
    "resCode": "200",
    "resDesc": "Success",
    "data": {
        "commonQrInfo": {
            "payloadFormat": "01",
            "pointOfInit": "11",
            "paymentSystemUniqueId": "com.p2pqrpay",
            "acquirerId": "CHBKPHMMXXX",
            "paymentType": "",
            "payeeUpiId": "",
            "payeeName": "",
            "payeeMcc": "",
            "mcc": "6016",
            "merchCreditAccount": "5300456987135246321",
            "proxyType": "",
            "proxyNotificationFlag": "",
            "proxyUpdateFlag": "",
            "countryCode": "PH",
            "tip": "",
            "convenienceFee": "",
            "convenienceFeePercent": "",
            "merchName": "JUANDELACRUZ",
            "merchCity": "Mandaluyong",
            "txnAmount": "",
            "txnCountryCode": "",
            "txnCurrencyCode": "608",
            "txnFeeVal": "",
            "txnFeePercent": "",
            "txnType": "",
            "referenceId": "",
            "qrMedium": "",
            "invoiceNo": "",
            "invoiceDate": "",
            "minimumAmount": "",
            "currencyCode": "",
            "merchId": "99964403",
            "storeId": "",
            "additionalInfo": {
                "reference": "211000",
                "transactionType": "P2P",
                "mPaymentReferenceId": "",
                "feeAmount": "0.0",
                "purpose": "***",
                "mPaymentSystemUniqueId": "",
                "feePercentage": "2",
                "qrType": "PHQR"
            }
        }
    }
}
```
{% endtab %}
{% endtabs %}

