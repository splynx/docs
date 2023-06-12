Windcave (formerly Payment Express)
==============

Windcave (formerly Payment Express) is a Splynx add-on which allows refilling of customer balance and paying invoices via the payment gateway - https://www.windcave.com/.

The add-on can work with different credit cards, if cards are saved on customer profiles, the add-on allows you to charge all customers using *Direct debit orders*.


### Add-on installation


The add-on can be installed in two methods, via the **CLI** or **Web UI** of your Splynx server.

To install the *Payment Express* add-on via **CLI**, the following commands can be used:

```
apt-get update
apt-get install splynx-paymentexpress
```
To install it via the **Web UI**:

Navigate to `Config → Integrations → Add-ons`:

![(image)](0.png)

Locate or search for the `splynx-paymentexpress` add-on and click the *Install* icon in the *Actions* column:

![(image)](1.png)

Click the `OK, confirm` button to begin the installation process:

![(image)](2.png)


### Add-on settings


After the installation process has completed, you have to configure the add-on:

Navigate to `Config → Integrations → Modules list`:

![(image)](3.png)

Locate or search for the `splynx-paymentexpress` add-on and click on the <icon class="image-icon">![edit](edit.png)</icon> (*Edit*) icon in the *Actions* column:

![(image)](4.png)

**Main information and API settings:**

![(image)](5.png)

* **API domain** - api domain should be the same as Splynx URL. The forward slash `/` is required at the end;

* **API key, API secret** - auto generated default values. Don't change it unless it is absolutely necessary.


**Windcave (Payment Express) settings**


![(image)](pe_settings.png)

* **Currency** - select a currency. Windcave supports a number of currencies, which can be used with all interfaces;


**Windcave (Payment Express) PxPay credentials**

Type your PxPay *Payment Express* account credentials in the related fields.

In case in Splynx system is used the multiple [Partners](administration/main/partners/partners.md) scheme, you can divide the *Payment Express* configuration between them. Create a new partner in Splynx, in the *Payment Express* config select the necessary partner and set the required settings.

![(image)](7.png)

<icon class="image-icon">![image](note.png)</icon> The fields marked with `*` sign have the different values from original ones (original values are related to **Default** partner).


**Common settings**

![(image)](8.png)

* **Splynx url** - your Splynx URL address with a slash sign at the end;

* **Payment method ID** - when a customer pays using this add-on, the payment will be allocated as this [payment method](configuration/finance/payment_methods/payment_methods.md);

* **Payment statement grouping** - choose how to group payment statements (`Finance → Payment Statements → History`) monthly or daily.


### Entry points configuration


The configuration of add-on **Entry points** can be found in `Config → Integrations → Modules list`, near the `splynx_addon_paymentexpress` module item in the *Actions* column. Click the <icon class="image-icon">![](entry_point.png)</icon> (*Edit entry points*) icon.

![(image)](9.png)

More information about *Modules list* can be found [here](configuration/integrations/modules_list/modules_list.md).


### Invoice payment


Once the configuration has been completed, customer can add a credit card on the [Portal](customer_portal/customer_portal.md) in `Finance → Credit card via Payment Express`.

<icon class="image-icon">![image](note.png)</icon> An amount of $1 will be debited to authorize the card, which will then be refunded.

![(image)](10.png)

![(image)](11.png)

![(image)](12.png)

Now customer can pay for their invoices using the *Payment Express* system in `Finance → Invoices` on the Portal (the related entry point should be enabled):

![(image)](13.png)

![(image)](14.png)

Moreover, if the payment credentials are added by the customer, the administrator can pay the invoices directly from customer's profile as well:

![(image)](15.png)

If everything goes well, you will see the status of invoice marked as `Paid` (on the customer or admin portal):

![(image)](16.png)

![(image)](17.png)

![(image)](19.png)

On the *Portal Dashboard* page (the related entry points should be enabled), the customer can also see the list of non-paid (proforma) invoice (-s) in *Payment Express* widget (entry point) and the same-name buttons to pay such invoice (-s).

![(image)](20.png)

The customer can refill their balance using the **Add money by Payment Express** menu on *Portal Dashboard* (the `paymentexpress_add_money_on_dashboard` entry point should be enabled).

If the customer is logged into the *Portal*, the following link to refill the balance ``` https://<splynx_domain_address>/paymentexpress ``` is supported as well.

The administrator of Splynx can also top up the customer's balance using the **Pay Now** button on the *Information* tab, for example, of customer's profile (the `paymentexpress_add_money_by_admin` entry point should be enabled).

![(image)](21.png)

Additionally, the administrator can charge all customers using one button, navigate to `Finance → Invoices`, set the period and click on **Charge** button as depicted below:

![(image)](23.png)

The [Charge history](finance/invoices/invoices.md) tab contains the charge history of all charges you have made, sometimes it is very helpful when there are finance issues.

![(image)](24.png)

### Direct payment

Using the payment link is the simplest way to accept payment made with credit card (the **credentials should be entered every time**). This feature is available in the *Windcave* add-on to pay the *Invoices*.

To create a **direct payment link to pay the invoice**, please use the pattern below:

```
https://<splynx_domain_address>/paymentexpress/direct-pay-invoice?item_id=<Invoice_number>

```
