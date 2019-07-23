Paymentexpress
==============

Paymentexpress is a Splynx add-on. It allows to refill balance and pay invoices via payment gateway - https://www.paymentexpress.com/

Add-on can work with different credit cards, if cards are saved, then addon allows to charge all customers using Direct debit order.

To install splynx-paymentexpress add-on, use following commands:

```
apt-get update
apt-get install splynx-paymentexpress
```
or you can install it from Web UI:

Config → Integrations → Add-ons:

![(image)](0.png)

![(image)](1.png)

After installation you have to configure addon:

Config → Integrations → Modules list:

![(image)](3.png)

![(image)](4.png)

![(image)](5.png)

In this menu you can also configure fee parameters:

![(image)](6.png)

Customers can save pay-card details for the next payments in "Finance" menu:

![(image)](7.png)

or he can add it, from payment window while paying invoices as on the screenshot:
![(image)](9.png)

![(image)](9-1.png)

Also you can turn on entry point in Config -> Integrations -> Modules List -> Splynx Add-on Payment Express as on the screenshot:

![(image)](10-1.png)

![(image)](10.png)

After that customers with billing type "Prepaid daily" will be able to refill balance from dashboard:

![(image)](11.png)

Customers with other billing type can refill balance by using the link - “http://yoursplynxurl/paymentexpress/"

![(image)](12.png)

When customers saved their credit cards, you can charge all customers, using one button! Go to Finance → Invoices, set the period and click "Charge" as at the screenshot:

![(image)](14.png)

![(image)](15.png)
