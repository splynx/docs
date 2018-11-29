iCharge
==================

**iCharge** is a Splynx add-on. It uses to synchronize customers, invoices and payments with payment software - https://xilo.com Customers using iCharge can pay your invoices through their credit cards.

Add-on can work with different credit cards, if cards are saved, then addon allows to charge all customers using *Direct debit order*.


To install *splynx-icharge* add-on, use following commands:


```bash
apt-get update
apt-get install splynx-icharge
```
or you can install it from Web UI:

*Config → Integrations → Add-ons:*

![1.png](1.png)

![2.png](2.png)

![3.png](3.png)

After installation you have to configure addon:

*Config → Integrations → Modules list:*

![4.png](4.png)

Set those parameters from your https://xilo.com account:

![6.png](6.png)

![5.png](5.png)

After that, customers can pay their invoices by using iCharge system. They will see a new button *"Pay by iCharge"* as on the screenshot:

![7.png](7.png)


To refill balance customers can use the link - *“http://yoursplynxurl/icharge/”*:

![10.png](10.png)


Customers can save pay-card details for the next payments in "Financ" menu:

![12.png](12.png)

or he can add it, from payment window as on the screenshot:
![8.png](8.png)

![9.png](9.png)

When customers saved their credit cards, you can charge all customers, using one button! Go to *Finance → Invoices*, set the period and click "Charge" as at the screenshot:

![13.png](13.png)

![14.png](14.png)
