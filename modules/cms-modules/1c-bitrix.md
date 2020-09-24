# 1C Bitrix

**The Module Setup and Installation Instruction**

A simple and convenient solution for connecting CMS 1C-Bitrix clients to our platform. To install the module, just [use the Marketplace service](https://marketplace.1c-bitrix.ru/solutions/unitpay.paymodule/).

**Installation and Setup**

Solution settings can be set in the menu Settings-&gt; Product settings-&gt; Module settings-&gt; UnitPay Payment System.

You need to fill in the following mandatory parameters in the module settings:

* Unitpay.money domain;
* Project NO. \(specified in the title of the project of the UnitPay account\); 
* Public key of the project \(specified on the project page in the Payment Method section of the UnitPay account\); 
* Secret key of the project \(specified in the project settings \(SECRET KEY parameter\) of the UnitPay account\); 
* description of the order \(e.g. Payment for an order from a flower shop\); 
* currency \(the currency in which the amount due is invoiced\); 
* language of the payment method. 
* transmit the order content for the receipt - if you use a cash register in the UnitPay system.

After creating a new payment system, select UnitPay as the handler for the necessary types of payers. The payment system does not require any additional customization.

In the payment handler of the project settings on the UnitPay website, you need to specify [http://your\_site\_name/unitpay\_processor/result.php?UNITPAY\_HANDLER=UNITPAY](http://your_site_name/unitpay_processor/result.php?UNITPAY_HANDLER=UNITPAY)

**Update from czebra.unitpay**

To update the module, you need to:

* delete the old module
* install and set up the module according to the instruction above; 
* Change the handler url in your account _at_ [http://your\_site\_name/unitpay\_processor/result.php?UNITPAY\_HANDLER=UNITPAY](http://your_site_name/unitpay_processor/result.php?UNITPAY_HANDLER=UNITPAY); 

