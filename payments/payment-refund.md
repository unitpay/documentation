# Возврат платежа

{% api-method method="get" host="https://unitpay.money/api?method=refundPayment" path="" %}
{% api-method-summary %}
Возврат платежа
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="paymentMethod" type="string" required=false %}
**Признак способа расчета:** full\_prepayment - предоплата 100%   
prepayment - предоплата   
advance - аванс   
full\_payment - полный расчет
{% endapi-method-parameter %}

{% api-method-parameter name="sum" type="number" required=false %}
Cумма возврата, если платежная система поддерживает не полный возврат \(Не обязательный параметр\). Если параметр не передан, будет произведен полный возврат
{% endapi-method-parameter %}

{% api-method-parameter name="paymentId" type="number" required=true %}
ID платежа в системе UnitPay  
Например: 1234512345
{% endapi-method-parameter %}

{% api-method-parameter name="secretKey" type="string" required=true %}
Секретный ключ проекта, доступен в настройках проекта
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{ 
    "result": {
        "message": "Возврат успешно произведен",
}}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

**ВАЖНО:** При неполном возврате не на всю исходную сумму при повторных возвратах нет защиты от дублирования! Единственная проверка, которая реализована при частичном возврате - в течении получаса по одной и той же транзакции нельзя вернуть одну и ту же сумму, будет выдана ошибка.

#### Успешный ответ

|  | Тип | Описание |
| :--- | :--- | :--- |
| **message** | string | Комментарий успешной операции можно использовать как подсказку пользователю после выполнения запроса |

#### Ошибочный ответ

|  | Тип | Описание |
| :--- | :--- | :--- |
| **message** | string | Информация с описанием ошибки запроса |

{% hint style="info" %}
Вы можете воспользоваться готовой библиотекой [Unitpay PHP-SDK](https://github.com/unitpay/php-sdk) 
{% endhint %}

