# 3DSS Protocol 1.0

### **What is 3D Secure 1.0?**

3D Secure 1.0, cardholder authentication is more widely known as _Verified by Visa_, _Mastercard SecureCode_, or _American Express SafeKey_. It allows the merchant to verify the identity of the customer by redirecting them to their bank's authentication page to enter a secure passphrase, which could be in the form of a pin, password / sms code or use two-factor authentication. Under the right conditions, 3D Secure provides protection for the merchant in the event of a fraud related chargeback.

### Transaction Flow

![](<../../.gitbook/assets/1.0 (1).jpg>)

1\) 3DS Requestor initiates pVrq(2) versioning request with 3DS Server

2\) 3DS Server responds with pVrs(3) versioning response and provides the version supported by ACS and DS for the card BIN range. In this case, version is 1.0.2

3\) 3DS Requestor initiates pArq(4) with 3DS Server with the API request with message\_version as 1.0.2

4\) 3DS Server initiates Vereq(3DS 1.0) message with DS and receives Veres from ACS

5\) Once Veres is received with status = "Y", 3DS Server will create the Pareq, and respond to 3DS requestor with pArs(9), with encoded Pareq and ACS URL for Pareq redirection.

6\) 3DS Requestor to redirect customer browsing by posting the Pareq(11) received from 3DS Server to the ACS URL.

7\) ACS to perform 1.0 processing and provide Pares (12) by redirecting the browser back to 3DS Requestor.

8\) 3DS Requestor to make pRqFr (14) call to 3DS Server and pass the Pares received from ACS to 3DS Server.

9\) 3DS Server decodes Pares and extracts key fields like eci, cavv.

10\) 3DS server responds to 3DS Requestor with pRsFr with eci, cavv.

11\) 3DS requestor initiates authorisation call with acquirer.

### Potential Issues with 3DS 1.0 Flow

Being introduced in the payments market in 1999, the obvious issue is that the system was never designed with the proliferation of mobile devices in mind, which have become the prime means of online shopping for consumers. This is even though the protocol has been upgraded to combat the mobile issues with risk-based authentication and reconfigured customer pages.

Moreover, customers were not happy with the amount of friction the system caused for each time they needed to complete payment online. 3-D Secure is not optional, but automatic at the end of a transaction. Customers were required to enrol with static passwords, which some were not able to remember later, this added frustration simply forcing them to abandon the process. This is especially pronounced for mobile users who are redirected to a bank page that is typically not optimised for mobile. The alternative to the static password is an SMS text message, which can be even more frustrating. Shoppers who are abroad may not be able to receive the SMS message.
