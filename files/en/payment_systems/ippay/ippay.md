IPpay by Convergence
==================

IPpay is a Splynx add-on. It allows to refill balance and pay invoices via IPpay payment gateway - https://www.ippay.com/.

Add-on can work with different credit cards, if cards are saved, then addon allows to charge all customers using *Direct debit order*.

To install *splynx-ippay* add-on, use following commands:


```bash
apt-get update
apt-get install splynx-ippay
```
or you can install it from Web UI:

*Config → Integrations → Add-ons:*

![1.png](1.png)

![2.png](2.png)

![3.png](3.png)

After installation you have to configure addon:

*Config → Integrations → Modules list:*

![4.png](4.png)

![5.png](5.png)

![6.png](6.png)

Then customers have to add a credit card:

![7.png](7.png)

![8.png](8.png)

Now customers can pay their invoices using IPpay system in Finance / Invoices:

![9.png](9.png)

![10.png](10.png)

![11.png](11.png)

If everything went well, you will see status of invoice as "Paid" (in portal and in admin):

![12.png](12.png)

On a portal dashboard customers can also see the list of non-paid invoices and "Pay" button near each invoice:

![13.png](13.png)

To refill balance customers can use the link - “http://yoursplynxurl/ippay”, where they have to enter Amount of payment and click "Add":

![14.png](14.png)

![15.png](15.png)

Besides that, you can charge all customers using one button! Go to Finance → Invoices, set the period and click "Charge" as on a screenshot:

![16.png](16.png)

![17.png](17.png)

![18.png](18.png)
