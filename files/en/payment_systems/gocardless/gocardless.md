GoCardless
==========
Gocardless is a Splynx add-on which allows customers to pay for invoices via the payment gateway - https://gocardless.com/.

Customers using *Gogardless* platform  can pay for invoices through banks or you can charge your customers bank accounts by debit orders.

### Add-on installation

The add-on can be installed in two methods, via the CLI or Web UI of your Splynx server

To install the Gocardless add-on via CLI, the following commands can be used:

```
apt-get update
apt-get install splynx-gocardless-rb
```

To install it via the Web UI:

Navigate to `Config → Integrattions → Add-ons`:

![0.png](0.png)

Locate or search for the `splynx-gocardless-rb` add-on and click on the *Install* icon in the *Actions* column:

![1.png](1.png)

Click on the **OK, confirm** button to begin the installation process:

![1.png](1.1.png)

### Add-on settings

Once the installation process has completed, we can proceed to configuration the add-on in `Config → Integrations → GoCardless`:

![2.png](2.png)

Please enter your **Splynx URL** in the provided field and click on the **Link Splynx with GoCardless button**. You will be redirected to the *GoCardless* registration page:

![3.png](3.png)

![4.png](4.png)

Enter your registration data in the registration form and click on the **Connect account** button.

![5.png](5.png)

If everything is correct, you will be redirected to finish-page:

![6.png](6.png)

After that, the customer should enter the registration details in the provided fields, navigate to `Finance → Gocardless` and click on `Confirm and allow future charge` link.

![6.1.png](6.1.png)

![9.png](9.png)

![10.png](10.png)

![10.png](10.1.png)

Other *Gocardless* add-on parameters are located in `Config → Integrations → Modules list`,

![](config1.png)

locate or search for the `splynx_go_cardless_rb_addon` add-on module and click on the
<icon class="image-icon">![edit](edit.png)</icon> (*Edit*) icon in the *Actions* column:

![](config2.png)

![](config3.png)

![](config4.png)

![](config5.png)

### Invoice payment

Once the configuration has been completed, customers can pay their invoices on the [Portal](customer_portal/customer_portal.md) using the *Gocardless* system in `Finance → Invoices`:

![8.png](8.png)

or directly from *Portal Dashboard* via *Gocardless* widget (entry point):

![7.png](7.png)

The configuration of add-on **Entry points** can be found in `Config → Integrations → Modules list`, near the `splynx_go_cardless_rb_addon` module item in *Actions* column, click on the <icon class="image-icon">![](entry_point.png)</icon> (*Edit entry points*) icon. More information about *Modules list* can be found [here](configuration/integrations/modules_list/modules_list.md).

![12.png](12.png)

![13.png](13.png)

If everything goes well, you will see the status of the invoice marked as `Paid` (on the customer and admin portal).

After a period of time, which can be view on the following page: https://gocardless.com/direct-debit/timings/, we can see the payment in the customer and admin-portal, as depicted below:

![14.png](14.png)

![15.png](15.png)

Customers can also refill their balances using the following link - `https://<splynx_domain_address>/gocardless-rb`:

![16.png](16.png)

Additionally, you can charge all customers using one button, navigate to `Finance → Invoices`, set the period and click on **Charge** button as depicted below:

![](18.0.png)

![](18.png)

### Export customers

To **sync all customers from Splynx to GoCardless**, follow the steps below:

Navigate to `Config → Integrations → GoCardless` :

![](18.1.png)

Select the [Payment method](configuration/finance/payment_methods/payment_methods.md) and [Partner](administration/main/partners/partners.md), then click on the **Export** button:

![](19.png)

You will receive your customers list as a csv-file. Then, you can open your *GoCardless* dashboard on https://gocardless.com/ and upload the csv-file, as depicted below:

![20.jpg](20.jpg)

![21.jpg](21.jpg)

All customers from the list will receive emails to authorize the action:

![23.jpg](23.jpg)

![22.jpg](22.jpg)

![25.jpg](25.jpg)

![26.jpg](26.jpg)

![27.jpg](27.jpg)

### Direct payments

Using the payments links is the simplest way to accept payments from customers. This feature is available in the *Gocardless* add-on to pay *Invoices* and *Proforma Invoices*. This provides convenience and simplicity for your customers, so the amount of on-time payments will increase. For example, you can add a payment link to the e-mail with the (proforma) invoice, as a result, the customer can make payment quickly by clicking onto such link instead of logging in to their *Portal* page. In case the customer has saved the payment credentials on the *Portal*, they do not need to add further details when using the direct payment link in the future. If the credit card in not linked on the *Portal*, the payment details need to be entered each time the payment link is used.

To create a direct payment link, please use the patterns below:

**To pay the Invoice:**

<details>
<summary>by invoice ID</summary>
<div markdown="1">

```
https://<splynx_domain_address>/gocardless/direct-pay-invoice-by-id?item_id=<Invoice_id>

```
</div>
</details>

<details>
<summary>by invoice number</summary>
<div markdown="1">

```
https://<splynx_domain_address>/gocardless/direct-pay-invoice?item_id=<Invoice_number>

```
</div>
</details>



**To pay the Proforma Invoice:**

<details>
<summary>by proforma invoice ID</summary>
<div markdown="1">

```
https://<splynx_domain_address>/gocardless/direct-pay-proforma-by-id?item_id=<proforma_id>

```
</div>
</details>

<details>
<summary>by proforma invoice number</summary>
<div markdown="1">

```
https://<splynx_domain_address>/gocardless/direct-pay-proforma?item_id=<proforma_number>

```
</div>
</details>
