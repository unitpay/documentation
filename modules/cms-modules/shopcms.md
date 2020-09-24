# ShopCMS

### Инструкция по настройке и установке модуля.

1. Скачайте [архив](https://github.com/unitpay/shopcms-module/releases/download/v2.0.1/phpshop-module-2.0.1.zip) модуля.

2. Скопируйте содержимое директории "unitpay" из архива в корень вашего сайта.

3. Перейдите в "Модули" -&gt; "Модули оплаты" и нажмите "Инсталлировать".

4. Нажмите "Редактировать" напротив установленного модуля "Unitpay".

5. Введите DOMAIN - unitpay.money, PUBLIC KEY и SECRET KEY, которые вы можете взять из личного кабинета Unitpay.ru.

6. Выберите статусы, в которые будет устанавливаться заказ после успешной оплаты либо ошибки.

7. Сохраните изменения.

8. Перейдите в "Настройки"-&gt;"Варианты оплаты" и добавьте новый вариант оплаты "Unitpay".

9. В файл core/includes/helper.php добавьте следующий код:

```text
// Helper for Unitpay
// Result Url - index.php?unitpay=yes
if(isset($_GET["unitpay"])){
    $data = $_GET;
    $params = $data['params'];
    $orderID = (int)$params['account'];
    $q = db_query( "select paymethod  from ".ORDERS_TABLE." where orderID=".$orderID);
    $order = db_fetch_row($q);
    if ( $order )
    {
        $paymentMethod = payGetPaymentMethodById( $order["paymethod"] );
        $currentPaymentModule = modGetModuleObj( $paymentMethod["module_id"], PAYMENT_MODULE );
        if ( $currentPaymentModule != null ) $result = $currentPaymentModule->after_payment_php( $_GET );
    }else{
        header('Content-Type: application/json');
        $result = array('error' =>
            array('message' => 'Order not present')
        );
        $result = json_encode($result);
        die($result);
    }
}

<br>
```

10. Очистите кеш, для этого удалите содержимое папки cache.

11. В личном кабинете Unitpay.ru введите адрес обработчика платежей  [http://&lt;адрес](http://xn--%3C-8cdug0fj/) вашего сайта&gt;/index.php?unitpay=yes

