# MODX \(miniShop2\)

### Инструкция по настройке и установке модуля.

1. Скачайте [архив с модулем.](https://github.com/unitpay/modx/archive/main.zip)

2. Скопируйте содержимое директории unitpay из архива в корень вашего сайта.

3. Запустите скрипт ВАШ ДОМЕН/unitpay\_setup.php

4. Перейдите в Пакеты -&gt; Minishop 2 -&gt; Настройки -&gt; Способы оплаты. Убедитесь что модуль UnitPay присутствует в списке и включен, если нет то добавьте

![](../../.gitbook/assets/image_2020-12-14_17-33-55.png)

5. Перейдите в "Системные настройки & События" в панеле управления MODX. 

![](../../.gitbook/assets/nastroiki.png)

Отфильтруйте по типу настроек - "minisho2" и типу "Платежи". Установите UnitPay Domain \(**unitpay.money**\), UnitPay Public Key, UnitPay Secret Key \(их можно взять в настройках проекта в личном кабинете Unitpay\)

![](../../.gitbook/assets/b3de862d-5262-47f1-b0a9-3a2b4cbbe663.png)

Тут же задаются настройки НДС \(none, vat0, vat10, vat20\) и валюта.

6. Доставка задается в Пакеты -&gt; miniShop2 -&gt; Настройки Варианты доставки

![](../../.gitbook/assets/dostavka.png)

7. В личном кабинете Unitpay введите адрес обработчика платежей http://&lt;адрес вашего сайта&gt;//assets/components/minishop2/payment/unitpay.php

![](../../.gitbook/assets/503ada5aa8cf420011bef9717e36cc70.png)

