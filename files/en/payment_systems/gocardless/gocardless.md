Gocardless.com
==============

Gocardless.com is a Splynx add-on. It uses to synchronize customers, invoices and payments with Gocardless.com payment software - [https://gocardless.com/](https://gocardless.com/). Customers using Gogardless.com can pay invoices through banks or you can charge your customers bank accounts by debit orders.

To install Gocardless.com add-on, use following commands:

```bash
apt-get update
apt-get install splynx-gocardless-rb
```

Then first step - you should to switch "sandbox" to "live" in the configuration:

![Selection_627.jpg](Selection_627.jpg)

![Selection_629.jpg](Selection_629.jpg)

Then go to the Config / Integrations and proceed configuration:

![Selection_630.jpg](Selection_630.jpg)

![Selection_631.jpg](Selection_631.jpg)

Please, check your Splynx URL and click button 'Link Splynx with GoCardless'. You will be redirect to registration page GoCardless:

![Selection_015.png](Selection_015.png)

And now, enter your registration data in registration form and click 'Connect' button. If everything is correct, you will be redirected to finish-page:

![Selection_016.png](Selection_016.png)

After that customers have to enter registration details in current fields in new Tab - "Gocardless" → Main menu "Finance" as on the screenshot:

![Selection_010.png](Selection_010.png)

That is all settings.

Now, customers will see a new icon in Invoices list:

![Selection_013.png](Selection_013.png)

and can click to receive a payment:

![Selection_006.png](Selection_006.png)

![Selection_007.png](Selection_007.png)

After some time ([https://gocardless.com/direct-debit/timings/](https://gocardless.com/direct-debit/timings/)) we can see the payment in portal and admin-side, as on screenshots:

![Selection_008.png](Selection_008.png)

![Selection_011.png](Selection_011.png)

Also, customer can refill balance using link - “http://yoursplynxurl/gocardless-rb”:

![Selection_009.png](Selection_009.png)

Besides, you can charge all customers, using one button! Go to _Finance → Invoices_, set the period and click "Charge" as at screenshot:

![Selection_020.png](Selection_020.png)

![Selection_001.png](Selection_001.png)

Next one option, you can sync all customer, just follow steps below:

open Config / Integrations / GoCardless :

![Selection_273.jpg](Selection_273.jpg)

then select Payment method, Partner and click export button:

![Selection_274.jpg](Selection_274.jpg)

You will receive customers list in csv-file. After that you should open dashboard on [https://gocardless.com/](https://gocardless.com/) and upload csv-file, as on next screenshots:

![Selection_275.jpg](Selection_275.jpg)

![Selection_277.jpg](Selection_277.jpg)

![Selection_278.jpg](Selection_278.jpg)

Now, all customers from list receive mails and will have to authorise:

![Selection_279.jpg](Selection_279.jpg)

![Selection_280.jpg](Selection_280.jpg)

![Selection_281.jpg](Selection_281.jpg)

![Selection_282.jpg](Selection_282.jpg)