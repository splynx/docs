Finance settings
=============

To set global financial settings for new customers or update existing customers go to `Config → Finance → Settings`.

![Main menu](main_menu.png)

It is possible to set here global parameters for the following important parts of financial module:
![Main menu](menu.png)

----
#### Billing settings - Recurring type of billing is set by default in Splynx global configuration.

* **Billing Enabled** -  enable / disable billing for the customer.

* **Period** -  it can be prepaid or postpaid, which means in Prepaid Mode recurring Invoices can be issued up to 5 months in advance and in Postpaid Mode Invoices will be generated after services usage.

  ![Period](period.png)

* **Payment Method** - choose a Payment Method for recurring payment, such as Cash, Bank Transfer, Credit Card, PayPal, Refill Card, BrainTree and others.

  ![Payment method](payment_method.png)

* **Billing day** - when the customer will be charged. It is a day of Invoice generating.

* **Billing due** - the last day when customer have to make a payment before get blocked. For example, we choose 1st day of the month as a billing day and 15th day of the month as Billing due day, which means that Invoice will be generated on 1st day of the month and if customer don't make a payment until 15th day of the month, the next day he will be in blocked status. Even though customer will have blocked status, his services will be still accounted.

* **Grace Period** - when the customer's services will be disabled: time when customer will have inactive status. For e.g. it could be 10 days, which means after 10th day customer's status will be automatically changed from blocked to inactive and his services won't be accounting.

  ![Billing settings](billing.png)

* **Minimal balance** - defines the customer balance in Recurring payment and is set by default to "0" in Global configuration, but it is possible to change here according your needs.

* **Work with** - you can choose from two options: work with balance or customer's deposit.


#### Invoices settings

![Invoices](invoices.png)

* **Create Invoices** (after *To charge*) - with this option enabled **Invoices will be issued automatically** after charging the customer.

* **Auto pay Invoices from deposit** - you can enable this option if customers' payments are regularly made from their deposit.

* **Invoice number pattern** - you can set up an Invoice number pattern here.

* **Invoice cache** - with option enabled all changes made will be visible only in new invoices, old Invoices will remain without changes.



#### Proforma Invoice settings

Settings for auto generating Proforma Invoices. In our billing system Proforma Invoice can be used as a request of payment in advance. For example, it can be created 1 month before the occuring payment, so you will see if customer is able to pay the Proforma Invoice. When proforma invoice is created, the customer’s balance hasn't changed. The main reason for this billing approach is to prevent the payment of VAT tax for non-paying customers. If the customer pays the amount specified in the Proforma Invoice PDF, the company can issue a tax Invoice.

![Proforma](proforma.png)

* **Enable Auto Proforma Invoices** - with this option enabled Proforma Invoices will be issued automatically
* **Day of generating Auto Proforma Invoices** - choose the day for automatic issuing Proforma Invoices
* **Type** - choose for how many months in advance Proforma Invoice will be generated.  
* **Create Proforma Invoices for** - there are 2 options here: create pro forma invoice for current month and for the next month.
* **Proforma Invoice number pattern** - create a Proforma Invoice number pattern here.


#### Receipt settings

![Receipt settings](receipt.png)

* **Receipt number pattern** - create a payment receipt number pattern here.

* **Add to Phrasebook**
    * No wordlists for English -> Russian...
    * Create a new wordlist...

* **Copy**
