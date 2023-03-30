---
description: >-
  Wibmo Prepaid Platform APIs are completely RESTful and all our responses are
  returned in JSON.
cover: >-
  https://github.com/akshatknsl/wibmo-developer-live/blob/master/.gitbook/assets/documenting_web_apis%20(1).png
coverY: 0
---

# API Reference Guide

### API Authentication by generating x-api-key

All Prepaid Platform APIs are authenticated using `Key Auth`.

`Key Auth` expects an `x-api-key` header for each request

Please get in touch with your Wibmo representative to receive `x-api-key` to access our private sandbox environment.

Note that this `x-api-key` will be passed in the header of each, and every API request made to Wibmo Prepaid Platform. The `x-api-key` for Sandbox environment and production environment will be different

### Payload Encryption & Decryption

In order to ensure maximum security during the API calls, we recommend our clients to encrypt and decrypt the request and response payload respectively.

`Client Key (Secret Key)`: This key will be used to encrypt or decrypt the request or response using CBC mode. Please get in touch with your Wibmo representative to get the client encryption/ decryption key.

Algorithm: AES-192-CBC symmetric key-based encryption/decryption

### Message Code mapping of APIs

Prepaid platform provides a message code that is mapped against our API requests and responses. This message code will be passed as a request parameter by the client calling our APIs. Below showcases the list of APIs covered and its corresponding message codes

| Message Request Code | Message Response Code |             API            |
| :------------------: | :-------------------: | :------------------------: |
|         1010         |          1011         |         Create Card        |
|         1090         |          1091         |        Card Inquiry        |
|         1240         |          1241         |         Block Card         |
|         1250         |          1251         |        Unblock Card        |
|         3010         |          3011         |     Change Card Status     |
|         1120         |          1121         |          Reset PIN         |
|         1072         |          1073         |      Statement Inquiry     |
|         1080         |          1081         |       Credit Account       |
|         1480         |          1481         |        Debit Account       |
|         1990         |          1991         |     Load Unload Account    |
|         1550         |          1551         |         AML Inquiry        |
|         1680         |          1681         |        Fund Transfer       |
|         3020         |          3021         |      Verify Cardholder     |
|         1190         |          1191         |     Cardholder Profile     |
|         1930         |          1931         |    Retrieve Cust Record    |
|         2010         |          2011         | Create Beneficiary Account |
|         2020         |          2021         |  View Beneficiary Accounts |
|         2030         |          2031         | Delete Beneficiary Account |
|         2050         |          2051         |        Check Status        |
