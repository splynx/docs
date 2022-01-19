Integrapay
============

**Integrapay** is a Splynx add-on which allows customers to pay for invoices via the payment gateway - https://www.integrapay.com.au/. Customers using *Integrapay* can pay for their invoices through bank and credit card or you can charge your customers bank accounts by debit orders.

### Add-on installation

The add-on can be installed in two methods, via the CLI or Web UI of you server.

To install the *Splynx-Integrapay* add-on via CLI, the following commands can be used:

```
apt-get update
apt-get install splynx-integrapay
```
To install it via the Web UI:

Navigate to `Config → Integrations → Add-ons`:

![(image)](0.png)

Locate or search for the `splynx-integrapay` add-on and click on the *Install* icon in the *Actions* column, you will be presented with a window to confirm or cancel the installation, click on the **OK, confirm** button to begin the installation process.

![(image)](1.png)

![(image)](1.1.png)

### Add-on settings

The first step is to register an account on https://www.integrapay.com.au/. After registering, *Integrapay* will send you an email with your credentials, where  _**Bussines ID** is your **Username** and  **Api User Key** is your **Password**_ :

![(image)](13.png)

Then, you need to set your **Username**, **Business ID** and **Password** in `IntegraPay API settings` section of add-on config page, navigate to `Config → Integrations → Modules list → Splynx Add-on IntegraPay` and locate or search for the `splynx_addon_integrapay` add-on module and click on the <icon class="image-icon">![edit](edit.png)</icon> (*Edit*) icon in the *Actions* column, enter your credentials in the related fields.

![(image)](2.png)

![(image)](3.png)


**Main information and API settings:**

![(image)](4.png)

* **API domain** - api domain should be the same as Splynx URL. The forward slash `/` is required at the end;

* **API key, API secret** - auto generated default values. Don't change it unless it is absolutely necessary.


**IntegraPay billing settings:**

![(image)](5.png)

* **Ignore Fee** - ignore IntegraPay fee;
* **Fee VAT** - service [fee VAT](configuration/finance/taxes/taxes.md) percent;
* **Add fee to request** - add fee (position) to request;
* **Fee message** - if `Add fee to request` option is enabled, the current message will be added as description for fee item in invoice;
* **Payment method for Credit Card / Bank Account** - when a customer pays using this add-on, the payment will be allocated as this payment type;
* **Transaction fee category** - transaction [category](configuration/finance/transaction_categories/transaction_categories.md) of the fee transactions;
* **Bank statements group** - choose how to group bank statements (`Finance → Bank Statements → History`) monthly or daily;
* **Available Payment Methods** - choose a payment method that the customer can add on Portal. Pay attention, IntegraPay service does not support using two payment methods at the same time. If 'Bank account or Card' option is selected, a customer can add either their bank account or a credit card and use only one method at a time;
* **Mask card's number and CVV** - hide card number and CVV code when adding on the Portal;
* **Customers identifier** - select what to use as identifier of customer on IntegraPay service side;
* **Sending email with terms** - enable/disable the email sending with terms and conditions of the service to customers;
* **Subject of email with terms** - subject of the email with terms and conditions of the service;
* **Message of email with terms** - message of the email with terms and conditions of the service;
* **Top-up for admins** - enable/disable the form to refill customer account balance from their billing configuration page (see the example below).

<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>Example</b></summary>
<div markdown="1">

![(image)](top-up_1.png)

If the payment credentials are not added, the administrator can add it from this form. Pay attention, only one payment method can be used.

![(image)](top-up_2.png)

If the payment credentials are added by customer, e.g. credit card but `Top-up for admins` option is disabled on add-on configuration page, the administrator will see the next message

![(image)](top-up_3.png)

If the option `Top-up for admins` is enabled on add-on configuration page, the administrator can top up the customer's balance, the saved payment method will be used.

![(image)](top-up_4.png)

![(image)](top-up_5.png)

</div>
</details>


<br>


**IntegraPay API settings:**

![(image)](5.1.png)

The configuration of add-on **Entry points** can be found in `Config → Integrations → Modules list`, near the `splynx_addon_integrapay` module item in *Actions* column, click on the <icon class="image-icon">![](entry_point.png)</icon> (*Edit entry points*) icon. More information about *Modules list* can be found [here](configuration/integrations/modules_list/modules_list.md).

### Invoice payment

Before making any payment it's required to set up the bank account or the credit card, depends on what option customers would like to use to pay.

Navigate to `Finance → IntegraPay payment credentials` and type the required credentials.

![(image)](8.png)

![(image)](9.2.png)

![(image)](9.3.png)

Once the configuration has been completed, customers can pay their invoices on [Portal](customer_portal/customer_portal.md),

using the *IntegraPay* entry point in `Finance → Invoices`:

![(image)](6.png)

![(image)](6.1.png)

**IMPORTANT:** the `Service Fee` value cannot be set on add-on config page, as a result, will be shown only `Total to pay` amount.

![(image)](6.2.png)

or pay directly on Portal Dashboard (the related entry points should be enabled):

![(image)](pay_from_dashboard.png)

![(image)](6.3.png)

If everything goes well, you will see the status of the invoice marked as `Paid` (on the customer and admin portal).

![(image)](6.4.png)

Customers can also refill their balances using **Add money via Integrapay** menu on Portal Dashboard.

![(image)](10.png)

![(image)](10.1.png)

Additionally, you can charge all customers using one button, navigate to `Finance → Invoices`, set the period and click on **Charge** button as depicted below:

![(image)](11.png)

![(image)](12.png)

The [Charge history](finance/invoices/invoices.md) tab contains the charge history of all charges you have made, sometimes it is very helpful when there are finance issues.

### Add-on log files

*IntegraPay* add-on logs can be found in `Administration → Logs`:

![(image)](logs.png)

In *Integrapay Logs* the different records can be viewed and its response details etc.

![(image)](logs1.png)

### Direct payments

Using the payments links is the simplest way to accept payments made with credit card or bank account. This feature is available in the *IntegraPay* add-on to pay *Invoices* and *Proforma Invoices*. This provides convenience and simplicity for your customers, so the amount of on-time payments will increase. For example, you can add a payment link to the e-mail with the (proforma) invoice, as a result, the customer can make payment quickly by clicking onto such link instead of logging in to their *Portal* page. In case the customer has saved the payment credentials on the *Portal*, they do not need to add further details when using the direct payment link in the future. If the credit card in not linked on the *Portal*, the payment details need to be entered each time the payment link is used.

To create a direct payment link, please use the patterns below:

**To pay the Invoice:**

<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>by invoice ID</b></summary>
<div markdown="1">

```
https://<splynx_domain_address>/integrapay/direct-pay-invoice-by-id?item_id=<Invoice_id>

```
</div>
</details>

<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>by invoice number</b></summary>
<div markdown="1">

```
https://<splynx_domain_address>/integrapay/direct-pay-invoice?item_id=<Invoice_number>

```
</div>
</details>

<br>

**To pay the Proforma Invoice:**

<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>by proforma invoice ID</b></summary>
<div markdown="1">

```
https://<splynx_domain_address>/integrapay/direct-pay-proforma-by-id?item_id=<proforma_id>

```
</div>
</details>

<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>by proforma invoice number</b></summary>
<div markdown="1">

```
https://<splynx_domain_address>/integrapay/direct-pay-proforma?item_id=<proforma_number>

```
</div>
</details>


<!---     do NOT remove this info block !

### Integration with BPAY

**Pay attention, this feature is not available in the major release of IntegraPay add-on.**

**BPAY** is an electronic bill payment system in Australia which enables payments to be made through online or phone banking service. The customers should be registered as BPAY billers with the BPAY operating company through its bank. Unlike receiving standard bank transfers or credit card payments – all BPAY transactions have a unique CRN (Customer Reference Number) which can be used to identify which customer made the payment and what invoice it is related to.

Splynx uses BPAY service via *IntegraPay* API to pay (proforma) invoices, but **we can only create a reference num. (CRN) for the invoice and the customer**.




<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>How does BPAY work?</b></summary>
<div markdown="1">

1. SIP sends a customer an invoice displaying a BPAY logo, a **unique BPAY Biller Code** and a **Customer Reference Number (CRN)**;

2. A customer logs into their Internet banking and follows the prompts to make a BPAY payment;

3. A customer will be asked to provide the payment details: the **Biller Code**, the **reference number from the invoice/customer (CRN)** and the **amount**** they wish to pay. After that the customer’s bank validates the payment in real-time (the information about payment is transferred to *IntegraPay* via BPAY) with the system issuing a receipt;

![(image)](bpay_example.png)

4. Funds will be deposited into the corporate account.


More information you can find in an official [FAQ](https://bpay.com.au/bpay-for-you/personal-faqs).



</div>
</details>



**Pay the invoice by BPAY according to the created (proforma) invoice CRN in Splynx:**

1. (for administrator) Install and configure the *IntegraPay* add-on in Splynx (see above). Create the invoice for the customer to pay;

2. (for administrator) Double-check if the necessary entry point for (proforma) invoice is enabled: navigate to `Config → Integrations → Modules list → Splynx Add-on IntegraPay` and click on **Edit entry points**

![(image)](entry_point_invoice.png)

![(image)](entry_point_proforma.png)

3. (for customer) Open the [Portal](customer_portal/customer_portal.md), navigate to `Finance → Invoices` (`Finance → Proforma invoices`) and click on `Pay via BPay` icon near the unpaid invoice (the [bank statement](bank_statement_processing/bank_statement_processing.md) will be created in `Pending` status - it will be used to read the status of transaction from *IntegraPay* side. The payment will be created if the customer pays the invoice in their bank and we receive information about this transaction from *IntegraPay*): showing the Customer Reference Number (CRN) of the current invoice indicates that it has been generated successfully and the CRN is fixed in *IntegraPay*.

![(image)](pay_invoice_via_bpay.png)

4. A customer makes payment using the provided Biller Code and Customer Reference Number (CRN). After that, a new transaction associated with CRN will appear in the customer profile.


**Pay the invoice by BPAY according to the created customer CRN in Splynx:**

1. (for administrator) Install and configure the *IntegraPay* add-on in Splynx (see above). Create the invoice for the customer to pay;

2. (for administrator) Double-check if the `BPay CRN` entry point in `Finance` section of customer portal is enabled: navigate to `Config → Integrations → Modules list → Splynx Add-on IntegraPay` and click on **Edit entry points**

3. (for customer) Open the Portal, click on `Finance` item on the sidebar, then click on `BPay CRN` item: the unique CRN for customer will be generated (each customer will have their own unique CRN)

![(image)](bpay_crn_for_customer.png)

4. A customer can pay any amount of money using the provided Biller Code and Customer Reference Number (CRN). Then, Splynx receives the status of the transaction and the money will be added to the customer's balance. Only the payment will be created in the customer profile.


<icon class="image-icon">![image](information.png)</icon> **Things to keep in mind:**

- the change of transaction statuses is performed by API request from Splynx, which is limited to no more than 1 request per hour (the task is executed by *cron*);

- the two methods (for the invoice and the customer) of CRN generation in Splynx can work simultaneously;

- when a customer incorrectly entered the amount of payment for the invoice and the amount is less than the required amount, it simply creates a payment that is not linked to the invoice;

- if a customer later pays the correct amount using the same CRN (of the invoice), the payment should be linked to the correct invoice;

- if the amount of payment is larger than required, then 2 payments will be created in Splynx. The one with the required amount and it will be linked to the invoice, the second one will be added to the customer's balance;

- in case an invoice is paid or deleted before the transaction status is analyzed by Splynx, the information about this event will be added to the log and the transaction will be marked as processed.


**Add the Bpay logo with references to the (proforma) invoice templates**

Navigate to `Config → Templates`, choose `Invoice PDF` or `Proforma Invoice PDF` **type** and near the required template click on the
<icon class="image-icon">![edit](edit.png)</icon> icon in the *Actions* column to edit the template.

<icon class="image-icon">![image](warning.png)</icon> **It's recommended to create a new template instead of changing the default one**.

Add the next line to the *footer* of your template:

![(image)](edit_template.png)

After that, double-check if the correct template is selected in [Company information](configuration/system/company_information/company_information.md), the fields: `Invoice PDF Template` and `Proforma Invoice PDF Template`.

**CRN for the invoice:**




<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>for Invoice PDF template</b></summary>
<div markdown="1">



```   
<img src="https://your_domain/integrapay/get-bpay-crn?invoiceNumber={{ number }}" width="150" height="43">

```


</div>
</details>




<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>for Proforma Invoice PDF template</b></summary>
<div markdown="1">


```   
<img src="https://your_domain/integrapay/get-bpay-crn?invoiceNumber={{ number }}&isProforma=1" width="150" height="43">

```


</div>
</details>

<br>

**CRN for the customer:**



<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>for Invoice PDF template</b></summary>
<div markdown="1">



```   
<img src="http://your_domain/integrapay/get-bpay-crn-customer?customerId={{ customer.id }}" width="150" height="43">

```


</div>
</details>




<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>for Proforma Invoice PDF template</b></summary>
<div markdown="1">


```   
<img src="http://your_domain/integrapay/get-bpay-crn-customer?customerId={{ customer.id }}&isProforma=1" width="150" height="43">

```


</div>
</details>

<br>

Example:

![(image)](logo_in_template.png)


-->
