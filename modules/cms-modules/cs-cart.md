# CS-Cart

**The Module Setup and Installation Instruction**

1. Download the [archive](https://github.com/unitpay/cscart-module/releases/download/1.0.2/cscart-module-1.0.2.zip) with the module.
2. Run queries from the install.sql file in your database.
3. Copy the contents of the Unitpay directory from the archive to the root of your site.
4. In the admin panel of the website menu, select Administration/Payment Methods.
5. Click + to add a new payment method.
6. In the window that appears:
7. enter a name for the new payment method,
8. select the Unitpay processor from the drop-down list,
9. select the payment category: online payments.

![](https://gblobscdn.gitbook.com/assets%2Fdokumentacziya%2F-M9xezG_6tZ_3GRmvyig%2F-M9y3ACs8BjSLJtJtcU2%2F0.png?alt=media)https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5800c14cc697915a23d793d4/file-f4a2Rtg53K.png

1. Go to the Settings tab and enter the domain \(unitpay.money\), public and secret keys. You can get these keys in your Unitpay account.

![](https://gblobscdn.gitbook.com/assets%2Fdokumentacziya%2F-M9xezG_6tZ_3GRmvyig%2F-M9y3ACtWZ4Gikau0hX1%2F1.png?alt=media)https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5e69080d2c7d3a7e9ae905c3/file-NuCjKo9cBV.png

1. Click Create to create a new payment method.
2. In your Unitpay account, enter the path to the payment handler using the template: [http://&lt;your](http://%3Cyour/) site address&gt;/unitpay/callback.php

![](https://gblobscdn.gitbook.com/assets%2Fdokumentacziya%2F-M9xezG_6tZ_3GRmvyig%2F-M9y3ACurlb-l3fvMdUm%2F2.png?alt=media)https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5800c3a9c697915a23d793e9/file-6rY1j5zahv.png

