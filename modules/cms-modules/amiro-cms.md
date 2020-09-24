# Amiro CMS

### Инструкция по настройке и установке модуля. <a id="instrukciya-po-nastroike-i-ustanovke-modulya"></a>

1. Скачайте [архив](https://github.com/unitpay/amiro-module/releases/download/v2.0.1/amiro-module-2.0.1.zip) с модулем.

2. Перейдите по ссылке [**http://ваш\_сайт/\_admin/engine.php?mod\_id=ami\_market&upload=1**](http://xn--_-7sbbf2b7bj7b/_admin/engine.php?mod_id=ami_market&upload=1)​

3. Выберите в качестве файла дистрибутива скачанный архив с модулем и загрузите его.

4. Перейдите в "Сервис"-&gt; "Настройка системы"-&gt; "Способы оплаты".

5. Найдите в списке драйверов Unitpay и нажмите "Установить".

6. Нажмите кнопку "Редактировать" в строке Unitpay и заполните поля DOMAIN \(unitpay.ru\), PUBLIC KEY и SECRET KEY, которые вы можете взять в личном кабинете unitpay.ru. Далее нажмите на кнопку сохранить.

7. Переходим в Сервис-&gt;Настройка системы и в выпадающем списке выбираем "Каталог товаров"-&gt; "Заказы".

​![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/589319b72c7d3a784630896a/file-gK9kaw5I6F.png)​

8. В строке "Доступные способы оплаты" нажимаем "Редактировать", выбираем необходимые способы, включая Unitpay и в самом низу жмем кнопку "Применить изменения".

9. В личном кабинете Unitpay.ru введите адрес обработчика платежей [http://&lt;адрес](http://xn--/%3C-8cdug0fj/) вашего сайта&gt;/drivers/gate\_unitpay.php. Из-за особенностей модуля будет гореть красным "Ошибка формата", это нормально.![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/58931dfd2c7d3a7846308987/file-yzfMRJS7QE.png)

