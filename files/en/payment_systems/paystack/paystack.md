Paystack
=========

Paystack is a Splynx add-on which allows customers to pay for invoices via the payment gateway - https://paystack.com/.

The add-on can work with different credit cards and bank accounts, if cards or bank accounts are saved in customer profiles, the add-on allows you to charge all customers using *Direct debit orders*.

### Add-on installation

The add-on can be installed in two methods, via the CLI or the Web UI of your Splynx server.

To install the Paystack add-on via CLI, the following commands can be used:

```
apt-get update
apt-get install splynx-paystack
```

To install it via the Web UI:

Navigate to `Config → Integrations → Add-ons`:

![(image)](0.png)

Locate or search for the `splynx-paystack` add-on and click on the *Install* icon in the *Actions* column:

![(image)](1.png)

Click on the **OK, confirm** button to begin the installation process:

![(image)](2.png)

### Add-on settings

After the installation process has completed, you have to configure the parameters in `Config → Integrations → Modules list`. As depicted below:

![(image)](3.png)

Locate or search for the `splynx-paystack` add-on module and click on the
<icon class="image-icon">![edit](edit.png)</icon> (*Edit*) icon in the *Actions* column:

![(image)](4.png)

![(image)](5.1.png)

**Public** and **secret** keys can be obtained from your *Paystack account:*

![(image)](14.png)


### Invoice payment

Once the configuration has been completed, customers can pay their invoices on the [Portal](customer_portal/customer_portal.md) using the *Paystack* system in `Finance → Invoices`:

![(image)](7.png)

or directly from *Portal Dashboard* via *Paystack* widget (entry point):

![(image)](7.1.png)

The configuration of add-on **Entry points** can be found in `Config → Integrations → Modules list`, near the `splynx_paystack_addon` module item in *Actions* column, click on the <icon class="image-icon">![](entry_point.png)</icon> (*Edit entry points*) icon. More information about *Modules list* can be found [here](configuration/integrations/modules_list/modules_list.md).

![(image)](8.png)

![(image)](9.png)

![(image)](10.1.png)

If everything goes well, you will see the status of the invoice marked as `Paid` (on the customer and admin portal):

![(image)](11.png)

Additionally, you can charge all customers using one button, navigate to `Finance → Invoices`, set the period and click on **Charge** button as depicted below:

![(image)](12.png)

![(image)](13.png)

### Add-on log files

*Paystack* add-on logs can be found in `Administration → Logs`:

![(image)](paystack_logs.png)

In *Paystack Logs* the different records can be viewed, like when a verification was performed or when a transaction was processed, etc.

![(image)](paystack_logs1.png)

### Direct payments

Using the payments links is the simplest way to accept payments made with credit card or bank account. This feature is available in the *Paystack* add-on to pay *Invoices* and *Proforma Invoices*. This provides convenience and simplicity for your customers, so the amount of on-time payments will increase. For example, you can add a payment link to the email with the (proforma) invoice, as a result, the customer can make payment quickly by clicking onto such link instead of logging in to their *Portal* page. In case the customer has saved the payment credentials on the *Portal*, they do not need to add further details when using the direct payment link in the future. If the credit card in not linked on the *Portal*, the payment details need to be entered each time the payment link is used.

To create a direct payment link, please use the patterns below:

**To pay the Invoice:**

<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>by invoice ID</b></summary>
<div markdown="1">

```
https://<splynx_domain_address>/paystack/direct-pay-invoice-by-id?item_id=<Invoice_id>

```
</div>
</details>

<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>by invoice number</b></summary>
<div markdown="1">

```
https://<splynx_domain_address>/paystack/direct-pay-invoice?item_id=<Invoice_number>

```
</div>
</details>

<br>

**To pay the Proforma Invoice:**

<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>by proforma invoice ID</b></summary>
<div markdown="1">

```
https://<splynx_domain_address>/paystack/direct-pay-proforma-by-id?item_id=<proforma_id>

```
</div>
</details>

<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>by proforma invoice number</b></summary>
<div markdown="1">

```
https://<splynx_domain_address>/paystack/direct-pay-proforma?item_id=<proforma_number>

```
</div>
</details>
