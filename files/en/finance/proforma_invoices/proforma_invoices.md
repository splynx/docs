Proforma invoices
==========

**Pro-forma Invoice** is an abridged or estimated invoice sent by a seller to a buyer in advance of delivery of services/goods. It notes the kind and quantity of services/goods, their value, and other important information. Proforma invoices are commonly used as preliminary invoices with a quotation, or for customs purposes in importation. They differ from a normal invoice in not being a demand or request for payment.

In our billing system Proforma Invoice can be used as a request of payment in advance. For example, it can be created 1 month before the occurring payment, so you will see if customer is able to pay the Proforma Invoice. When proforma invoice is created, the customer’s balance hasn't changed. The main reason for this billing approach is to prevent the payment of VAT tax for non-paying customers. If the customer pays the amount specified in the Proforma Invoice PDF, the company can issue a tax Invoice.

An example of this document is shown in the picture below:
![an example proforma invoice](proforma.png)

---
All issued Proforma invoices can be found in `Finance → Proforma Invoices`.  It is possible to range them by particular period of time or partner.

![proforma invoices list](list.png)


By clicking on a period you can set it up manually, so you can select the option to show all proforma invoices for today, yesterday, last or 30 days, this or last month or just choose a custom range and click on *Apply*.

![Period](period.png)

It is possible to operate with every proforma invoice with icons <icon class="image-icon">![Icons](invoices_icons.png)</icon> in the column *Operations*.

* To be able **to view** the proforma invoice in PDF with icon <icon class="image-icon">![View icon](view_invoice.png)</icon>, it is necessary to configure an invoice template first in `Config → System → Templates` and define template values in `Config → System → Company information`.
More information about Invoice template configuration you can find here - [Templates](configuration/system/templates/templates.md), [Invoices](invoices/invoices.md).

* You can also **set up proforma invoice global settings** for all customers in `Config → Finance → Settings`.

![Proforma invoice settings](proforma_invoice_settings.png)


**To edit** the proforma invoice with <icon class="image-icon">![Edit invoice](edit_invoice.png)</icon> , click on the tab `Billing → Proforma Invoices`.

![Edit](edit_proforma_invoice.png)


It is possible **to send** the proforma invoice via email with <icon class="image-icon">![Send](send_invoiceviamail.png)</icon> (if the email server is [configured](configuration/main_configuration/email_config/email_config.md)).
You can write a message body or choose it from templates and load it.

![Load template](load_template.png)


You can also write here a message body and save it as a template.

![Save template](save_template.png)


---
**To print or export** the list of proforma invoices for accounting purposes, click on `Finance → Invoices` and click on `Export`. You can select here Period of time, Partner, Location, Customer payment type (cash, bank transfer, PayPal, Credit card, refill card etc.), Status (paid\ unpaid), Export type (CSV, PDF file inactive, one PDF file etc.). You can also check an export history here.

![Export](export.png)


It is possible to **enable auto making of proforma invoices** in `Customer's Billing → Billing overview` with choosing particular day, month and type.

![Settings](settings.png)


---
There is a possibility **to create Proforma Invoice manually** by clicking on *Add Proforma Invoice* in `Customer's Billing → Proforma Invoices`.

![Create proforma invoice manually](manually.png)
![View](check.png)
