# Using the Test API

**Introduction**

The API test mode allows you to learn how to work with the Unitpay API on test data without actually conducting transactions:

* data exchange;
* format of queries and responses;
* content of queries and responses.

To use the API in test mode, you must add the **params\[test\]=1** parameter to the query.

**The test data that need to be transmitted in queries:**

| **Parameter** | **Value** |
| :--- | :--- |
| **projectId** | 135 |
| **login** | test\_user |
| **secretKey** | Any line containing Latin characters and numbers |

_**IMPORTANT NOTE!**_ _After switching to operative mode, remember to change the test parameters to actual ones!_

For the API in test mode, you should send all the mandatory parameters which can be viewed on the main page of the used method.  
All the response parameters of the API in test mode correspond to the response in operative mode unless otherwise stated in the test API documentation.

| **Available methods for test mode** |
| :--- |
| Creating payment \(initPayment\) |
| Information about payment \(getPayment\) |
| Payment refund \(refundPayment\) |
| Creating a payout \(massPayment\) |
| Information about payout \(massPaymentStatus\) |
| Getting a list of active subscriptions \(listSubscriptions\) |
| Getting information about subscription \(getSubscription\) |
| Closing subscription \(closeSubscription\) |

**Payments**

**Creating a Payment**

**initPayment**  
Mandatory method parameters

**Test data:**

| **Parameter** | **Value** |
| :--- | :--- |
| **paymentType** | card  \(only card is supported in test mode\) |
| **account** | Any line containing Latin characters and numbers |
| **desc** | Any line containing characters and numbers |

Other parameters should be specified according to the documentation.

**Successful response. The difference of the values of the parameters in test mode:**

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **redirectUrl** | line | **Test** URL for redirecting the user to the payment platform gateway. If the payment does not require redirecting, this parameter will not be available. |
| **receiptUrl** | line | **Test** URL for redirecting the user to the payment receipt. |

_Warning_: the transmitted information will not be saved in test mode. Therefore, the payment information may differ from the values transmitted when creating the payment. The payment receipt number and paymentId will also change after payment using the payment details.

**Test forms**

The URL received when creating a payment **in test mode** is only needed for testing the payment, 3ds authorization, and receipt output. Do not share this link with users!

To test the payment, follow the link from redirectUrl. The link leads to a test form for entering card details. Enter your details and go through 3ds authorization to get the payment status. The money will not be debited using real details.

**Test details for payment by card:**

| **Value** | **Description** |
| :--- | :--- |
| 1234567465831234 | Successful payment |
| Any other value | Error payment |

After entering the card details, you will switch to the 3ds authorization **test** form.  
In the Code field, enter **391745** for a successful payment.

**Payment under subscription**

Payment under subscription is only available for payments by credit cards. To make a test payment under the subscription, add the **subscriptionId** parameter with the test value to the initPayment method.

**Test subscriptionId:**

| **Value** | **Description** |
| :--- | :--- |
| from 1 to 5 | Successful payment |
| Any other subscriptionId | Returns an error: Subscription not found |

**Information about Payment**

**getPayment**  
Mandatory method parameters

**Test paymentId for payments:**

| **Value** | **Description** |
| :--- | :--- |
| 100301 | Payment in process |
| 100303 | Successful payment |
| 100304 | Error payment |

Use **paymentId** from the test responses to get information about the payment.

**Important Note**: information about the test payment will not be saved. The data received in the response may differ from the data transmitted when creating the payment. The value of **purse** can be hidden in test mode.

**Payment Refund**

**refundPayment**  
Mandatory method parameters

**Test paymentId for refund:**

| **Value** | **Amount** | **Partial refund** |
| :--- | :--- | :--- |
| 12358132134 | 5000 | Supported |
| 383117770 | 1000 | Not supported |

Add an optional **params\[sum\]** to the request to get various refund events \(more or less than the allowed refund amount\).

**Payouts**

**Creating a Payout**

**massPayment**  
Mandatory method parameters

**Test parameters for payouts:**

| **Parameter** | **Value** |
| :--- | :--- |
| **login** | test\_user |
| **projectId** | 135 |
| **transactionId** | Any line containing Latin characters and numbers |
| **secretKey** | Any line containing Latin characters and numbers |
| **purse** | Any line containing Latin characters and numbers |

When creating a payout, you can get different statuses. To test them, use the **paymentType=card** parameter and the following **transactionId**:

| **Value** | **Status** |
| :--- | :--- |
| F12358132134 | success |
| F383117770 | error |
| Any other value | not\_completed |

**Warning**: the created payout will not be saved in test mode. Getting information about the completed test payment using massPaymentStatus will result in an error.

**Information about Payout**

**massPaymentStatus**  
Mandatory method parameters

In test mode, you can only get information about a payout from the list. You can view the test parameters in the table below.

**Test transactionId for getting information about payouts:**

| **Value** | **Status** |
| :--- | :--- |
| F12358132134 | success |
| F383117770 | error |
| Any other value | Error response |

**Subscriptions**

**Getting a List of Active Subscriptions**

**listSubscriptions**  
Mandatory method parameters

To get a list of test active subscriptions, use the **projectId** specified in the table _The test data that need to be transmitted in queries._

**Getting Information About Subscription**

**getSubscription**  
Mandatory method parameters

In test mode, you can only get information about your subscription by using the subscriptionids listed in the table below.

**Test subscriptionId:**

| **Value** | **Status** |
| :--- | :--- |
| 1, 2, 5 | active |
| 3 | close |
| 4 | new |

**Closing a Subscription**

**closeSubscription**  
Mandatory method parameters

In test mode, you can only close a subscription from the table below.

**Test subscriptionId of subscriptions:**

| **Value** | **Status** |
| :--- | :--- |
| 1, 2, 5 | active |
| 3 | close |
| 4 | new |

**Important Note**: the subscription closing status will not be saved.

