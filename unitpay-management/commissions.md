# Commissions

To interact with the API, we recommend using the [Unitpay PHP-SDK](https://github.com/unitpay/php-sdk) library

![](../.gitbook/assets/image%20%2861%29.png)

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **projectId** | number | Project ID in the system |
| **login** | line | Partner's email in the UnitPay system |
| **secretKey** | line | Partner's secret key, available in the [profile settings](https://unitpay.money/partner/profile/edit) |

**Successful response**

![](../.gitbook/assets/image%20%2866%29.png)

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **operator code** | text | Operator alphabetic code |
| **commission** | number | Full commission for effecting the payment |

**Error response**

![](../.gitbook/assets/image%20%2852%29.png)

|  | **Description** |
| :--- | :--- |
| **-32000** | Authorization error |
| **-32602** | Invalid request parameters |
| **-32603** | Internal technical error |

