# Wallet Management

This section covers the APIs for the wallet management features like blocking/unblocking wallet, Fetch & Update user profile, Link Debit/Credit Cards, Beneficiary management for wallet to account transfers and to set recurring payments to load wallet, if the wallet balance falls below the threshold.

<figure><img src="../../../../.gitbook/assets/Wallet%20management%20(2).png" alt=""><figcaption></figcaption></figure>

## Card Management:

1. Call [**Payment Params API**](../payment/api-specification/payment/version-2/payment-param-api.md) to get the configured route for card management
2. If the pgImplementation mode is SDK, refer [**Generate Hash API**](../payment/api-specification/payment/version-2/hash-init-api.md) to fetch, add and delete cards
3. Call [**Consent API**](../payment/api-specification/payment/version-1/consent-api.md) in order to tokenise cards
4. Refer [**Card Link API**](wallet-management/api-specification/version-2/card-management/wallet-link/api-specification/link-card-api.md) to link a debit/credit card
5. To fetch the payment instrument linked to the user account, refer [**Fetch Accounts API**](wallet-management/api-specification/version-2/card-management/wallet-link/api-specification/fetch-linkedcards-api.md)
6. To update the Nick name of the card linked, refer [**Update Card Name API**](wallet-management/api-specification/version-2/card-management/wallet-link/api-specification/update-nickname-api.md)
7. To unlink the cards, use [**Unlink Card API**](wallet-management/api-specification/version-2/card-management/wallet-link/api-specification/unlink-card-api.md)

## Beneficiary Management:

To enable bank transfers from wallet, below API provides support to manage beneficiaries.

1. To add a new beneficiary, refer [**Add Beneficiary API**](wallet-management/api-specification/version-2/beneficiary-management/api-specification/add-beneficiary-api.md)
2. To fetch the list of beneficiaries, use [**Fetch Beneficiaries API**](wallet-management/api-specification/version-2/beneficiary-management/api-specification/fetch-beneficiary-account-api.md)

## Auto top-up Management:

The below API's helps to manage subscription to auto top up wallet if the wallet balance falls below the user defined threshold. A penny drop transaction is done to authenticate the user enabling for consuming this service.

1. Refer [**Top-up Subscription Init API**](wallet-management/api-specification/version-2/auto-top-up-management/api-specification/subscription-init-api.md) to initiate the subscription.
2. To confirm the subscription, use [**Top-up Subscription Confirm API**](wallet-management/api-specification/version-2/auto-top-up-management/api-specification/subscription-confirm-api.md). This api to be called after authenticating the penny drop transaction.
3. Status of the subscription can be fetched by using Fetch [**Top-up Subscription Status API**](wallet-management/api-specification/version-2/auto-top-up-management/api-specification/status-api.md)
4. Subscription can be modified using [**Modify Top-up Subscription API**](wallet-management/api-specification/version-2/auto-top-up-management/api-specification/modify-top-up-subscription-api.md)

## Wallet Management:

The below section defines the API's to block/unblock the user's own wallet and to block/unblock other user's to initiate collect request.

1. To block wallet initiated by the user, refer [**Wallet Block API**](wallet-management/api-specification/version-2/wallet-management/api-specification/wallet-card-block.md)
2. To unblock wallet initiated by the user, refer [**Wallet UnBlock API**](wallet-management-new/api-specification/version-2/block-unblock-wallet/api-specification/unblock-mobile-number-api.md)
3. User wants to restrict collect request being received from a particular user, refer [**Block Collect Request API**](wallet-management-new/api-specification/version-2/block-unblock-wallet/api-specification/blocked-mobile-number-list-api.md)
4. To unblock a particular user in order to receive collect request, refer [**UnBlock Collect Request API**](wallet-management/api-specification/version-2/wallet-management/api-specification/unblock-mobile-number-api.md)
5. To view the list of blocked users, refer [**Blocked User List API**](wallet-management/api-specification/version-2/wallet-management/api-specification/blocked-mobile-number-list-api.md)

*
