Stripe online payments
======================

Stripe is a Splynx add-on  used to synchronize customers, invoices and payments with the *Stripe payment gateway* - [https://stripe.com](https://stripe.com).

The add-on can be installed in two methods, via the CLI or the Web UI of your Splynx server.

To install the Stripe add-on via CLI the following commands can be used:


```bash
apt-get update
apt-get install splynx-stripe
```
To install it via the Web UI:

Navigate to `Config → Integrations → Add-ons`:

![Addons](0.png)

Locate or search for the "splynx-stripe" add-on and click on the install icon in the *Actions* column, you will be presented with a window to confirm or cancel the installation, click on confirm to begin the installation process:

![Stripe Web install](stripe_web_install.png)

After the installation process has completed, you have to configure the parameters in *Config → Modules List*

![Module list](4.png)

Locate or search for the "splynx-stripe" add-on and click on the edit icon in the *Actions* column

![Stripe configuration](configuration.png)

You have to Set your Splynx URL, Company Name, Public Key and Secret Key:

![Stripe main settings](main_settings.png)

Customers the have to add a credit card in the customer portal:

![Stripe add card 1](add_card_1.png)

![Stripe add card 2](add_card_2.png)

![Stripe add card 3](add_card_3.png)

Once the configuration is completed, customers can pay for their invoices using the [stripe.com](https://stripe.com) system in *Finance / Invoices*:

![Stripe pay invoice 1](pay_invoice_1.png)

![Stripe pay invoice 2](pay_invoice_2.png)

![Stripe pay invoice 3](pay_invoice_3.png)

![Stripe pay invoice 4](pay_invoice_4.png)

If everything went well, you will see the status of the invoice marked as *"Paid"* (in the customer and admin portal):

![Stripe paid invoice 1](paid_invoice_1.png)

![Stripe paid invoice 2](paid_invoice_2.png)

Additionally, you can charge all customers using one button! Navigate to *Finance → Invoices*, set the period and click on "Charge" as depicted below:

![Stripe charge invoices 1](charge_invoices_1.png)

![Stripe charge invoices 2](charge_invoices_2.png)

![Stripe charge invoices 3](charge_invoices_3.png)
