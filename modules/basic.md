# Basic

Suitable for most projects. To install it, just [download the module](https://github.com/unitpay/base_module) and follow the instructions in the readme.txt file.

**Step 1.** Create the unitpay\_payments table in the database:

![](../.gitbook/assets/image%20%2823%29.png)

The unitpay\_payments table will log information about payments made

**Step 2**. Place the scripts in any directory on the web server that can be accessed via the Internet. Make sure that php version 5.x.x or higher is installed on the server and the mysqli extension is available \(for working with mysql databases\).

**Step 3.** In config.php, specify parameters for connecting to the database, the cost of one unit \(item\) of goods, the secret key \(you can find it in the project settings in your unitpay.money account\), as well as the table with users and the field in this table that must be updated after payment.

**Step 4.** In your unitpay. money account, enter the handler's address in the project settings. In this case, this is the absolute URL at which index.php of the current module can be accessed.

