Automation
=============

To eliminate financial errors and delays caused by manual processes, in Splynx, you can configure finance automation in `Config → Finance → Automation`.

<icon class="image-icon">![image](warning.png)</icon> **These settings are global and affect all customers**.

![Menu](icon.png)

The following parameters can be configured on this page:

### Finance Automation

![image](finance_automation.png)
![image](finance_automation2.png)

* **Enable automatic issuing** - enables/disables automatic issuing of Invoices, Transactions and Proforma Invoices;

* **Confirmation period (days)** - set the time in days for automatic confirmation of invoices/invoice batches to execute their automatic issuing. If you don't confirm the generated invoices during the confirmation period (by default `3` days), the **invoices will be auto-generated the next day at 10:00 pm**. The values for choosing the confirmation days are: `0`, `3`, `5`, `10`, `15`, `20`, `25`, `30`, and `last day of the month`.

**Example**

If the billing day is the first day of the month and you use the default 3 days as your confirmation period, the invoices which are not manually confirmed will be auto-generated on the 4th day of the month at 10:00 pm.

* **Run preview before billing day (amount of days prior)** - (<icon class="image-icon">![image](warning.png)</icon> to start using this feature, be sure that `Allow confirming a preview in the future` option is enabled) set the time in days to allow the finance preview generation before the billing day (by default `0` days).

**Example**

The billing day is the 6th, the confirmation period is 3 days and the preview should be generated 5 days before billing day. So, using the `5` days value, the preview will be generated on the 1st day and the invoices which are not confirmed will be auto-generated on the 4th day.

* **Date to use on finance elements** - choose which date will be used as actual one on the invoice and transactions. The available values: `billing day` or `real date of issuing`.

**Example**

The billing day is on 1st day of the month and you have set 3 days as a confirmation period. In this case, the invoice will be dated according to the billing day regardless of confirmation days or the real date of issuing - maximum on the 4th day of the month (if you don't confirm the preview, invoices will be auto-generated the next day);

* **Dashboard notification** - enable/disable the notification on the Dashboard about the confirmation of invoices on the day of billing;

* **Allow confirming a preview in the future** - enables/disables the ability to confirm a preview of invoices for upcoming months/future dated months (`Finance → History & Preview`);

* **Block customers on weekends** - enables/disables the processing of `Billing Due` and `Deactivation period` on weekends;

* **Block customers on holidays** - enables/disables the processing of `Billing Due` and `Deactivation period` on holidays. Navigate to `Config → Main → Localization` to set up the holiday list;

* **Generate separate preview per partner** - preview will be generated separately for each partner;

* **Show previously generated preview version** - if the toggle is enabled, an existing preview will be shown; if the toggle is disabled, a new preview will start to be created while the recurring invoice is being generated.


### Automatic blocking

![image](automatic_blocking.png)

* **Enable processing of Billing Due** - enable/disable blocking on the `Blocking period` date if the customer balance is less than the minimum balance;

* **Blocking time** - the time of day that customers are eligible for blocking;

* **Enable processing of Deactivation period** - enable/disable the setting of recurring customers to an **inactive** status on the the `Deactivation period` date if their balance is less than the minimum balance;

* **Enable processing of Deactivation period for prepaid customers** - set the prepaid customers' services as **stopped** status when the `Deactivation period` date is reached;

* **Block customers by One-time invoices** - process blocking of customers by one-time invoices (if the customer failed to pay their one-time invoice by the blocking period date).


### Automatically remove IPs for inactive prepaid customers

![image](auto_remove_ip_prepaid.png)

If a service is disabled and the customer is not active but the service has a static IP address configured, we can automatically clear the IP address of this service to make this IP available in the pool again.

* **Enable removing IPs for disabled services** - enables/disables auto removing the IP addresses for disabled services;

* **Period (months)** - if a service is disabled for more than the specified period in months (by default `12`), the service will be archived and its IP address and login will be freed up. The available values are from `1` to `24`.


### Automation reminders

![image](automation_reminders.png)

* **Static days** - days for sending reminders. They can be set up individually for each customer's profile. If this toggle is enabled, the '*Reminder # 1/2/3 days*' values will be replaced with the default ones where Reminder #1 = 3 days; Reminder #2 = 5 days; Reminder #3 = 7 days. The default values will also be set in the [reminder settings](configuration/finance/reminders/reminders.md) for all customers in the system;

* **Processing Reminder #1** - with this toggle enabled, Reminder #1 will be sent to the customer according to the days set in their Billing Config;

* **Processing Reminder #1** - with this toggle enabled, Reminder #1 will be sent to the customer according to the days set in their Billing Config;

* **Processing Reminder #1** - with this toggle enabled, Reminder #1 will be sent to the customer according to the days set in their Billing Config.

