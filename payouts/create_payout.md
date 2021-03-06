# Создание выплаты

Через API возможно настроить только массовые выплаты.  
  
Для взаимодействия с API используйте библиотеку [Unitpay PHP-SDK](https://github.com/unitpay/php-sdk)

https://unitpay.money/api?  
     method=massPayment  
     params\[sum\]=10.00  
     params\[purse\]=7951xxxxx71  
     params\[login\]=partner@gmail.com  
     params\[transactionId\]=1782  
     params\[secretKey\]=ключ  
     params\[paymentType\]=qiwi

**Обязательные параметры:**

|  | Значение | Описание |
| :--- | :--- | :--- |
| **login**  | строка | Email партнера в системе UnitPay |
| **secretKey** | строка | Секретный ключ партнера, доступен в настройках профиля |
| **purse** | строка | Кошелек получателя в формате, принятом в платежной системе |
| **transactionId** | текст | Уникальный ID выплаты на стороне партнера |
| **sum** | число | Сумма перевода в рублях, например: "10.22"  |
| **paymentType** | строка | [Код платежной системы](../book-of-reference/payment-system-codes.md): Поддерживаются:  qiwi, card, mc, yandex |

**Дополнительные параметры:**

|  | Значение | Описание |
| :--- | :--- | :--- |
| **projectId**  | число | Уникальный ID проекта в системе UnitPay  |
| **comment** | текст | Комментарий к выплате. Отображается только в вашем личном кабинете \(разрешены только буквы, цифры, точки и запятые\) |

{% hint style="danger" %}
Если после создания выплаты вам требуется проверить ее статус, то необходимо использовать запрос "[Информация о выплате](https://help.unitpay.money/payouts/payout_info)"
{% endhint %}

**ВАЖНО:** всегда используйте уникальный **transactionId** для новых выплат, при получении существующего **transactionId** \(вне зависимости от других параметров\) возвращается текущий статус выплаты. Запрос можно выполнить в тестовом режиме. [Узнать подробнее](https://help.unitpay.money/other/test-api#vyplaty)

#### Успешный ответ

```text
{"result": {
    "message": "Выплата успешно проведена",
    "status": "success",
    "payoutId": "114233",
    "partnerBalance": "15733.00",
    "createDate": "2016-10-01 11:51:02",
    "completeDate": "2016-10-01 11:52:02",
    "sum": "300",
    "payoutCommission": "6.00",
    "partnerCommission": "0.00"
}}
```

|  | Значение | Описание |
| :--- | :--- | :--- |
| **message** | строка | Комментарий успешной операции можно использовать как подсказку пользователю после выполнения запроса |
| **status** | строка | success — успешная выплата not\_completed — выплата отправлена в платежную систему, но еще не получено подтверждение \(временный статус\)  |
| **payoutId** | число | Уникальный ID выплаты в системе UnitPay |
| **partnerBalance** | число | Баланс партнера в системе доступный для выплат |
| **createDate** | текст | Дата создания выплаты |
| **completeDate** | текст | Дата завершения выплаты |
| **sum** | число | Сумма выплаты |
| **payoutCommission** | число | Комиссия выплаты |
| **partnerCommission** | число | Комиссия партнера |

#### Ошибочный ответ

```text
{"error": {
    "message": "Номер телефона не входит в список доступных для выплат стран.",
    "code": 104
}}
```

|  | Значение | Описание |
| :--- | :--- | :--- |
| **message** | строка | Информация с описанием ошибки запроса |
| **code** | строка | Код ошибки, подробная расшифровка в таблице ниже |

**Ошибки:**

|  | Описание |
| :--- | :--- |
| **100** | Услуга "масспеймент" отключена |
| **101** | Услуга "масспеймент" для вас недоступна |
| **102** | Минимальная сумма единовременного платежа должна быть более 1 рубля |
| **103** | Сумма выплаты должна быть меньше или равна текущему балансу |
| **104** | Номер телефона не входит в список доступных для выплат стран |
| **1051** | Мы не смогли получить информацию о кошельке получателя средств. Проверьте номер кошелька и попробуйте повторить операцию снова или через некоторое время |
| **1052** | Мы не смогли получить информацию о номере карты. Проверьте номер карты и попробуйте повторить операцию снова или через некоторое время |
| **1053** | Мы не смогли получить информацию о номере телефона. Проверьте номер телефона и попробуйте повторить операцию снова или через некоторое время |
| **201** | Мы не смогли перевести средства на указанный вами счет  Это может быть связано с ограничениями счета получателя средств или ошибками на платформе платежной системы. |

**Технические ошибки:**

|  | Описание |
| :--- | :--- |
| **-32000** | Ошибка авторизации |
| **-32602** | Ошибочные параметры запроса |
| **-32603** | Внутренняя техническая ошибка |

