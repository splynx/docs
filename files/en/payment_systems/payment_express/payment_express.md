Paymentexpress
==============

Paymentexpress is a Splynx add-on. It allows to refill balance and pay invoices via payment gateway - https://www.paymentexpress.com/

Add-on can work with different credit cards, if cards are saved, then addon allows to charge all customers using Direct debit order.

To install splynx-icharge add-on, use following commands:

```
apt-get update
apt-get install splynx-paymentexpress
```
or you can install it from Web UI:

Config → Integrations → Add-ons:

![(image)](0.png)

![(image)](1.png)

![(image)](2.png)

After installation you have to configure addon:

Config → Integrations → Modules list:

![(image)](3.png)

![(image)](4.png)

![(image)](5.png)

In this menu you can also configure fee parameters:

![(image)](6.png)

Customers can save pay-card details for the next payments in "Financ" menu:

![(image)](7.png)

![(image)](8.png)

or he can add it, from payment window as on the screenshot:

![(image)](13.png)

After that, customers can pay their invoices by using Payment Express system. They will see a new button "Pay by Payment Express" as on the screenshot:

![(image)](9.png)

also you can turn on entry point in config -> integrations -> modules list -> Splynx Add-on Payment Express as on the screenshot:

![(image)](4.png)

![(image)](10.png)

After that customers with billing type "Prepaid daily" will be able to refill balance from dashboard:

![(image)](11.png)

Customers with other billing type canrefill balance by using the link - “http://yoursplynxurl/paymentexpress/"

![(image)](12.png)

When customers saved their credit cards, you can charge all customers, using one button! Go to Finance → Invoices, set the period and click "Charge" as at the screenshot:

![(image)](14.png)

![(image)](15.png)
