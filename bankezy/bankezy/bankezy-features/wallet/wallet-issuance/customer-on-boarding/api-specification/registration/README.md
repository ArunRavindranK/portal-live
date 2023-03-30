# Registration

* First app will check if the user is registered or not by calling[ check registration api](broken-reference)
* App will call [generate otp](broken-reference) to trigger otp to the user entered mobile number. Once user entered the mobile number, otp will be validated by calling [validate otp api](broken-reference)
* Once validation successfully completed, app will save login device details by calling [save device details api](broken-reference)
* After saving device details, app will save user entered credential details (pin or device) by calling [save credential api](broken-reference)
