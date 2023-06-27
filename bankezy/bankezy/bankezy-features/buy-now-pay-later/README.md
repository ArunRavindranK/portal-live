---
description: Lending
---

# Buy Now Pay Later

Buy Now, Pay Later (BNPL) is a type of short-term financing that allows consumers to make purchases and pay for them over time with no interest. BNPL arrangements, also called point-of-sale instalment loans, are an increasingly popular payment option, especially for online shopping.

Key features

* End-to-end support across the BNPL value chain
* Onboarding: KYC validations, Credit Bureau checks, Underwriting
* Credit line issuance: Rule based issuance of credit lines.
* Transaction life cycle: Settlements, Fees, Financial Risk Management, Merchant Authentication
* Post-credit line issuance: Repayments and collections through a dedicated app or SDK/API integration with the client app
* Lender management: Credit Line organisation & distribution with personalisation in \
  consumer credit limit and repayment notifications
* Merchant Management: Merchant risk checks, Merchant Onboarding, Reporting.

**BNPL Onboarding Flow**



<figure><img src="../../../../.gitbook/assets/bnplregistration - External Use.png" alt=""><figcaption></figcaption></figure>

&#x20;

BNPL Onboarding Steps

* User is prompted to enter the Mobile Number and mail ID to check the BNPL registration The registration status of the user shall be verified by[ Sign In API.](onboarding/sign-in.md)
* Non registered user is onboarded using BNPL Onboarding with OTP Authentication using [Generate OTP](onboarding/generate-otp.md) and [Verify OTP](onboarding/verify-otp.md).
* On OTP authentication, user onboarding is initiated using [Onboard user API](onboarding/onboard-user.md) with user consent for KYC (PAN, CKYC)&#x20;
* User provided PAN details are verified before onboarding the user.
* On successful PAN validation, user will be validated against CKYC database to get the benefit of Full KYC wallet benefits.
* IF CKYC information is not available for the user, [EKYC Process](../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/api-specification/non-bank-customer-kyc-process/ekyc-process/)  is initiated
* On Address confirmation with [Confirm CKYC API](onboarding/confirm-ckyc.md) ,User credit information is obtained from CIBIL&#x20;
* Loan limit for the user is calculated based on the Business Rules configured in the rule engine with CIBIL details and BNPL Limit set for user can be retrieved through [Get Limit API](onboarding/get-limit.md)



BNPL Transaction and Repayment

* Once the Limit is Set, User can do the BNPL transaction&#x20;
* If the user is availing for the benefits of loan with a merchant for the first time, additional authentication to be taken from the user. In order to identify if additional authentication of the user is needed for that specific merchant, **Init Loan API** can be used.
* Transaction is initiated with [Transaction/Loan](create-loan/transaction-loan.md) API
* Loan Reference ID and payment date is provided to the user.
* Bill details are fetched from the LMS, User can get the bill details using [Bill Fetch ](loan-repayment/bill-fetch.md)API
* Payment for un-billed/billed amount can be done using [Bill Payment Init ](loan-repayment/bill-payment-init.md)API
* Bill Payment status can be update through [Bill Payment ](loan-repayment/bill-payment.md)API&#x20;
* Refund can be initiated from[ Refund ](create-loan/refund.md)API
* Transaction History can be viewed using [Fetch Transaction](../wallet/wallet-transactions/api-specification/version-2/transaction-history/api-specification/fetch-transactions-api.md) API
