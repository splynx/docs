Mass sending
==============

The *Mass sending* option in `Messages → Mass sending → Create` allows you to send an email to the customer(s) directly from Splynx using different templates and attaching financial or other documents.

![Main window](./main_window.png)

It is necessary to configure email first in `Config → Main → Email` before sending email to the customer. More information about email configuration can be found in - [Email config](configuration/main_configuration/email_config/email_config.md).

**To create an email** click on *Create* in `Messages → Mass sending`, a window will appear with the following fields:  

* **Recipient** - choose who receives an email: *Customer* or *Lead*

* **Login** - a login can be specified

* **Status** - there are New, Active, Inactive, Blocked statuses of the customer

* **Full name** - full name of the customer/lead

* **Email** - personal email of the customer/lead

* **Billing email** - billing email of the customer/lead

* **Phone number** - phone number of the customer/lead

* **Category** -  could be Private person or Company

* **Location** - location of the customer

* **Type of billing** - Recurring payments, Prepaid (Custom) or All

* **Partner** - partner, service provider of the customer

* **Tariff plans** - all available tariff plans in Internet, Voice, Custom services

* **Service** - Internet service, Voice service, Recurring or Bundle

* **Send to** - the options are: Email, Customer portal, Customer portal & Email, SMS

* **Send to billing email** - the options allows to send the correspondence only to billing mail

* **Subject** - Subject of the email

* **Message** - Body of the message

* **Templates** - Templates of Customer portal, Email, and SMS can be used.

* **Attachments** - individual attachments

* **Attach financial documents** - Invoices, Proforma Invoices and Payments from Splynx.

* **Send message if financial documents exists** - the financial documents will be send only if they are present in customer/lead profiles

It is not necessary to fill all the fields to send an email to the customer or the lead. The easiest way is to enter a customer's login, choose the "Send to" option, type a Subject and write a message itself. You can choose a message body from templates or write particular text to populate the body of the message. You can also type your own message and save it as a new template by clicking on *"Save as new"*. There is also an option to attach financial documents of the customer (invoices, proforma invoices and payments receipts).

![New email](./new_email.png)

You can view your messages before sending it by clicking on the *Preview* button at the bottom of the page.

![Preview](./preview.png)

When you click on the *Send* button, a window will appear with the confirmation details of the recipient.

![Send message](./send_message.png)

If you click on *Send as test* button, a window will appear where the specific email has to be entered.

![Pop-up](./pop_up.png)

There is also an option of mass sending, for example, you can choose particular recipients by Partner or Location.

![Mass sending](./mass_sending.png)

If you choose the sending option as *Send to Customer portal* or *Customer Portal & email*, customers will be able to read the email in their portal in the Messages section, where all incoming emails will be shown.

![Sent to customer](./sent_to_customer.png)

By clicking on the message *Subject*, the email will appear with the attachment enclosed.

![View message](./view_message.png)

It is possible to track all emails that were sent in Splynx by navigating to `Messages → Mass sending → History`. You can sort all items by their status (Any, New, Processing, Sent, Cancelled, Removed, Sent with error) or a period of time (Today, Yesterday, Last 7 days, This month, Last month, Custom Range).

![History](./history.png)

By clicking on the actions buttons <icon class="image-icon">![ViewIcon2](./icon2.png)</icon>, you'll be able to see the list customers' (in case of mass sending it will be a full list with customers' names), view the email or delete it.

![Customer's list](./customers_list.png)

It is also possible to check all recipients list by their IDs and Email addresses in `Administration → Logs → Email`, where you can set a particular period, type of email message or status.

![Recipients](./recipients.png)
