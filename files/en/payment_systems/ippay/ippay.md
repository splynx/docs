IPpay by Convergence
==================

IPpay is a Splynx add-on which allows refilling of customer balances and paying invoices via the IPpay payment gateway - https://www.ippay.com/.

The Add-on can work with different credit cards, and if cards are saved on customer profiles, the addon allows you to charge all customers using *Direct debit orders*.

The add-on can be installed in two methods, via the CLI or the Web UI of your Splynx server

To install the *splynx-ippay* add-on via CLI, the following commands can be used:


```bash
apt-get update
apt-get install splynx-ippay
```
To install it via the Web UI:

Navigate to `Config → Integrations → Add-ons`:

![1.png](1.png)

Locate or search for the "splynx-ippay" add-on and click on the install in the *Actions* column:

![2.png](2.png)

Click on the "OK, confirm" button to begin the installation process:

![3.png](3.png)

After installation process has completed, you have to configure addon:

Navigate to `Config → Integrations → Modules list`:

![4.png](4.png)

Locate or search for the "splynx-ippay" add-on and click on the edit icon in the *actions column:

![5.png](5.png)

![6.png](6.png)

Customers then have to add a credit card in the customer portal under *Finance/Credit card*:

![7.png](7.png)

![8.png](8.png)

Now customers can pay for their invoices using the IPpay system in *Finance / Invoices*:

![9.png](9.png)

![10.png](10.png)

![11.png](11.png)

If everything went well, you will see the status of invoice marked as "Paid" (in the portal and in the admin page):

![12.png](12.png)

On the customer portal dashboard, customers can also see the list of non-paid invoices and a "Pay" button near each invoice:

![13.png](13.png)

To refill balances, customers can use the following link - “http://yoursplynxurl/ippay”, where they have to enter an Amount of payment and click on "Add":

![14.png](14.png)

![15.png](15.png)

Additionally, you can charge all customers using one button! Navigate to *Finance → Invoices*, set the period and click on "Charge" as depicted below:

![16.png](16.png)

![17.png](17.png)

![18.png](18.png)
