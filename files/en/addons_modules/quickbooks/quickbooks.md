Quickbooks accounting
==========================================

_Splynx QuickBooks_ is the add-on of Splynx which is used to synchronize customers, invoices and payments with the [Quickbooks accounting gateway](https://quickbooks.intuit.com/).

### Important:

**It's recommended do not configure the add-on on your own.**
**Please, contact our support team before starting the accounting integration.**

The add-on can be installed in two ways:
* via the command-line interface (CLI) and the following commands
```
apt update
apt install splynx-quickbooks
```
* via the Web UI of your Splynx server in `Config → Integrations → Add-ons`
![Install add-on](Selection_f3f25.png)

After the installation process has completed, click on `Finance` item on the sidebar of Splynx and in the drop-down menu click on `QuickBooks Accounting`.

![Entry point 1](1.png)

After that, it is necessary to obtain a Quickbooks Online account to start the integration (the screenshots related to Quickbooks were taken from its developer sandbox environment).

![Entry point 1](2.png)

And create your company

![Entry point 1](3.png)

The settings of QuickBooks Accounting add-on is located in `Config → Integration → Modules list`, click on the edit button in the Actions column:

![Entry point 1](Selection_c31f3.png)

To open the configuration of add-on entry points click on _Edit entry points_ icon:

![Entry point 1](Selection_fd768.png)

The general configuration of the QuickBooks integration module can be viewed and edited here:

![Entry point 1](Selection_afeaa.png)

![Entry point 1](Selection_bbb87u.png)

### Accounting API settings:

**Splynx domain** - the Splynx domain must be the same as the API domain URL but without last slash "/". **HTTPS is required!**;

**Country code** - Choose the required country code (US, FR or Other);

**US tax code** - (for US companies only) specify the tax code which will be applied to invoices. The id can be obtained from `Config → Finance → Accounting tax rates`;

**Currency code** - the currency that is used for customers, invoices and payments.

### Synchronization settings:

**Payment method ID** - select the payment method for imported payments;

**Bank statements group** - group bank statements by "month" or "day";

**Partners ignore list** - select the partners of which will be ignored in sync process. Customers, invoices and payments of the partners selected here **WILL NOT** be synced with QuickBooks;

**Payments synchronization direction** - define the direction of syncing payments: _QuickBooks → Splynx_, _Splynx → QuickBooks_ or _Bidirectional_;

**Payments push to QuickBooks** - select the payment methods to sync to QuickBooks, this selection only applies if the selected method to sync payments is set to _Splynx → QuickBooks_.
_Please note that you do not have to select QuickBooks in the list of payment methods to sync as this will grab payments from QuickBooks._;

**Import payments from date** - specify the date in `Y-m-d` format, e.g. 2021-05-01, which will be used as the start date for importing all prepayments to Splynx;

**Export invoices from date** - set a date in `Y-m-d` format, e.g. 2021-01-01 from which the invoices will be synchronized. The invoices that have been created by this date will be ignored during export. Will be checked by the invoice field `Date`.

**Create payment without invoice** - a toggle allows to enable creating payment in Splynx when customer doesn't have invoice (e.g. for the partial payments in *QuickBooks*) or, in disabled status - only bank statement (-s) will be created in Splynx. Used on payments import. Attention: in some cases can lead to duplicate payments. Use this option with caution;

**Customer name pattern** - used to set a customer's name pattern during sync to *QuickBooks* where it will be represented as `Display name as`. The next variables can be used: `{id}, {login}, {name}, {email}`. By default: `{name}`.


<details>
<summary><b>name display example</b></summary>
<p markdown="1">


![](display_name_example1.png)

![](display_name_example2.png)


</p>
</details>


### Cron settings

**Customers** - enables/disables automatic syncing of customers;

**Invoices** - enables/disables automatic syncing of invoices;

**Payments** - enables/disables automatic syncing of payments.

_It is recommended that all settings in the "Cron Settings" section should be disabled for the initial set up of the add-on to avoid syncing all these elements automatically via cron jobs, the first import and export should be done manually in `Finance → QuickBooks Accounting`_

### Let's start with QuickBooks

Click on `Finance` item on the sidebar of Splynx and in the drop-down menu click on `QuickBooks Accounting`.

![Entry point 1](1.png)

First of all, we need to connect the Add-on to our Quickbooks account:

![Entry point 1](4.png)

Click on the button _Connect with QuickBooks_, enter your account credentials and press _Connect_ to allow Splynx to view and update the date on the QuickBooks side:

![Entry point 1](5.png)

When it's connected, the token will be created:

![Entry point 1](6.png)

We can add/edit Taxes, Products and Services in Quickbooks:

![Entry point 1](7.png)
![Entry point 1](8.png)
![Entry point 1](9.png)
![Entry point 1](Selection_79293.png)

The taxes should be the same as the taxes in Splynx (`Config → Finance → Taxes`) to work properly.

Now, in `Finance → QuickBooks Accounting` run _Import mapping settings into Splynx_

![Entry point 1](10.png)

After successful synchronization,
```
2021-05-13 09:04:28.413400 Start accounting categories synchronization
2021-05-13 09:04:31.119300 Accounting synchronization completed
2021-05-13 09:04:31.119500 Done!
2021-05-13 09:04:31.119900 Start tax rates synchronization
2021-05-13 09:04:32.157200 Tax rates synchronization completed
2021-05-13 09:04:32.157300 Done!
2021-05-13 09:04:32.157400 Start accounting bank accounts synchronization
2021-05-13 09:04:33.162500 Accounting bank accounts synchronization completed
2021-05-13 09:04:33.162600 Done!
```
make chnages to _Accounting categories_, _Accounting bank accounts_ and _Taxes settings_ in `Config → Finance`

![Entry point 1](11.png)

Let's look at this in more details.
In `Config → Finance → Accounting categories` all accounting categories from QuickBooks (`Sales →  Products and Services`) must be assigned to transactions categories (`Config →  Finance → Transaction categories`) in Splynx

![Entry point 1](12.png)

As soon as the relevant categories are configured, we can proceed with bank accounts `Config → Finance → Accounting bank accounts`. We will follow the same steps, assign the QuickBooks bank accounts (`Accounting →  Chart of Accounts types`) to payment methods (`Config → Finance → Payment methods`) in Splynx, also the default bank account should be selected.

![Entry point 1](13.png).

And the last one - `Config → Finance → Accounting tax rates`:
For US company select "NON" for zero values and "TAX" for other values

![Entry point 1](14.png)

And in `Config → Integration → Modules list → QuickBooks Accounting` set the tax rate accounting id and the currency:

![Entry point 1](15.png)

![Entry point 1](16.png)

For other countries - select the matching between taxes in Splynx and in Quickbooks:

![Entry point 1](17.png)

_Pay attention that the invoices cannot be updated for France._

When the accounting settings are done, we can export our customers from Splynx to Quickbooks or match existing clients in the databases:

![Entry point 1](18.png)

We can check if all clients were pushed to QuickBooks:

![Entry point 1](19.png)

Once the customers export has completed, we can export the invoices:

**NOTE:**

- The invoices without transactions or marked as **Deleted** in Splynx will not be synced to Quickbooks;

- The invoices in Splynx with negative total amount will be exported to Quickbooks as **Credit Note** or **Credit Memo** (the name depends on the company location).

![Entry point 1](20.png)

![Entry point 1](21.png)

![](credit_memo.png)

<details>
<summary>What Is A Credit Note?</summary>
<div markdown="1">

The credit notes can be used in any situation that would require an invoice to be changed and re-issued. For example, the credit note should be issued when there is a need to cancel all or part of an invoice that has already been charged. This is done to keep accounting records straight since invoices cannot be deleted or edited once issued. Credit notes allow you to delete the amount of the invoice from your financial records without deleting the invoice itself in cases when the invoices deleting is unlawful.

</div>
</details>

And after that export the payments from Splynx to Quickbooks (depends on _Payments synchronization direction setting_ in add-on configuration), you can check received payments via report.

![Entry point 1](22.png)

![Entry point 1](23.png)

Now we are ready to issue Invoices in Splynx and process Payments. This information will be sent to Quickbooks online immediately. All changes are also synced immediately between the two systems.

Let's issue 3 invoices in Splynx:
![Entry point 1](24.png)

Done! they've been synced to Quickbooks as well!

![Entry point 1](25.png)

After processing payments in Splynx, the information is also synced to Quickbooks. Let's pay 2 invoices in Splynx:

![Entry point 1](26.png)

Payments are sent to QuickBooks in few seconds:

![Entry point 1](27.png)

### Quickbooks logs

Sync logs are located in `Administration → Logs → Accounting integrations`

![Entry point 1](28.png)

If a customer/invoice/payment has an "Accounting ID", this indicates that it was synced, if not, it was not synced.

![Entry point 1](29.png)

The same logic is for invoices and payments, if accounting ID is present - it was synced.

### Quickbooks tweaks

In `Config → Integration → Modules list → QuickBooks Accounting` when to click on the gear icon, we will see the drop down menu with additional settings related to QuickBooks add-on:

![Entry point 1](30u.png)

**Connect with QuickBook** - if the QuickBooks Accounting addon was disconnected from the QuickBooks account, you can reconnect it here;

**Refresh OAuth token** - setting to refresh the OAuth token;

**Manual Synchronization** - used to go back to manual synchronization window;

**Customers manual pairing** - setting is used to open pairing window when there are existing customers in Splynx as well as in QuickBooks. Notice what the currency is set in QuickBooks add-on configuration, if Quickbooks customer currency is different, there will be synchronization errors for their related data;

In addition, there is a "Load QuickBooks customers for manual pairing" button. This feature pulls the customer list from QuickBooks into Splynx and allows the admin to manually pair the customers without having to create them in either platform again. Firstly, load customers and then, perform manual pairing.

![Entry point 1](31u.png)

![Entry point 1](32.png)

**Tools** - this menu is used for resetting the accounting database, all items that were selected previously in `Accounting categories`, `Accounting bank accounts` and `Accounting tax rates` will be erased. It is mainly used when the organization changes. Before changing the organization, the accounting database must be reset:

![quickbooks tools](quickbooks_tools.png)

**Module Config** - the link is used to open the QuickBooks add-on configuration page (`Config → Integration → Modules list → QuickBooks Accounting`).
