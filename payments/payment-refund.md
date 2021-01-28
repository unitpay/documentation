# Payment Refund

To interact with the API, use the [Unitpay PHP-SDK](https://github.com/unitpay/php-sdk) library.

To make a refund, run a GET request:

![](../.gitbook/assets/image%20%286%29.png)

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **paymentId** | number | Payment ID in the UnitPay system |
| **secretKey** | line | Project secret key |
| **sum** | number | The refund amount, if the payment system does not support a full refund \(Optional parameter\). If the parameter is not transmitted, a full refund will be made |

**IMPORTANT NOTE:** In case of a partial refund of the original amount, there is no protection against duplication for repeated refunds! The only check that is implemented for a partial refund is that you cannot return the same amount within half an hour for the same transaction: an error message will appear.

You can run the query in test mode. [Learn more](../other/test-api.md)

**Successful response**

![](../.gitbook/assets/image%20%2865%29.png)

| Платеж успешно подтвержден | Payment successfully confirmed |
| :--- | :--- |


|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **message** | line | The comment of a successful transaction can be used as a hint to the user after completing the request |

**Error response**

![](../.gitbook/assets/image%20%2860%29.png)

| Неверный секретный ключ | Invalid secret key |
| :--- | :--- |


|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **message** | line | Information with a description of the request error |

