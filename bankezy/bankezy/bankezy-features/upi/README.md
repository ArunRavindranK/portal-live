# UPI

BankEzy platform supports issuer UPI features. Following are the features supported

1. UPI Registration
2. UPI payments
   1. Send Money
   2. Receive money
   3. QR transaction
   4. Intent support
3. Push notifications
4. Dispute management
5. UPI Account Management

Below diagram explain the UPI registration flow

<figure><img src="../../../../.gitbook/assets/UPI PPI - UPI Registration (1).png" alt=""><figcaption></figcaption></figure>

1. The registration status of the user shall be verified by [**UPI Registration Status Inquiry API**](registration/version-2/upi-registration-status-inquiry-api.md).
2. Non registered user will be prompted for UPI registration. The SMS token for UPI registration will be received from backend using [**UPI Registration SMS Token API**](registration/version-2/upi-registration-sms-token-api.md)
3. App to send the SMS token to specific number.
4. Post sending the SMS, App will initiate the [**Device Binding API**](registration/version-2/device-binding-api.md)
5. The status of the device binding can be verified using [**UPI Registration Polling API**](registration/version-2/polling-api.md)
6. Incase to abort the registration process,  [**Decline Device Binding API** ](registration/version-2/decline-device-binding-api.md)can be used.

Below diagram explains the UPI transaction flow

<figure><img src="../../../../.gitbook/assets/UPI PPI - UPI Transaction (3).png" alt=""><figcaption></figcaption></figure>

1. The VPA of the user can be verified using [**Verify VPA API**](payments/version-2/verify-vpa-api.md)
2. User will be able to send and receive money using [**Send Money API**](../wallet/wallet-transactions/api-specification/version-2/wallet-to-account/api-specification/send-money-api.md)
   1. If Send Money via SCAN\_PAY then we will validate that scan url using [**Validate scan pay url API**](payments/version-2/validate-scan-pay-url-api.md) in case of signed QR
3. User will be able to request money via UPI using [**Request Money API**](../wallet/wallet-transactions/api-specification/version-2/request-money/version-2/request-money-process-api.md)
4. User can check list of collect requests using [**List Pending Collect Requests API**](../wallet/wallet-transactions/api-specification/version-2/request-money/version-2/request-money-fetch-api.md)
5. Payer can approve, decline or block the received Collect request using [**Request Money Accept/Decline API**.](../wallet/wallet-transactions/api-specification/version-2/request-money/version-2/request-money-accept-initiate-api.md)

Following are the few other UPI management related APIs supported.

1. Add a new VPA using [**Add VPA API**](account-management/version-2/add-vpa-api.md)
2. Deregister VPA using [**Deregister VPA API**](account-management/version-2/deregister-vpa-api.md)
3. Delete VPA using [**Delete VPA API**](account-management/version-2/delete-vpa-api.md)
4. Blocking VPA using [**Request Money Accept/Decline API**](../wallet/wallet-transactions/api-specification/version-2/request-money/version-2/request-money-accept-initiate-api.md)
5. Unblocking VPA using [**Unblock VAP API**](account-management/version-2/unblock-vpa-api.md)
6. To view the list for blocked VPA using [**Blocked VPA list API**](account-management/version-2/blocked-vpa-list-api.md)

Following are the features related to dispute management

1. To get the pre defined set of reasons to raise compliant [**Get Dispute Reasons** ](dispute-management/api-specification/version-2/get-dispute-reasons.md)API to be used.
2. Raise a complaint using [**Register Compliant**](dispute-management/api-specification/version-2/register-complaint.md) API
3. To check the status of the raised complaint, [**Check Status**](dispute-management/api-specification/version-2/check-status.md) API to be used.
4. To view the list of disputes raised, [**Fetch**](dispute-management/api-specification/version-2/fetch-api.md) API can be used.





