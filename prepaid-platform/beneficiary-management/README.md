---
description: >-
  "This module will be utilized to allow Full-KYCed wallet customers of client
  programs to pre-register beneficiaries so that they can transfer funds to the
  beneficiary"
---

# Beneficiary Management

Fund Transfers allowed through this Beneficiary management are:

1. Customer can transfer money to beneficiary’s bank account through A/C no & IFSC Code or Branch Name
2. Customer can transfer money to beneficiary’s bank account through UPI VPA
3. Customer can transfer money to beneficiary’s wallet that belongs to the same Client program managed by Wibmo Prepaid. However, Beneficiary wallet account must be Full-KYC. Self-transfer of money is not allowed. Ex: In Citruspay wallet, Wallet/Cardholder with customer ID 12345 and mobile no. 9712912345 cannot transfer money to mobile No. 9712912345
4. Customer can transfer money to beneficiary’s wallet that belongs to a different Client program managed by Wibmo Prepaid. However, Beneficiary wallet account must be Full-KYC. Self-transfer between programs can be allowed. Ex: Wallet/Cardholder with Customer ID 12345 and mobile No. 9712912345 (Citruspay wallet) can transfer money to Abhinaya with Customer ID 364826 and mobile No. 9712912345 (Tata Digital Wallet)
5. If one customer is registered for more than 1 client program wallet managed by Wibmo prepaid, then that Customer can transfer money from one client program wallet to another client program. However, the customer wallet account must be Full-KYC wallet in both programs

You can use the following APIs to perform beneficiary management on Prepaid Card/ Wallet for the customer:

<mark style="color:blue;">`Beneficiary Account Creation API`</mark>

<mark style="color:blue;">`View Beneficiary Accounts API`</mark>

<mark style="color:blue;">`Beneficiary Account Deletion API`</mark>

{% hint style="info" %}
This module is undergoing upgrade. The new specifications will be updated shortly.
{% endhint %}
