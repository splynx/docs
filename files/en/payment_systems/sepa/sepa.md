SEPA debit orders
=================

SEPA is a European standard for bank payments. You can install the SEPA add-on and charge your customer via Direct debit orders.

The add-on can be installed in two methods, via the CLI or the Web UI of your Splynx server.

## Installation

To install the SEPA add-on via CLI, the following commands can be used:

```bash
apt-get update
apt-get install splynx-sepa
```

To install it via the Web UI:

Navigate to `Config → Integrations → Add-ons`:

![Addons](0.png)

Locate or search for the "splynx-sepa" add-on and click on the *Install* icon in the *Actions* column. You will be presented with a window to confirm or cancel the installation. Click on the `Ok, confirm` button to begin the installation process:

![111.png](111.png)

After the installation process has completed, you have to configure the add-on.

## Configuration

Navigate to `Config → Integrations → Modules list`:

![Module list](4.png)

Locate or search for the "splynx_sepa_addon" and click on the *Edit* <icon class="image-icon">![image](edit.png)</icon> icon in the *Actions* column. Then fill in the provided fields:

![113.png](113.png)

![image](113_2.png)

![image](113_3.png)

![image](113_4.png)

**Customer’s IBAN** and **Mandate ID** can be set in the customer profile (see below)

![add_iban.png](add_iban.png)
TODO
![add_iban1.png](add_iban1.png)

## Generate the XML file for the bank

Navigate to _Finance/Invoces/_ and click on the _Charge_ button
![charge.png](charge.png)

![116.png](charge1.png)

After clicking "Charge" you will see a download xml document link.

**4\. Mark invoices as paid**

![charge2.png](charge2.png)

Check invoices

![121.png](paid-invoice.png)

**5\. SEPA - process the return file from the bank with non-payers**

Sometimes customers does not have funds on their bank accounts. In that case, the Bank sends you an XML file back with returns. It will contain data about customers which the Bank was not able to charge. You can import this file to Splynx as well, and then paid invoices of non-payers will become unpaid again, so you can charge them next month and include the fee for a failed charge.

The handler to choose is SEPA XML returns:

![SEPA_last.png](SEPA_process.png)

**6\. SEPA - process of the refund from the bank in case of overpaid**

If customers have the overpayments, we can provide the money-back. In order to do this, create for particular customers the invoices with negative price value. The status for such invoices will be set to _Paid (from account balance)_ automatically. After that in `Finance → Invoices` apply the charge with the following options:

![charge3.png](charge3.png)

and download the archive with generated XML file:
![charge4.png](charge4.png)
