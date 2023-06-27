# Payment - SDK Based

<figure><img src="../../../../.gitbook/assets/BankEzy Payment Flows-New - Payment Flow -  SDK.png" alt=""><figcaption></figcaption></figure>

1. To integrate for the SDK based approach,  different hash needs to be generated for all the required request to check the integrity of the request. Refer [**Generate Hash API**](api-specification/payment/version-2/hash-init-api.md) for the same.
2. Use [**Txn Status Update API**](api-specification/payment/version-2/txn-status-update-api.md) to update the txn status in case of failures like user abort&#x20;
