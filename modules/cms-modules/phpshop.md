# PHPShop

### Инструкция по настройке и установке модуля. <a id="instrukciya-po-nastroike-i-ustanovke-modulya"></a>

1. Скачайте [архив](https://github.com/unitpay/phpshop-module/archive/master.zip) с модулем.

2. Распакуйте содержимое архива в корень сайта.

3. В файле phpshop/inc/config.php добавьте следующие строчки:

```text
[unitpay]​domain = "unitpay.money";​ public_key = "<Ваш публичный ключ из личного кабинета unitpay>";​secret_key = "<Ваш секретный ключ из личного кабинета unitpay>";
```

4. В админпанели перейти в "Заказы"-&gt; "Способы оплаты" и добавить способ оплаты "Unitpay". Проверьте, чтобы стояла галка "Показывать".

![](../../.gitbook/assets/php1.png)

5. В личном кабинете unitpay.money введите адрес обработчика платежей [http://](http:)​[&lt;адрес](http://xn--/%3C-8cdug0fj/) вашего сайта&gt;/payment/unitpay/result.php

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/58cc04892c7d3a79f5f8d4f5/file-8ygNqAPAqM.png)

