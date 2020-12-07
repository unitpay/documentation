# Magento 2

### Инструкция по настройке и установке модуля. <a id="instrukciya-po-nastroike-i-ustanovke-modulya"></a>

1.Скачать [архив модуля](https://github.com/unitpay/magento2/archive/main.zip) и загрузить в корень сайта.  


2. В консоли из корня сайта запустить команду php bin/magento setup:upgrade для установки модуля  


3. php bin/magento setup:di:compile для компиляции конфигурационных файлов  


4. Заходим в админ панель. Stores -&gt; Configuration

![](../../.gitbook/assets/image2%20%281%29.png)

5. В левом меню выбираем Sales -&gt; Payment Methods

![](../../.gitbook/assets/image7%20%281%29.png)

6. Находим модуль unitpay и задаем настройки Domain \(**unitpay.money**\), Public Key, Secret Key \(можно взять в настройках проекта в личном кабинете Unitpay\)

![](../../.gitbook/assets/image6.png)

7. По умолчанию доставка действует на каждый товар \(3 товара = тройная стоимость доставки\). Чтобы это настроить идём в Stores -&gt; Configuration . Потом в раскрывающимся списке Sales ищем Shipping methods

![](../../.gitbook/assets/image4%20%281%29.png)

