# Registration

* First app will check if the user is registered or not by calling[ check registration api](check-registration-api.md)
* App will call [generate otp](../../common-apis/otp-and-token/generate-otp-api.md) to trigger otp to the user entered mobile number. Once user entered the mobile number, otp will be validated by calling [validate otp api](../../common-apis/otp-and-token/validate-otp-api.md)
* Once validation successfully completed, app will save login device details by calling [save device details api](save-device-details-api.md)
* After saving device details, app will save user entered credential details (pin or device) by calling [save credential api](save-credentials-api.md)

