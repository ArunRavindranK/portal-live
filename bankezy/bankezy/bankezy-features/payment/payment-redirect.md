# Payment - Redirect

<figure><img src="../../../../.gitbook/assets/BankEzy Payment Flows-New - Payment Flow - Redirect.png" alt=""><figcaption></figcaption></figure>

1. To integrate for the Redirect based approach, load the redirectFormAction url from the  Payment Params API or QR Init API with the required data like merchant id, txn id and api key. Refer [**PG Connect API**](api-specification/payment/version-2/connect-pg-api.md)
2. Use[ **Txn Status Update API**](api-specification/payment/version-2/txn-status-update-api.md) to update the txn status in case of failures like user abort&#x20;
