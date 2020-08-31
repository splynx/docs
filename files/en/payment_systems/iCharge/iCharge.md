iCharge
==================

**iCharge** is a Splynx add-on which allows refilling of customer balances and pay invoices via the Xilo payment gateway - https://xilo.com.**

The add-on can work with different credit cards, if cards are saved on the customer profile, the addon allows you to charge all customers using *Direct debit orders*.

The add-on can be installed in two methods, via the CLI or Web UI of your Splynx server.

To install the *splynx-icharge* add-on via CLI, the following commands can be used:


```bash
apt-get update
apt-get install splynx-icharge
```
To install it via the Web UI:

Navigate to `Config → Integrations → Add-ons`:

![1.png](1.png)

Locate or search for the "splynx-icharge" add-on and click on the install icon in the *Actions* column:

![2.png](2.png)

Click on the "OK, confirm" button to begin the installation process:

![3.png](3.png)

After installation process has completed, you have to configure the addon:

Navigate to *Config → Integrations → Modules list:*

![4.png](4.png)

Set these parameters from the data in your https://xilo.com account and set  your server IP address on the Xilo xServ settings (IP address from where Xilo will take requests):

![6.png](6.png)

![5.1.png](5.1.png)

Thereafter, customers can pay for their invoices by using the iCharge system. Customers will see a new button *"Pay by iCharge"* in their customer portal as depicted below:

![7.png](7.png)

You can also enable entry points in *config -> integrations -> modules list -> Splynx iCharge Add-on* as depicted below:

![18.png](18.png)

![15.png](15.png)

Thereafter, customers will be able to pay for their invoices from the dashboard:

![16.png](16.png)

To refill balances, customers can use the following link - *“http://yoursplynxurl/icharge/”*:

![10.png](10.png)

Alternatively, you can enable the entry point in *config -> integrations -> modules list -> Splynx iCharge Add-on* as depicted below:

![18.png](18.png)

![17.png](17.png)

Thereafter, customers will be able to refill his balance from dashboard:

![19.png](19.png)

Customers can save pay-card details for future payments in the "Finance" section:

![12.png](12.png)

They can also add cards from the payment window as depicted below:
![8.png](8.png)

![9.png](9.png)

When customers saved their credit cards, you can charge all customers using one button! Navigate to *Finance → Invoices*, set the period and click "Charge" as at the screenshot:

![13.png](13.png)

![14.png](14.png)
