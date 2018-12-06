Paystack
=========

Paystack is a Splynx add-on. It's used to synchronize customers, invoices and payments with Paystack payment gateway - https://paystack.com/.

To install Paystack add-on use following commands:

```
apt-get update
apt-get install splynx-paystack
```

or you can install it from Web UI:

*config -> Integrations -> Add-ons:*

![(image)](0.png)

![(image)](0.1.png)

![(image)](1.png)

![(image)](2.png)

After installation you have to configure params in *config -> Integrations -> Modules list*. And here you can set a fee parameters. Look at the screenshot:

![(image)](3.png)

![(image)](4.png)

![(image)](5.1.png)

Public and secret keys can be taken from *Paystack account:*

![(image)](14.png)

Now customers can pay their invoices using Paystack system in *Finance / Invoices:*

![(image)](7.png)

![(image)](8.png)

![(image)](9.png)

![(image)](10.1.png)

If everything went well, you will see status of invoice as "Paid" (portal and admin):

![(image)](11.png)

Besides that, you can charge all customers, using one button! Go to Finance → Invoices, set the period and click "Charge" as on a screenshot:

![(image)](12.png)

![(image)](13.png)
