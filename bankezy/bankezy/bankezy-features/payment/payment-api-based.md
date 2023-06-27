# Payment - API Based

<figure><img src="../../../../.gitbook/assets/BankEzy Payment Flows-New - Payment Flow -  API based (2).png" alt=""><figcaption></figcaption></figure>

1. Use [**Payment Modes API**](api-specification/payment/version-2/fetch-payment-mode-api.md) to get the supported list of Payment source for the onboarded merchant along with list of linked payment instruments user has linked to their account.
2. To get the list of banks supporting Net banking txn refer [**Get NB Bank List API**](api-specification/payment/version-2/fetch-top-banks-api.md)

### Card Transaction:

1. Use [**Txn Auth API**](api-specification/payment-authentication/version-2/card-authentication/authentication-api.md) to authenticate the txn.
2. Refer [**Verify IVR API**](api-specification/payment/version-2/verify-ivr-api.md) to authenticate the txn if the issuer supports IVR authentication.
3. Use [**Txn Status Update API**](api-specification/payment/version-2/txn-status-update-api.md)[ ](api-specification/payment/version-2/txn-status-update-api.md)to update the txn status in case of failures like user abort&#x20;

### NetBanking Transaction:

1. Use [**NB Txn** **Auth API** ](api-specification/payment-authentication/version-2/net-banking-authentication/initiate-authentication-api.md)to authenticate the txn.
2. Use [**Txn Status Update API**](api-specification/payment/version-2/txn-status-update-api.md) to update the txn status in case of failures like user abort&#x20;
