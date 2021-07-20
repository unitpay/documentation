# Текущий баланс

Для взаимодействия с API рекомендуется использовать библиотеку [Unitpay PHP-SDK](https://github.com/unitpay/php-sdk)

     `https://unitpay.money/api?   
     method=getPartner   
     params[login]=partner@gmail.com   
     params[secretKey]=ключ`

|  | Значение | Описание |
| :--- | :--- | :--- |
| **login**  | строка | Email партнера в системе UnitPay |
| **secretKey** | строка | Секретный ключ партнера, доступен в [настройках профиля](https://unitpay.ru/partner/profile/edit) |

#### Успешный ответ

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

|  | Значение | Описание |
| :--- | :--- | :--- |
| **email**  | email | Email партнера в системе UnitPay |
| **balance** | число | Баланс партнера в рублях |
| **balance\_payout** | число | Баланс партнера, доступный для вывода, в рублях |
| **unitwallet** |  | Необязательное поле с обозначением блока для балансов кошельков UnitWallet |
| **rest\_balance** | число | Доступный остаток по балансу в рублях |
| **rest\_payouts** | число | Доступный остаток по выведенным средствам за календарный месяц в рублях |
| **rest\_ecommerce\_payouts\_today** | число | Доступный остаток по выведенным средствам  через Qiwi, Юmoney, WMP в рублях |
| **rest\_ecommerce\_payouts\_month** | число | Доступный остаток по выведенным средства в текущем календарном месяце через Qiwi, Юmoney, WMP в рублях |
| **rest\_card\_payouts\_today** | число | Доступное количество выплат на банковские карты до 23:59 текущего дня |
| **rest\_card\_payouts\_month** | число | Доступное количество выплат на банковские карты в текущем месяце |

#### Ошибочный ответ

```text
{"error": {
    "message": "Неверный секретный ключ",
    "code": -32000
}}
```

|  | Описание |
| :--- | :--- |
| **-32000** | Ошибка авторизации |
| **-32602** | Ошибочные параметры запроса |
| **-32603** | Внутренняя техническая ошибка |

