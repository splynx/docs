Inboxes
=============
Here you can find settings of inboxes(incoming email). When customer will send message to email address of one of inboxes - ticket will be created in Splynx.
This feature was developed for faster contact with Splynx support by sending email message to support email address instead of login to Splynx customer portal and create a ticket.

![icon](icon.png)

## INCOMING INBOXES

![Inboxes](mailboxes.png)

Here new inboxes can be added, removed or changed. Let's create a new one, click on "+":

![add inbox](add_inbox.png)

I'm going to create a new inbox using gmail email address. IMAP details for gmail can be found here: https://support.google.com/mail/answer/7126229?hl=en

When all credentials added, click on "Test connection" to run test and ensure that inbox is connected to gmail account.

Under IMAP settings can be configured next parameters:
  * **Which messages to process:** "All" or "Unread";

  * **Process from date/time** - here you should specify date for start email processing. Fox example here will be date 2020-01-01 00:00:00, all emails from this date Splynx will try to process and create a tickets from all these emails;

  * **Mark as read** - mark email what was processed successfully as read in inbox;

  * **Use address from header** - "From", "Reply to" or "Sender" - means use address from one of this available fields.

Under "Ticket Creating" settings can be configured next parameters:
  * **Receive unregistered emails** - means if this option enabled, tickets will be created from all emails, even if email address isn't in Splynx. If disabled, only customers with email address can create a ticket from inbox;

  * **Priority** - select priority for ticket;

  * **Group** - select group for ticket;

  * **Type** - select type for ticket;

And the last option under "Other" config, "Enabled" - enable or disable creating tickets from this inbox.

I added few more inboxes for finance questions and for general support questions.
So if customer will send a message to a finance@myisp.com will be created ticket type = accounts and will be assigned to ticket group "Finance", and if message will be send to support@myisp.com ticket will be created with type = Support and will be assigned to group "IT". Inbox with ID #1 is disabled and I'm not using it in my system.

![few inboxes](few_inboxes.png)

## COMMON

![Common](common.png)

**Regex for find ticket** - value what should be default, if change is needed better to contact Splynx support;

**Save format** - for now only one option is available "Purify HTML";

**Process forwarded emails from admins** - create tickets from admins emails;

**Enabled** - global enable/disabled option. Even if 5 inboxes with status "Enabled" but this option disabled, tickets won't be created.


## BLACKLIST

![blacklist](blacklist.png)

Here some email addresses can be added to ignore them. Tickets from emails from this list won't be created.
