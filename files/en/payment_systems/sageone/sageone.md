SageOne
====================

**We have developed an addon for SageOne within Splynx. It’s used for synchronization of accounting actions between SageOne and Splynx**

**The integration is described here: https://www.youtube.com/watch?v=ctuNzm_qWgs**

*SageOne does NOT allow the charging of customers.*

Install the add-on with commands:

```bash
apt update
apt install splynx-sageone
```

or you can install it from Web UI:

**Config → Integrations → Add-ons:**

![install_sageone.png](install_sageone.png)
Click on "Update(apt)" button first and then install SageOne. On this example the add-on already installed.

**For the Splynx-SageOne integration, you need to create a new SageOne account and configure your account accordingly.**

**We recommend to starting with a fresh SageOne account, if you have existing customer data, we will not be able to match customers in SageOne with customers in Splynx.**

Once you have created a new SageOne account navigate to **Config → Integrations → Modules list** and click the "Edit" button on *splynx_addon_sageone_accounting*:

![edit_module.png](edit_module.png)

Enter your account details:

![configuration.png](configuration.png)
Here you have to specify your SageOne account login and password. "Company ID" will be loaded automatically if left empty, however, if you know your Company ID please insert it.

**Configure and map your accounting categories and bank accounts**

For categories-configuration navigate to **Config → Finance → Accounting categories**

![categories.png](configuration2.png)

![categories.png](categories.png)
Click on "Load categories" to sync categories from SageOne to Splynx. On this screenshot, we only have 4 categories. For services, we selected the "internet services" category, and for the rest - the "Extra" category. Don't forget to save the configuration.

Category configuration depends on your SageOne account items. If you have created item for each tariff (1 tariff in Splynx = 1 item in Sage) you would configure the categories as per the guide below:

![step1.png](step1.png)
Item for tariff Fibre 50Mbps - synced.

![step2.png](step2.png)
Next, we need to create a transaction category in Finance→Transaction categories for this item and select the option "same as service or tariff" and save the configuration.

![step2-2.png](step2-2.png)
Enable the option below to access the transaction category option in the specified tariff.

![step3.png](step3.png)
In the internet tariff config, select the transaction category which you created in Finance→Transaction categories.

This way you can map all tariff plans which you have created as items in SageOne.

For **payment synchronization** you must configure bank accounts:

For bank accounts configuration navigate to **Config → Finance → Accounting bank accounts**
![bank_accounts.png](bank_accounts.png)
In this example, we have 2 bank accounts and we will use #2 "Bank Payment" as the default account and specify it for the SageOne payment method.


**Once the add-on is configured we can start working with SageOne.**

Navigate to **Config → Integrations → Splynx Sageone Accounting** and sync your customers to SageOne.
![manual_sync.png](manual_sync.png)

In this example we have 3 customers and by clicking **Export customers to SageOne** we will synchronize our customers to the SageOne account.

![customers_sync.png](manual_customers_sync.png)

You can log in to your SageOne account to ensure that customers were synchronized:
![synced_customers.png](synced_customers.png)

You can also view SageOne synchronization logs in **Administration → Logs → Accounting integrations**:
![customers_sync.png](logs_location.png)
Here you can view statuses of all synchronized customers, payments and invoices.

![log_synced_customers.png](log_synced_customers.png)
As you can see on the *Customers* tab there are 3 entries for 3 synced customers. Every synchronized customer, invoice and payment will have an "Accounting ID". If this value is empty - the item wasn't synchronized with SageOne. In this case, you can run a manual synchronization or wait until the next scheduled synchronization. In this view you can see a warning about transaction categories configuration because it was captured before we mapped the categories in *Config → Finance → Accounting categories*

Once customers are synchronized, we can create an invoice and push it to SageOne.
![sync_invoice.png](sync_unpaid_invoice.png)
As you can see from the screenshot, the invoice was synchronized.

In the logs, you can view all synchronized invoices:
![sync_payments.png](log_synced_invoice.png)

![synced_invoice.png](synced_invoice_on_sageone.png)
In SageOne we can also view this UNPAID invoice.

Once the invoice is PAID, Splynx will import the new payment automatically (bank account must be configured for payments synchronization).
![paid_invoice.png](paid_invoice_on_sageone.png)

Alternatively, you can manually sync payments here:
![sync_payments.png](sync_payments.png)

**NOTE! To mark the invoice status as "paid" we have to enable the following option after payment synchronization - "Allow pay invoices from account balance" must be enabled under the customer’s billing tab.**
![option_to_enable.png](option_to_enable.png)

You can also view logs of synced payments:
![log_sync_payments.png](log_synced_payment.png)

We can also view the invoice status which will now reflect as “Paid”:
![sync_payments.png](customer_paid_invoice.png)

The transaction was also created:
![customer_transaction.png](customer_transaction.png)

As well as the payment:
![customer_payment.png](customer_payment.png)


**Some examples of errors which could occur:**

*Scenario 1*

An invoice was synchronized, deleted in Splynx (for example invoice was incorrect and you have deleted it and create a new one with the same number) and you are attempting to sync invoices to SageOne:

![error_sync_invoice.png](error_sync_invoice.png)

Fix: Remove the invoice from within the SageOne account or if you are unable to remove it from SageOne re-create the invoice in Splynx with a new invoice number.
