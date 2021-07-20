# Current Balance



To interact with the API, we recommend using the [Unitpay PHP-SDK](https://github.com/unitpay/php-sdk) library:  
 `https://unitpay.money/api?   
     method=getPartner   
     params[login]=partner@gmail.com   
     params[secretKey]=ключ`

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **login** | line | Partner's email in the UnitPay system |
| **secretKey** | line | Partner's secret key, available in the [profile settings](https://unitpay.money/partner/profile/edit) |

**Successful response**

```text
{
    "result": {
        "email": "partner@gmail.com",
        "balance": "13.20",
        "balance_payout": "13.20",
        "unitwallet": {
            "rest_balance": "59986.80",
            "rest_payouts": "198151.00",
            "rest_ecommerce_payouts_today": "15000.00",
            "rest_ecommerce_payouts_month": "39919.00",
            "rest_card_payouts_today": 13,
            "rest_card_payouts_month": 267
        }
    }
}
```

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **email**  | email | Partner's email in the UnitPay system |
| **balance** | число | Partner's balance in rubles |
| **balance\_payout** | number | Partner's balance, available for withdrawal, in rubles |
| **unitwallet** |  | The field for UnitWallet wallet balances \(optional\) |
| **rest\_balance** | number | Available balance on the balance sheet in rubles \(will be actual since 15.06.2021\) |
| **rest\_payouts** | number | Available balance on withdrawn funds for a calendar month in rubles \(will be actual since 15.06.2021\) |
| **rest\_ecommerce\_payouts\_today** | number | Available for withdrawal until 23:59 \(MSK\) via Qiwi, Юmoney, WMP in rubles \(will be actual since 15.06.2021\) |
| **rest\_ecommerce\_payouts\_month** | number | Available for withdrawal in the current calendar month via Qiwi, Юmoney, WMP in rubles \(will be actual since 15.06.2021\) |
| **rest\_card\_payouts\_today** | number | Available number of withdrawals to bank cards until 23:59 \(MSK\) |
| **rest\_card\_payouts\_month** | number | Available number of withdrawals to bank cards in the current calendar month |

**Error response**

```text
{"error": {
    "message": "Неверный секретный ключ",
    "code": -32000
}}
```

|  | **Description** |
| :--- | :--- |
| **-32000** | Authorization error |
| **-32602** | Invalid request parameters |
| **-32603** | Internal technical error |

