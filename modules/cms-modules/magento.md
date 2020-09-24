# Magento

### Инструкция по настройке и установке модуля.

1. Скачайте   [архив](https://github.com/unitpay/magento-module) с модулем.

2. Скопируйте содержимое директории unitpay из архива в корень вашего сайта.

3. Отключите кеширование, для этого перейдите в меню System -&gt; Cache management, кликните на Select all и в выпадающем списке справа выберите Actions Disable и нажмите Submit

.![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/57a211f490336040e83796a8/file-pX5wIKG4z1.png)

4. Теперь перейдите в меню System-&gt;Configuration и в меню слева выберите Payment Methods. Среди методов оплаты вы увидите графу Unitpay. Щелкните на нее и в открывшихся параметрах введите DOMAIN \(unitpay.money\), PUBLIC KEY и  SECRET KEY, которые вы можете взять в личном кабинете на сайте Untipay.ru. После ввода нажмите  Save Config.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5e68ef1704286364bc968b03/file-ejVLWAJnED.png)

5. Теперь вы снова можете включить кеширование.

6. Введите в личном кабинете Unitpay.ru обработчик платежей по шаблону [http://&lt;имя\_вашего\_сайта&gt;/index.php/unitpay/index/callback](http://xn--%3C__-7vebaolv6au8a9a1ct4h3f/)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/57a21630c697916efaadfc1b/file-oo4XvLeN3M.png)

7. Модуль тестировался на Magento версии 1.9.2.4

