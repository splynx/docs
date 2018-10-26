GoCardless
==========
Gocardless.com is a Splynx add-on. It uses to synchronize customers, invoices and payments with Gocardless.com payment software - https://gocardless.com/. Customers using Gogardless.com can pay your invoices through banks or you can charge your customers bank accounts by debit orders.

**To install Gocardless.com add-on, use following commands:**

apt-get update

apt-get install splynx-gocardless-rb

**or you can install it from Web UI:**

*Config → Integrattions → Add-ons:*

![0.png](0.png)

![1.png](1.png)


Then go to the *Config / Integrations* and proceed configuration:

![2.png](2.png)

![3.png](3.png)

Please, check your Splynx URL and click button 'Link Splynx with GoCardless'.  You will be redirect to registration page GoCardless:

![4.png](4.png)

![5.png](5.png)

And now, enter your registration data in registration form and click *'Connect'* button. If everything is correct, you will be redirected to finish-page:

![6.png](6.png)

After that customers have to enter registration details in current fields in new Tab - *"Gocardless" → Main menu "Finance"* as on the screenshot:

![6.1.png](6.1.png)

![9.png](9.png)

![10.png](10.png)

That is all settings.

Now, customers will see a new pay window on his *Dashboard* and new icon in Invoices list:

![7.png](7.png)

![8.png](8.png)

and can click to receive a payment:

![12.png](12.png)

![13.png](13.png)

After some time (https://gocardless.com/direct-debit/timings/) we can see the payment in portal and admin-side, as on screenshots:

![14.png](14.png)

![15.png](15.png)

Also, customer can refill balance using link - “http://yoursplynxurl/gocardless-rb”:

![16.png](16.png)

Besides, you can **charge** all customers, using one button! Go to *Finance → Invoices,* set the period and click "Charge" as at screenshot:

![18.png](18.png)

Next one option, you can sync all customer, just follow steps below:

open *Config / Integrations / GoCardless* :

![18.jpg](18.jpg)

then select Payment method, Partner and click *export* button:

![19.jpg](19.jpg)

You will receive customers list in csv-file. After that you should open dashboard on https://gocardless.com/ and upload csv-file, as on next screenshots:

![20.jpg](20.jpg)

![21.jpg](21.jpg)

Now, all customers from list receive mails and will have to authorise:

![23.jpg](23.jpg)

![22.jpg](22.jpg)

![25.jpg](25.jpg)

![26.jpg](26.jpg)

![27.jpg](27.jpg)
