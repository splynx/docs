## Prepaid billing engine

Prepaid billing is used when ISP's charge customers in advance for services and only provide them with access for certain periods of time. When the time period has been reached and the customer's account balances are not sufficient to pay for the continuation of services, the customer is disconnected until payments are made to continue services.

To configure **Prepaid type of billing** we start by changing the _Billing type_ of the customer to "Prepaid (Custom).

![Type of billing](type_of_billing_prepaid.png)


The next step is to choose the *Payment method*, options are Cash, Bank Transfer, Credit Card, Refill Card and others when additional methods are installed.

![Payment method](payment_method_2.png)


Then we define the minimum amount of funds to be available in the customer's account after service charges to avoid being blocked in the *Minimum balance* field, this field is 0.0000 by default.

![Minimal balance](minimal_balance_prepaid.png)

Customers can be charged for monthly or by any custom periods, (for example, one week), with the use of prepaid tariff custom periods.

By default, all prepaid tariffs are set to charge customers monthly.

![Prepaid(custom)](custom_prepaid_1.png)
![Prepaid(custom)](custom_prepaid_2.png)

However, it is possible to set any desirable period. Simply change the Prepaid Period of the service to **Days amount** and select the desired amount of days.

![Prepaid(custom)](custom_prepaid_3.png)

The next step is to set the 'Period' in the customer's billing settings `Customer → Billing → Billing overview`.  Any desired charged period can be set, to suit the unique needs of customers and every ISP.

![Prepaid(custom)](prepaid_period.png)

After configuring the customer's prepaid billing parameters, we need to add a payment to the customer’s account by clicking on the Add payment button in `Customer → Billing → Payment`. For example, 30 USD has been added, to activate their services.

![Payment](payment.png)

After the deposit has been made we then proceed to activate the customer's services by manually charging the customer with the **Charge & Invoice** button.

![Deposit](deposit_charge.png)

After charging the customer 30 USD and the customer is provided with access for one month.

![Deposit](information_prepaid.png)

If the option to Create invoices (*after charge&invoice*) is enabled in finance settings under `Config / Finance / Settings`, Splynx will generate an invoice for consumed services on the first day of the next month.

***Please note that Deactivation period for prepaid customers can be configured in Config / Finance / Settings***:

![Settings](settings.png)
![Settings](settings1.png)

Please remember if you would like your deactivation period to work it is necessary to enable the processing of deactivation period under *Config / Finance / Automation*:

![Automation](automation.png)
