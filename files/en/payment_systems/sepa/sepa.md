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

**Customer’s IBAN**, **Mandate ID**, and **BIC number** can be set in the customer profile (see below):

![add_iban.png](add_iban.png)

![add_iban1.png](add_iban1.png)

## Generate the XML file for the bank

Navigate to *Finance → Invoces* and click on the `Charge` button:

![charge.png](charge.png)

<icon class="image-icon">![image](note.png)</icon> Use `splynx-sepa-invoices` to invoice customers and `splynx-sepa-outstanding-balances` to charge customers' balances.

![116.png](charge1.png)

After clicking `Charge` you will see a download xml document link.


![charge2.png](charge2.png)

## Check invoices

![121.png](paid-invoice.png)

## SEPA - process the return file from the bank with non-payers

Sometimes customers does not have funds on their bank accounts. In that case, the Bank sends you an XML file back with returns. It will contain data about customers which the Bank was not able to charge. You can import this file to Splynx as well, and then paid invoices of non-payers will become unpaid again, so you can charge them next month and include the fee for a failed charge.

The handler to choose is SEPA XML (Returns):

![SEPA_last.png](SEPA_process.png)

