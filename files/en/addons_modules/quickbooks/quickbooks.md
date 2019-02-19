Quickbooks accounting (Add-on is outdated and not supporting)
==========================================

**(Add-on is outdated and not supporting)**

The installation of Add-on is performed with two commands:
```
apt update
apt install splynx-quickbooks
```

After installation, the QuickBooks addon appears on Splynx under Finance menu:
![Entry point 1](1.png)

We need to get a Quickbooks Online account to start the integration.
![Entry point 1](2.png)

![Entry point 1](3.png)

When the account is created and Splynx Quickbooks Add-on is installed on Splynx server, we can start syncing it together.

First of all, we need to connect Add-on to our Quickbooks account:
![Entry point 1](4.png)

Click on "Here" link and follow to QB login page:
![Entry point 1](5.png)

Whent it's connected, Add-on shows connected message
![Entry point 1](6.png)
Now we need to setup few things in CLI of Linux server where Splynx is running.

Open file /var/www/splynx/addons/quickbooks/config/params.php and set the correct URL, Sandbox = false and your country code:
![Entry point 1](7.png)
Now we can add Taxes in Quickbooks, set Payment Methods and sync it with Splynx server:
![Entry point 1](8.png)

![Entry point 1](9.png)
Splynx add-on displays the Tax codes that we need to put again to

/var/www/splynx/addons/quickbooks/config/params.php
![Entry point 1](10.png)

![Entry point 1](11.png)

The same thing is with Payment types:
![Entry point 1](12.png)

![Entry point 1](13.png)
When this is done, we can sync our customers from Splynx to Quickbooks or match existing clients in databases:
![Entry point 1](14.png)

![Entry point 1](15.png)

![Entry point 1](16.png)
We can check if all clients were pushed to QuickBooks:
![Entry point 1](17.png)
To sync Invoices and Payment on the fly we need to enable WebHooks inside Splynx settings, please open menu Config → Hooks:
![Entry point 1](18.png)
Now we are ready to issue Invoices in Splynx and process Payments. This information will be sent to QB online immediately. All changes are also synced immediately between two systems.

Let's issue 3 invoices in Splynx:
![Entry point 1](19.png)
Got it, they are moved to Quickbooks as well!
![Entry point 1](20.png)
We can open the Invoice in Splynx and see that it has a QB ID that identifies it in QuickBooks software:
![Entry point 1](21.png)
After processing payment in Splynx, information is also moved to Quickbooks. Let's pay 2 invoices in Splynx:
![Entry point 1](22.png)
Payments are sent to QuickBooks in few seconds:
![Entry point 1](23.png)
Of course, all information is set in correct accounts in Accounting part of QB and Taxes are also calculated properly:
![Entry point 1](24.png)
