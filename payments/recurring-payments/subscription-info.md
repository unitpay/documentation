# Получение информации о подписке

{% api-method method="get" host="https://unitpay.money/api" path="?method=getSubscription&params\[subscriptionId\]=1&params\[secretKey\]=ключ" %}
{% api-method-summary %}
Получение информации о подписке
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="subscriptionId" type="number" required=true %}
ID подписки в системе UnitPay
{% endapi-method-parameter %}

{% api-method-parameter name="secretKey" type="string" required=true %}
Секретный ключ, доступен в настройках проекта
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

{% tabs %}
{% tab title="Успешный ответ" %}
```
{
   "result": {
      "subscriptionId": 123456,
      "description": "Описание подписки",
      "status": "active",
      "startDate": "2017-09-01 09:00:00",
      "successPayments": 4,
      "failPayments": 0,
      "lastPaymentId": 12345678911,
      "lastDateUpdate": "2017-09-15 19:30:00",
      "parentPaymentId": 12345678910,
      "totalSum": 50
   }
}
```
{% endtab %}

{% tab title="Ошибочный ответ" %}
```
{
   "error": {
      "message": "Описание ошибки"
   }
}
```
{% endtab %}
{% endtabs %}
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### Успешный ответ

```text
{
   "result": {
      "subscriptionId": 123456,
      "description": "Описание подписки",
      "status": "active",
      "startDate": "2017-09-01 09:00:00",
      "successPayments": 4,
      "failPayments": 0,
      "lastPaymentId": 12345678911,
      "lastDateUpdate": "2017-09-15 19:30:00",
      "parentPaymentId": 12345678910,
      "totalSum": 50
   }
}
```

|  | Значение | Описание |
| :--- | :--- | :--- |
| **subscriptionId** | число | ID подписки в системе Unitpay |
| **description** | строка | Текстовое описание подписки |
| **status**  | строка | Статус подписки:  new — подписка создана, попыток списания по подписке еще не происходило active — подписка активна close — подписка закрыта  |
| **startDate**  | строка | Дата создания подписки в формате YYYY-mm-dd HH:ii:ss \(например 2012-10-01 12:32:00\) |
| **successPayments** | число | Количество успешных платежей по подписке |
| **failPayments** | число | Количество не успешных попыток списания по подписке |
| **lastPaymentId** | число | ID последнего платежа по подписке |
| **lastUpdateDate** | строка | Дата последнего платежа по подписке в формате YYYY-mm-dd HH:ii:ss \(например 2012-10-01 12:32:00\) |
| **parentPaymentId** | число | ID родительского платежа, который инициировал подписку |
| **totalSum** | число | Общая сумма, списанная с плательщика по подписке |
| **closeType** | строка | Причина закрытия подписки \(передается только в случае status=close\):  api — подписка закрыта партнером по API error — подписка закрыта в связи с достижением лимита на количество ошибок при попытке списания средств abuse — подписка закрыта в связи с жалобой абонента |

#### Ошибочный ответ

```text
{
   "error": {
      "message": "Описание ошибки"
   }
}
```

|  | Значение | Описание |
| :--- | :--- | :--- |
| **message** | строка | Информация с описанием ошибки |

{% hint style="warning" %}
Запрос можно выполнить в тестовом режиме. [Узнать подробнее](../../other/test-api.md).
{% endhint %}

