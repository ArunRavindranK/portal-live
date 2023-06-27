# Registration

* First app will check if the user is registered or not by calling check registration api
* App will call [generate otp](https://app.gitbook.com/o/p6zvZh1r7XYNx0PmyEsS/s/CwdILEPBOX4lLKCKMZGB/\~/changes/234/bankezy/bankezy/bankezy-features/wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/common-apis/otp-and-token/generate-otp-api) to trigger otp to the user entered mobile number. Once user entered the mobile number, otp will be validated by calling [validate otp api](https://app.gitbook.com/o/p6zvZh1r7XYNx0PmyEsS/s/CwdILEPBOX4lLKCKMZGB/\~/changes/234/bankezy/bankezy/bankezy-features/wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/common-apis/otp-and-token/validate-otp-api)
* Once validation successfully completed, app will save login device details by calling save device details api
* After saving device details, app will save user entered credential details (pin or device) by calling [save credential api](https://app.gitbook.com/o/p6zvZh1r7XYNx0PmyEsS/s/CwdILEPBOX4lLKCKMZGB/\~/changes/234/bankezy/bankezy/bankezy-features/wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/registration/save-credentials-api)

