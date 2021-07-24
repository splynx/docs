Recurring plans
============

Here are all the plans you specifically design to cater to the needs of your company and the services you render uniquely.

For example, certain ISP's provide public IP services to users; Rental of equipment; Hosting or IPTV services are examples of recurring tariff plans.

To create recurring plans navigate to _Tariff plans → Recurring_ and click on Add plan in the top right of the page.

![add_plan](add_plan.png)

You will be redirected to the add plan page and where you will enter the details of the plan in the provided fields.

![create_plan](add_plan_1.png)

* **Title** - the name of the tariff in the list/table of recurring tariffs;
* **Enabled** - enable/disable this plan (when disabled - you won't be able to create new services);
* **Service name** - the description of the plan;
* **Price** - the price for the service;
* **Partners** - the partners this plan will be available to;
* **VAT Included** - whether VAT is included in the price of the plan or not;
* **VAT** - the percentage of the VAT;
* **Tariff plans to change available in customer portal** - the list of other tariffs available for changing from the current tariff in the customer's portal;
* **Types of billing** - the types of billing the plan will be available to;
* **Prepaid (custom) period** - by default, it is set to monthly and customers will be charged for a period of a month, but it is possible to select "Days amount" which will cause another field to appear:" _Custom period (days)_" - this will allow you to set a custom period in days. (7 days (week), 10 days, etc up to 365 days);
* **Available in self-registration** - enables/disables the availability of the tariff when customers sign up for services via the social/self-registration addon.

![prepaid_custom.png](days_amount.png)

Once recurring plans has been created, it is possible to edit or to delete them with the icons found in the actions column of the table.

![list](table_view.png)

Like all tables in Splynx, you can modify the appearance of content, content to display and export the table into Excel, CSV or PDF formats, you can also choose to copy or print the table. This is done with the use of icons found at the bottom left of each table.

It is also possible to view a statistical graph of traffic for this plan with the use of the graph in the *Actions* column, this button will present you with the following window:

![graph](graph.png)

The graph can be filtered to display statistical data by Hour, day, week, month or year:

The Change plan icon can be used to change the plan in a mass action for all customers subscribed to this plan. Please follow the link below for more information:<br>
[Tariff Change](configuring_tariff_plans/tariff_change/tariff_change.md)

After creating a recurring plan, you can now assign it as a service to a customer. To assign a service to a customer, navigate to _Customers → List_, select the specific customer, navigate to their _Services_ tab and simply click on the *Add service* button located at the top left of the page.

![add_service.png](add_service_1.png)

A window will appear to create the service, where you will select a plan from the drop-down list and specify the data in the fields provided for the service.

![add_service_2](add_service_2.png)

Once you have completed the service data form and added it, it will appear in the service table of the customer.

![static_ip.png](service_list.png)

Another option you should pay attention to is update of the name and price for a plan. Sometimes ISP's need to increase/decrease price for plans and in Splynx you can do it in few clicks using *Edit* button under tariff plan:

![edit_plan](edit_plan.png)

To change *Service name* for new services you should update this field and do not enable option *Update description in existing services* as this will update all the services of this plan.

The same with price, if you need to update price for all services just specify new price, enable option "Update price in existing services" and these changes will be applied from next month.
