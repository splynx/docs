TBK-WebPay is a Splynx add-on. It allows to refill balance and pay invoices via payment gateway -  http://www.transbank.cl

To install Splynx-Integrapay add-on, use following commands:

```
apt-get update
apt-get install splynx-tbk-webpay
```
or you can install it from Web UI:

*Config → Integrations → Add-ons:*

![(image)](0.png)

![(image)](1.png)

![(image)](2.png)

Then first step - you should to register in http://www.transbank.cl. After that, you have to get Commercial Code on http://www.transbank.cl and set it at *Config/Integrations/Modules list/splynx_addon_webpay.* (And you can also set fee parameters here)

![(image)](3.png)

![(image)](4.png)

![(image)](5.png)

Then go to *Config/Integrations/WebPay Certificates* and generate self-signed certificate

![(image)](6.png)

![(image)](7.png)

After that, customers can pay their invoices and refill balances using transbank.cl system. They will see a new button _To Pay_ as on the screenshot:

![(image)](8.png)

After customers will press *Pay button* they will have to confirm their payment:

![(image)](9.png)

![(image)](10.png)

![(image)](11.png)

![(image)](12.png)

![(image)](13.png)

![(image)](14.png)

![(image)](15.png)

If everything went well, you will see status of invoice as "Paid" (portal and admin):

![(image)](16.png)

To refill balance customers can use the link - http://yoursplynxurl/webpay/ or go to the *Finance/Pay via Webpay*.

![(image)](17.png)

![(image)](18.png)

![(image)](19.png)

![(image)](20.png)

![(image)](21.png)

![(image)](22.png)

![(image)](23.png)
