# Webasyst Shop Script 7

#### Инструкция по установке и настройке модуля. <a id="instrukciya-po-ustanovke-i-nastroike-modulya"></a>

1. Скачайте [архив](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MDxJKwoVaj758xWx_jc%2F-MINU72_WdVBhDlUivMf%2F-MINVAw2kYlw_z0D7Q89%2Fshopscript-module-2.2.0.zip?alt=media&token=1785a76e-4802-449c-8b74-fce9f3d0170f) с модулем \(.zip\).

2. Копируем папку unitpay в wa-plugins/payment _\(ещё wa-plugins/payment есть внутри wa-sources - это не та директория что нужна, не перепутайте\)._

![](../../.gitbook/assets/image4.png)

3. Переходим в панель управления магазином "**Настройки → Оплата → Добавить способ оплаты → Unitpay**"

![](../../.gitbook/assets/1321.png)

4. Поля DOMAIN \(unitpay.money\), PUBLIC KEY и SECRET KEY можно взять со страницы вашего проекта на unitpay. Проверьте, чтобы у модуля стояла галочка "**Включен**".

![](../../.gitbook/assets/image5.png)

![](../../.gitbook/assets/12312.png)

5. На странице проекта в личном кабинете unitpay пропишите обработчик платежей по шаблону:[ http://адрес\_вашего\_сайта/payments.php/unitpay](http://xn--__-6kcbbakjfkd5c8cvaqht4h/payments.php/unitpay) и нажмите enter. 

If you are not mistaken, the payment handler will say **OK!**

![](../../.gitbook/assets/214124.png)

6. ДОПОЛНЕНИЕ: чтобы в магазине можно было оплачивать товар, нужно включить этот шаг. "**Магазин → Настройки → Оформление заказа → включите шаг Оплаты**".

![](../../.gitbook/assets/234234.png)



