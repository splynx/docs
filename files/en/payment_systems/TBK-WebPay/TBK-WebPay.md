TBK-WebPay
=================

TBK-WebPay is a Splynx add-on which allows refilling of customer balances and paying of invoices via the payment gateway -  http://www.transbank.cl

The add-on can be installed in two methods, via the CLI or the Web UI of your Splynx server.

To install the Splynx-TBK-Webpay add-on via CLI, the following commands can be used:

```
apt-get update
apt-get install splynx-tbk-webpay
```
To install it via the Web UI:

Navigate to `Config → Integrations → Add-ons`:

![(image)](0.png)

Locate or search for the "splynx-tbk-webpay" add-on and click on the install icon in the *Actions* column, you will be presented with a window to confirm or cancel the installation, click on confirm to begin the installation process

![(image)](1.png)

Therafter, the first step is to register in http://www.transbank.cl. After that, you have to obtain a Commercial Code on http://www.transbank.cl and set it in *Config/Integrations/Modules list/splynx_addon_webpay.* (you can also set fee parameters here)

Navigate to *Config/Integrations/Modules list*

![(image)](3.png)

Locate or search for the "splynx-tbk-webpay" add-on and click on the edit icon in the *Actions* column

![(image)](4.png)
Enter the *Commercial Code* and save:

![(image)](5.png)

Then navigate to *Config/Integrations/WebPay Certificates* and generate a self-signed certificate

![(image)](6.png)

![(image)](7.png)

Once the configuration has been completed, customers can pay for their invoices and refill their balances using the transbank.cl system. Customers will see a new button _To Pay_ as depicted below:

![(image)](8.png)

After customers press on the *Pay button*, they will have to confirm their payment:

![(image)](9.png)

![(image)](10.png)

![(image)](11.png)

![(image)](12.png)

![(image)](13.png)

![(image)](14.png)

![(image)](15.png)

If everything went well, you will see the status of the invoice marked as "Paid" (in the customer and admin portal):

![(image)](16.png)

To refill balances, customers can use the following link - http://yoursplynxurl/webpay/ or navigate to *Finance/Pay via Webpay*.

![(image)](17.png)

![(image)](18.png)

![(image)](19.png)

![(image)](20.png)

![(image)](21.png)

![(image)](22.png)

![(image)](23.png)
