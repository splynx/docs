Quickbooks accounting (Add-on is outdated and is no longer supported)
==========================================

**(Add-on is outdated and is no longer supported)**

The installation of Add-on is performed with the following two commands:
```
apt update
apt install splynx-quickbooks
```

After the installation process has completed, the QuickBooks addon will appear on Splynx under the Finance module:

![Entry point 1](1.png)

It is necessary to obtain a Quickbooks Online account to start the integration.
![Entry point 1](2.png)

![Entry point 1](3.png)

Once the account is created and the Splynx Quickbooks Add-on is installed on the Splynx server, we can start syncing it together.

First of all, we need to connect the Add-on to our Quickbooks account:
![Entry point 1](4.png)

Click on the "Here" link and follow to the QB login page:
![Entry point 1](5.png)

When it's connected, the Add-on status will show "connected"
![Entry point 1](6.png)


Thereafter, we need to setup a few elements in the CLI of the Linux server where Splynx is running from.

Open the /var/www/splynx/addons/quickbooks/config/params.php file and set the correct URL, Sandbox = false and your country code:
![Entry point 1](7.png)

Now we can add Taxes in Quickbooks, set Payment Methods and sync it with the Splynx server:
![Entry point 1](8.png)

![Entry point 1](9.png)

The Splynx add-on displays the Tax codes that we will need to add to the /var/www/splynx/addons/quickbooks/config/params.php file again, via CLI

![Entry point 1](10.png)

![Entry point 1](11.png)

The same should be done for Payment types:
![Entry point 1](12.png)

![Entry point 1](13.png)

When this is done, we can sync our customers from Splynx to Quickbooks or match existing clients in the databases:
![Entry point 1](14.png)

![Entry point 1](15.png)

![Entry point 1](16.png)

We can check if all clients were pushed to QuickBooks:
![Entry point 1](17.png)

To sync Invoices and Payments, we need to enable WebHooks within Splynx settings, navigate to `Config → Hooks`:

![Entry point 1](18.png)

Now we are ready to issue Invoices in Splynx and process Payments. This information will be sent to QB online immediately. All changes are also synced immediately between the two systems.

Let's issue 3 invoices in Splynx:
![Entry point 1](19.png)

Done! they've been synced to Quickbooks as well!
![Entry point 1](20.png)

We can open the Invoice in Splynx and see that it has a QB ID that identifies it in the QuickBooks software:
![Entry point 1](21.png)

After processing payments in Splynx, the information is also synced to Quickbooks. Let's pay 2 invoices in Splynx:
![Entry point 1](22.png)

Payments are sent to QuickBooks in few seconds:
![Entry point 1](23.png)

Of course, all information is set in the correct accounts in the Accounting part of QB and Taxes are also calculated properly:
![Entry point 1](24.png)
