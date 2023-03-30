# UPI

BankEzy platform supports issuer UPI features. Following are the features supported

1. UPI Registration
2. Device binding
3. UPI payments
   1. Send Money
   2. Receive money
4. Push notifications
5. Dispute management

Below diagram explain the UPI registration flow

<figure><img src="../../../../../.gitbook/assets/UPI PPI - UPI Registration.png" alt=""><figcaption><p>UPI Registration Flow</p></figcaption></figure>

1. The registration status of the user shall be verified by [UPI Registration Status Inquiry API](catch-all-no-need-to-publish/block-unblock-wallet/upi-registration-status-inquiry-api.md).
2. Non registered user will be prompted for UPI registration. The SMS token for UPI registration will be received from backend using [UPI Registration SMS Token API](api-reference/upi-registration/upi-registration-sms-token-api.md)
3. App to send the SMS token to specific number.
4. Post sending the SMS, App will initiate the [Device Binding API](catch-all-no-need-to-publish/device-binding-api.md)
5. The status of the device binding can be verified using UPI Registration Polling API

Below diagram explains the UPI transaction flow

<figure><img src="../../../../../.gitbook/assets/UPI PPI - UPI Transaction.png" alt=""><figcaption><p>UPI Transaction Flow</p></figcaption></figure>

1. The VPA of the user can be verified using [Verify VPA API](catch-all-no-need-to-publish/wallet-closure/verify-vpa-api.md)
2. User will be able to send and receive money using [Send Money API](../wallet-transactions/request-money/api-specification/send-money-via-upi-api.md)
   1. If Send Money via SCAN\_PAY then we will validate that scan url using [Validate scan pay url API](../wallet-transactions/request-money/api-specification/validate-scan-pay-url-api.md)
3. User will be able to request money via UPI using [Request Money API](../wallet-transactions/request-money/api-specification/request-money-via-upi-api.md)
4. User can check list of collect requests using [List Pending Collect Requests API](../wallet-transactions/request-money/api-specification/list-pending-collect-requests-api.md)

Following are the few other UPI management related APIs supported

1. Add a new VPA using [Add VPA API](../wallet-transactions/wallet-to-account/add-vpa-api.md)
2. Deregister VPA using [Deregister VPA API](../wallet-transactions/wallet-to-account/api-specification/deregister-vpa-api.md)
3. Delete VPA using [Delete VPA API](../wallet-transactions/wallet-to-account/api-specification/delete-vpa-api.md)
4. Blocking VPA using [Block VPA API](../wallet-transactions/wallet-to-account/api-specification/block-vpa-api.md)
5. Unblocking VPA using [Unblock VAP API](../wallet-transactions/split-bill/unblock-vpa-api.md)
6. To view the list for blocked VPA using [Blocked VPA list API](../wallet-transactions/split-bill/api-specification/blocked-vpa-list-api.md)

Following are the features related to dispute management

1. Raise a complaint
2. Check the status of the raised complaint





