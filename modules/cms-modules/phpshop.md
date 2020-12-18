# PHPShop

**The Module Setup and Installation Instruction**

1. Download the [archive](https://github.com/unitpay/phpshop-module/archive/master.zip) with the module.
2. Unpack the contents of the archive to the root of the site.
3. Add the following lines in phpshop/inc/config.php file:

```text
[unitpay]​domain = "unitpay.money";​ public_key = "<Ваш публичный ключ из личного кабинета unitpay>";​secret_key = "<Ваш секретный ключ из личного кабинета unitpay>";
```

4. In the admin panel, go to Orders -&gt; Payment Methods and add Unitpay payment method. Check that the "Show" checkbox is checked.

![](../../.gitbook/assets/php1%20%281%29.png)

5. In your unitpay.money account, enter the address of the payment handler [http://&lt;your](http://%3Cyour/) site address&gt;/payment/unitpay/result.php

![](https://gblobscdn.gitbook.com/assets%2Fdokumentacziya%2F-M9xezG_6tZ_3GRmvyig%2F-M9y2jxfzUkZVJDZikXI%2F1.png?alt=media)

