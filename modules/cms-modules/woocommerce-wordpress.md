# Woocommerce Wordpress

**The Module Setup and Installation Instruction**

**Important Note!!!** If you use Wordpress and the [api](../../payments/create-payment.md) instead of our module to generate requests to our platform, you need to contact the UnitPay manager to whitelist your IP.

1. Download the [archive](https://github.com/unitpay/woocommerce-module/archive/master.zip) with the module.
2. Copy the contents of the unitpay directory in the archive to the /&lt;site root&gt;/wp-content/plugins/ directory.
3. Go to Plugins -&gt; Installed and click Enable next to the UnitPay plugin.
4. In the menu, go to the WooCommerce -&gt; Settings and then go to the Payments tab and select UnitPay there.
5. Insert the value of unitpay.money in the DOMAIN field. Copy the public and secret key which you can get from your Unitpay account in the PUBLIC KEY and SECRET KEY fields. Click Save changes.

![](https://gblobscdn.gitbook.com/assets%2Fdokumentacziya%2F-M9xezG_6tZ_3GRmvyig%2F-M9y5FjX1KHBc695SgPF%2F0.png?alt=media)https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5e68dc452c7d3a7e9ae90273/file-mPvwuDGXSV.png

1. Enter the payment handler in your Unitpay.money personal account using the template: [http://&lt;your\_site\_name&gt;/?wc-api=wc\_unitpay](http://%3Cyour_site_name%3E/?wc-api=wc_unitpay)​

![](https://gblobscdn.gitbook.com/assets%2Fdokumentacziya%2F-M9xezG_6tZ_3GRmvyig%2F-M9y5FjYu7rSe-dC4Fo0%2F1.png?alt=media)https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/579634b7c6979160ca147078/file-YJh47Ao3iN.png

