# HostCMS

1. Download the [module](https://github.com/unitpay/hostcms-module/releases/download/1.0.1/hostcms-module-1.0.1.zip)​
2. Go to the admin panel of your site
3. Go to Content -&gt;Online stores, select your store and then go to directories -&gt;payment systems.
4. Add a new payment system, write Unitpay in the name and for example, Unitpay payment system in the description and click Apply.
5. Click the Edit button next to the Unitpay payment system, then go to the Additional tab and remember the number in the ID field

![](https://gblobscdn.gitbook.com/assets%2Fdokumentacziya%2F-M9xezG_6tZ_3GRmvyig%2F-M9y3VFeyI9_1p1AghP4%2F0.png?alt=media)https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5836d65c9033600698172453/file-AlNALyI8nn.png

1. Next, go to the Main tab and copy the contents of the module file handlerXX.php in the Handler field
2. In the name of Shop\_Payment\_System\_HandlerXX class, enter the ID you have previously remembered instead of XX.
3. In the handler, enter the values of the variables $domain = 'unitpay.money', $public\_key and $secret\_key which you can get in your unitpay.money personal account
4. If necessary, assign the code of the currency \(which is available in the store\) in which you want to receive payments to the value of $currency\_name variable. It is RUB by default.
5. In your Unitpay.ru account, enter the address of the payment handler [http://&lt;your](http://%3Cyour/) site address&gt;/shop/cart/

![](https://gblobscdn.gitbook.com/assets%2Fdokumentacziya%2F-M9xezG_6tZ_3GRmvyig%2F-M9y3VFfDHo5_CPrwtFT%2F1.png?alt=media)https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5836d9a3c6979106d373617d/file-WigCbE6rTX.png

