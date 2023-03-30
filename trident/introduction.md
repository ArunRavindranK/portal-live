# Introduction

**What is Trident?**

Trident, Wibmo’s fraud detection & FRM product, is an intelligent system that performs real-time fraud detection with/using/leveraging a powerful combination of a rules-based approach and advanced analytics.

It profiles each transaction based on identified patterns, historical data, customer profiles and transaction patterns. Combines a powerful rule-based engine (currently deployed in eGuard), advanced device fingerprinting technology, advanced analytics & machine learning to continuously learn and adapt based on data patterns. Trident evaluates each transaction to provide a risk score, which can enable better decision making.

![](<../.gitbook/assets/trident flow.png>)

Trident seamlessly integrates with systems such as ATM, POS, e-commerce, mobile banking, net banking etc. Total time taken to receive the risk score from trident by the requesting system is less than 2 seconds.

Once transaction is initiated, V-Req Api, is utilized to send information about the customer and the card details, once that is approved, P-Req Api is utilized to send the full details of transaction, eg: amount, place of transaction and etc. After which U-Req Api, is utilized to give update regarding the transaction completion, whether it was successful or not.
