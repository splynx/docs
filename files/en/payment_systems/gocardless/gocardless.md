GoCardless
==========
Gocardless is a Splynx add-on used to synchronize customers, invoices and payments with Gocardless payment software - https://gocardless.com/.

Customers using Gogardless.com can pay for invoices through banks or you can charge your customers bank accounts by debit orders.

The add-on can be installed installed in two methods, via the CLI or Web UI of your Splynx server

To install the Gocardless add-on via CLI, the following commands can be used:

```
apt-get update
apt-get install splynx-gocardless-rb
```

To install it via the Web UI:

Navigate to `Config → Integrattions → Add-ons`:

![0.png](0.png)

Locate or search for the "splynx-gocardless-rb" addon and click on the install icon in the *Actions* column, you will be presented with a window to confirm or cancel the installation

![1.png](1.png)


Once the installation process has completed, we can proceed to configuration the add-on under *Config / Integrations / GoCardless*:

![2.png](2.png)

![3.png](3.png)

Please enter your Splynx URL in the field provided and click on the 'Link Splynx with GoCardless' button.  You will be redirected to the GoCardless registration page:

![4.png](4.png)

Enter your registration data in the registration form and click on the *'Connect'* button.

![5.png](5.png)

If everything is correct, you will be redirected to finish-page:

![6.png](6.png)

Thereafter, customers will have to enter their registration details in the provided fields of the new Tab:  *"Gocardless" → Main menu "Finance"*, as depicted below:

![6.1.png](6.1.png)

![9.png](9.png)

![10.png](10.png)


Once these settings have been configured, customers will see a new pay window on their customer portal *Dashboard*, and a new icon in the Invoices section:

![7.png](7.png)

![8.png](8.png)

Customers can click  on the new icon to make a payment:

![12.png](12.png)

![13.png](13.png)

After a period of time, which can be view on the following page: https://gocardless.com/direct-debit/timings/, we can see the payment in the customer and admin-portal, as depicted below:

![14.png](14.png)

![15.png](15.png)

Customers can also refill their balances using the following link - “http://yoursplynxurl/gocardless-rb”:

![16.png](16.png)

Additionally, you can **charge** all customers, using one button! Navigate to *Finance → Invoices,* set the period and click on the "Charge" button as depicted below:

![18.png](18.png)

You can also sync all customers from Splynx to GoCardless, simply follow the steps below:

Navigate to *Config / Integrations / GoCardless* :

![18.jpg](18.jpg)

Select the Payment method and Partner, then click on the *export* button:

![19.jpg](19.jpg)

You will receive your customers list as a csv-file. Thereafter, you can open your GoCardless dashboard on https://gocardless.com/ and upload the csv-file, as depicted below:

![20.jpg](20.jpg)

![21.jpg](21.jpg)

All customers on the list will receive emails to authorise the action:

![23.jpg](23.jpg)

![22.jpg](22.jpg)

![25.jpg](25.jpg)

![26.jpg](26.jpg)

![27.jpg](27.jpg)
