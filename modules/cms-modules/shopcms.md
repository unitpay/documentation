# ShopCMS

### 

**The Module Setup and Installation Instruction**

1. Download the [archive](https://github.com/unitpay/shopcms-module/archive/master.zip) with the module.
2. Copy the contents of the Unitpay directory from the archive to the root of your site.
3. Go to Modules -&gt; Payment modules and click Install.
4. Click Edit next to the installed Unitpay module.
5. Enter DOMAIN \(unitpay.money\), PUBLIC KEY, and SECRET KEY which you can get in your Unitpay.money personal account.
6. Select the statuses which will be assigned to the order in case of successful or failed payment.
7. Save your changes.
8. Go to Settings -&gt; Payment options and add a new payment option - Unitpay.
9. Add the following code to core/includes/helper.php file:

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

10. Clear your cache by deleting the contents of the cache folder.

11. In your Unitpay personal account, enter the address of the payment handler [http://&lt;your](http://<your) site address&gt;/ndex.php?unitpay=yes

