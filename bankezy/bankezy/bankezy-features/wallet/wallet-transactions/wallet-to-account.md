---
description: >-
  This section covers the APIs is used for a registered full KYC Bankezy wallet
  user able to transfer money from Bankezy wallet to any user's bank account/UPI
  handle.
---

# Wallet To Account



<figure><img src="../../../../../.gitbook/assets/Wallet - SendMoney Design - W2A.png" alt=""><figcaption><p>Wallet to Account transfer</p></figcaption></figure>

## Fetch and Add Beneficiary

* To fetch the list of beneficiaries refer [**Fetch Beneficiary API**](api-specification/version-2/beneficiary-bank-account-link/api-specification/fetch-beneficiary-account-api.md)
* To add the Beneficiary [**Add Beneficiary API**](api-specification/version-2/beneficiary-bank-account-link/api-specification/add-beneficiary-api.md)

## Fetch Source

This API helps fetch the list of source account/s from where money needs to be transferred

* To fetch the list of source accounts refer [**Fetch Accounts API**](api-specification/version-2/fetch-accounts-api.md)

## Send Money

This section is to address the flow to send money between wallet and account(vpa).&#x20;

* To send money validation needs to be done, therefore to validate the transaction refer [**Validation API** ](api-specification/version-2/wallet-to-account/api-specification/w2a-verification-api.md)
* To confirm to send money refer [**Send Money API**](api-specification/version-2/wallet-to-account/api-specification/send-money-api.md)

