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
{"result": {
    "balance": "14434.33",  
    "email": "partner@gmail.com"
}}
```

|  | Значение | Описание |
| :--- | :--- | :--- |
| **balance** | число | Баланс партнера в рублях |
| **email**  | email | Email партнера в системе UnitPay |

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

