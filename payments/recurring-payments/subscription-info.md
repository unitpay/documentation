# Getting a List of Active Subscriptions

#### 

You can run the query in test mode. [Learn more](../../other/test-api.md)

**Required parameters:**

\*\*\*\*

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **projectId** | number | Your project ID in the UnitPay system |
| **secretKey** | line | Secret key, available in the project settings |

**Successful response**

![](../../.gitbook/assets/image%20%2841%29.png)

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **subscriptionId** | number | Subscription ID in the UnitPay system |
| **description** | line | Text description of the subscription |
| **status** | line | Subscription status:   new — subscription created, no attempts of debiting under the subscription have occurred yet   active — subscription is active   close — subscription is closed |
| **startDate** | line | Subscription creation date in the YYYY-mm-dd HH:ii:ss format \(for example, 2012-10-01 12:32:00\) |
| **successPayments** | number | Number of successful payments under the subscription |
| **failPayments** | number | Number of failed attempts of debiting under the subscription |
| **lastPaymentId** | number | ID of the last payment under the subscription |
| **lastUpdateDate** | line | Date of the last payment under the subscription in the dd.mm.YYYY HH:ii:ss format \(for example, 15.09.2017 19:30:00\) |
| **parentPaymentId** | number | ID of the parent payment that initiated the subscription |
| **totalSum** | number | The total amount debited from the payer under the subscription |
| **closeType** | line | Reason for closing the subscription \(transmitted only if status=close\):   api — subscription was closed by the API partner   error — subscription was closed due to reaching the limit on the number of errors when trying to debit the funds   abuse — subscription was closed due to the subscriber's complaint |

**Error response**

![](../../.gitbook/assets/image%20%2839%29.png)

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **message** | line | Information with a description of the error |

