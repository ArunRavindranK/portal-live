# API Specification

## To Start Initialisation of BankEzy-SDK:

This is step is used initialise the BankEzy-SDK in third-party application

1. Client app calls the start-init intent/method exposed by BankEzy-SDK
2. In response/callback a Public-Key key will be issued to client application.
3. Client application will send the Public-Key to the Client server.
4. Client server will send the Public-Key and user profile details BankEzy Gateway Server by passing client credentials (stored in client server only not in app) in header. The payload should be encrypted. Please refer API authentication section for more details.
5. BankEzy Gateway will validate header data passed by client server and further forward request to BankEzy Token server and in inline <mark style="color:red;">request</mark> will be passed to client application

## Complete Initialisation of BankEzy-SDK:

1. Client app should call complete-init intent/method exposed by BankEzy-SDK with the token, token expiry date and Public-key received from client server .
2. BankEzy-SDK will start communication with the BankEzy Server gateway with token passed from client application.
3. BankEzy gateway server will further forward the requests to token/internal services.
