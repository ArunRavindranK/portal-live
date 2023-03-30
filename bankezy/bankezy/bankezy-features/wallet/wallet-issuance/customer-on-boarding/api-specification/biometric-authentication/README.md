# Biometric Authentication

Bankezy application supports biometric authentication while registration or after login.

When user is opted for biometric authentication, App will call [Public key Api](public-key-api.md) to generate RSA and AES keys for one user on one device. If user changes device then again app will call public key api to generate RSK key for the new device.

After generating keys, server will return public and AES key to the app, private key will be saved at server end.

App will encrypt the public key with AES key and store it the encrypted public key. key reference along with a flag for biometric authentication securely in the application.

When user try for login, app will do the encryption on device id by using this public key and send it with the request along with key reference. refer Login API.
