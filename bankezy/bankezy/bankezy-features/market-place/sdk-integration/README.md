---
coverY: 0
---

# SDK Integration

## Start Initialisation of BankEzy-SDK:&#x20;

This step is used initialise the BankEzy-SDK in any third-party application&#x20;

1. Client app calls the method exposed by BankEzy-SDK based on platform specific integration.
2. In response/callback a Public-Key key will be issued to client application. &#x20;
3. Client application will send the Public-Key to the Client server. &#x20;
4. Client server will send the Public-Key and user profile details BankEzy Gateway Server by passing client credentials (stored in client server only not in app) in header. The payload should be encrypted. Please refer API authentication section for more details.
5. BankEzy Gateway will validate header data passed by client server and further forward request to BankEzy Token server and in inline <mark style="color:red;">request</mark> will be passed to client application&#x20;

## Complete Initialisation of BankEzy-SDK:&#x20;

1. Client app should call the method exposed by BankEzy-SDK based on platform specific integration with the token, token expiry date and Public-key received from client server .&#x20;
2. BankEzy-SDK will start communication with the BankEzy Server gateway with token passed from client application.&#x20;
3. BankEzy gateway server will further forward the requests to token/internal services.
