# Создание подписки

Механизм подписок позволяет автоматически списывать деньги с карты без участия клиента.

Данный метод полезен везде, где необходимо проведение периодических платежей \(списание арендной платы, пополнение телефона, оплата за доступ в интернет и др.\).

Создание подписки состоит из трех шагов:

1. Активации данной функции с вашим курирующим менеджером
2. Создание установочного платежа с передачей доп. параметра **params\[subscription\]=true**
3. Получение идентификатора подписки **subscriptionId** на [обработчике платежа](../payment-handler.md) вашего проекта.

После успешного создания подписки вы можете провести списание средств с карты клиента \(подписка должна иметь статус active\), используя стандартный механизм [создания платежа через API](../create-payment.md), передавая ИД подписки в параметр **params\[subscriptionId\]=XXX**. Сумма и периодичность списания определяется на стороне партнера.
