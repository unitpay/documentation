# Current Balance



To interact with the API, we recommend using the [Unitpay PHP-SDK](https://github.com/unitpay/php-sdk) library

![](../.gitbook/assets/image%20%2868%29.png)

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **login** | line | Partner's email in the UnitPay system |
| **secretKey** | line | Partner's secret key, available in the [profile settings](https://unitpay.money/partner/profile/edit) |

**Successful response**

![](../.gitbook/assets/image%20%2831%29.png)

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **balance** | number | Partner's balance in rubles |
| **email** | email | Partner's email in the UnitPay system |

**Error response**

![](../.gitbook/assets/image%20%2819%29.png)

|  | **Description** |
| :--- | :--- |
| **-32000** | Authorization error |
| **-32602** | Invalid request parameters |
| **-32603** | Internal technical error |

