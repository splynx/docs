Stripe online payments
======================

Stripe is a Splynx add-on. It's used to synchronize customers, invoices and payments with *Stripe payment gateway* - [https://stripe.com](https://stripe.com).

To install Stripe add-on use next commands:


```bash
apt-get update
apt-get install splynx-stripe
```
or you can install it from Web UI:

Config → Integrations → Add-ons:

![Stripe Web install](stripe_web_install.png)

After installation you have to configure params in Config → Modules List → Stripe → Edit:

![Stripe configuration](configuration.png)

You have to Set your Splynx URL, Company Name, Public Key and Secret Key:

![Stripe main settings](main_settings.png)

Then customers have to add a credit card:

![Stripe add card 1](add_card_1.png)

![Stripe add card 2](add_card_2.png)

![Stripe add card 3](add_card_3.png)

Now customers can pay their invoices using [stripe.com](https://stripe.com) system in *Finance / Invoices*:

![Stripe pay invoice 1](pay_invoice_1.png)

![Stripe pay invoice 2](pay_invoice_2.png)

![Stripe pay invoice 3](pay_invoice_3.png)

![Stripe pay invoice 4](pay_invoice_4.png)

If everything went well, you will see status of invoice as *"Paid"* (in portal and in admin):

![Stripe paid invoice 1](paid_invoice_1.png)

![Stripe paid invoice 2](paid_invoice_2.png)

Besides that, you can charge all customers, using one button! Go to *Finance → Invoices*, set the period and click "Charge" as on a screenshot:

![Stripe charge invoices 1](charge_invoices_1.png)

![Stripe charge invoices 2](charge_invoices_2.png)

![Stripe charge invoices 3](charge_invoices_3.png)
