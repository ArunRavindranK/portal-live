# Payment

This section describes the different modes of payment supported in the system like adding funds to wallet, QR transactions, Recharge and bill payments etc

The below sequence diagram represents the two kinds of integration supported in the system.

1. Payments via API's where we connect with internal components to process the transaction.
2. Payments via SDK or redirect where we connect with external Payment Aggregator to process the transaction.

<figure><img src="../../../../.gitbook/assets/BankEzy Payment Flows-New - Payment Initiation (2).png" alt=""><figcaption></figcaption></figure>

## QR transaction:

1. Initiate [**Payment Params API**](api-specification/payment/version-2/payment-param-api.md) to get the required the configured payment route and to fetch merchant info needed for SDK approach.
2. Use [**QR Init API**](api-specification/qr-payment/version-1/qr-init-api.md) to initiate the transaction.
3. Refer the Payment - API Based, Payment - SDK Based and Payment - Redirect sections for the transaction flow based on the pgImplementation mode.
4. Use [**QR Auth Update API**](api-specification/qr-payment/version-1/qr-auth-api.md) to update the status of QR transaction.&#x20;
5. [**QR Init Auth API**](api-specification/qr-payment/version-1/qr-init-auth-api.md) is used to initiate a txn with a last used card.

## Non QR transaction:

1. Use[ **Load Money Init API**](../wallet/wallet-transactions/api-specification/version-2/load-unload-wallet/api-specification/load-money-initiation-api.md) to initiate load funds to wallet and [**Recharge Validate Init API**](../bill-payments/api-specification/validation-init-api.md) to initiate recharge/bill payments.
2. Initiate [**Payment Txn Init API**](api-specification/payment/version-2/payment-initiation-api.md) to get the required the configured payment route and to fetch merchant info needed for SDK approach.
3. Refer the Payment - API Based, Payment - SDK Based and Payment - Redirect sections for the transaction flow based on the pgImplementation mode.
4. Use [**Load Auth Update API**](../wallet/wallet-transactions/api-specification/version-2/load-unload-wallet/api-specification/authentication-status-update-api.md) to update the status of load funds to wallet, [**Recharge Auth Update API**](../bill-payments/api-specification/recharge-request-api.md) to update the status of recharge/bill payments.
