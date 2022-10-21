Rates
=====

Under **_Rate tables_** we associate prices with prefixes and categories. It is divided into `Customers` and `Providers` rates. Customers rates will be configured with sell prices and provider rates with buy prices. To simplify things, we can describe customers rates like "price of a call to number like +9876* is 0.1$ per minute" and providers rates like "we pay for voice provider 0.1$ per minute for call to number like +9876* so later in configs we can add some markup let's say 20% to have a profit".

* Customers rates - define final tariffication for end customers;

* Providers rates - define an initial tariffication.

To configure rates navigate to *Voice → Rate tables → Customers/Providers* and click on `Add` button located at the top right of the table. You need to add a rate table first:

![add rate table](add_rate_table.png)

Here select name of a rate table and define if the tax is included or excluded:

![Add rate table](add_rate_table_1.png)

Once this done, click on the view & configure rates button:

![Rates config](list.png)

Here we can see a lot of buttons to click. On the left you can switch between rates for calls, messages or data and on the right side you can find buttons to add some rate manually (`Add`), `Load rates from another plan` (in case you have another rate table you can use it and just copy rates to a current table), `Import` (import a file with rates into this table), `Export` (Export rate table), `Mass update` (apply some massive update for range of rates in the current table):

![buttons](rate_table.png)

Let's add some customers rate:

![Customers rate](add_customer_rate.png)

Here is a description of all available fields:

* **Customer rate table** - predefined rate table;

* **Rate name** - name of this rate;

* **Description** - description of this rate;

* **Category** - category to associate with this prefix;

* **Prefix** - define a pattern to match phone numbers. Use these 2 marked tips to define a prefix correctly. In this case prefix `9876{!}` will match all phone numbers starts with 9876:

![examples](examples.png)

![test_mask](test_mask.png)

* **Price** - Price per minute;

* **First step** - Duration of the first step;

* **Tariffication step** - Duration of the tariffication step;

* **Connect cost** - Price for connecting the call.

### Rates import

If you have tons of rates, you don't have to import them all manually, it can be imported from a **.csv** file in *Config → Tools → Import*.

Select *File*, *Voice type* and *Rate table*:

![import1](import_1.png)


In next step you need to define fields but we recommend to have a file with the next structure to allow Splynx select fields automatically:

![file_structure](file_structure.png)

To set columns manually:

![import2](import_2.png)

Once the columns are set, click on `Submit`:

![import3](import_3.png)

Next, click on "Show preview & confirm" button:

![import4](import_4.png)

If there are no warnings or errors, click on `Confirm import`:

![import5](import_5.png)

The status will be changed to *Imported*:

![import6](import_6.png)
*********************************************

### Rates mass update

It is possible to update a specific range or all the rates:

![Update rates](update_button.png)

![Update rates](update_rate.png)

* **IDs for update** - select the IDs you want to update;

* **Connection costs** - Update the connection cost, by the specified Increase / Decrease , a percentage or a fixed price;

* **Price** - Update the price, by the specified Increase / Decrease , a percentage or a fixed price;

* **First step** - Duration of the first step;

* **Tariffication step** - Duration of the tariffication step.

Now when the rate table is configured, it can be assigned to some [voice plan](voice/tariff_settings/tariff_settings.md).
