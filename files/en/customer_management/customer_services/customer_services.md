Customer services
==========
The customer service tab is where all products/services supplied to that specific customer can be found, edited or new services can be added to the customers account. This is where you control all services for a client which will influence the bill they receive.

It is possible to associate different services for each customer: `Internet services`, `Voice services` and `Custom services`.
In order **to add a new service** for the customer, select the *Customer view*, go to the services tab and click `Add service` or on the `+` sign above the service table on the left. Please note that customers have to be active on the system to make us of their services, as well as to be able to add services to their profile.

![Service table](service_table.png)

After clicking the "add service" or "+" button, a window will pop up for you to select a service from the list of existing tariffs.

![Create service 1](create_service.png)

![Create service 2](create_service2.png)

* **Plan** - the tariff selected/list of tariffs available to select (`Internet`, `Voice`, `Custom`)
* **Description** - a description of the tariff (optional)
* **Quantity** - the multiple of plans for the selected service
* **Unit** - a unit of measurement (if using for invoices - for example: m, ft, etc.) (Optional)
* **Price** - the price of the tariff (custom prices can be set that differs from service price in the tariff configuration)
* **Pay period** - period of which to charge for this service
* **Start date** - when the system will start accounting for the service in billing perspective.
* **End date** - when the service will end, changed to a stopped status and the system will stop accounting for it in a billing perspective.
* **Discount** - sets a discount with parameters of a percentage, within start and end dates of the discount, please note that these dates refer to the period of which the discount will be applied.
* **Status** - the options are `Active`, `Disabled`, `Stopped`, `Pending`, `Archived`.
  * **Active** - service is active and ready for use.
  * **Disabled** - used when assuming that customer will no longer use the service,  end date has to be reached or configured for the system to stopped accounting for it in a billing perspective. This will be applied to existing services of customers marked as inactive
  * **Stopped** - Used to temporary disable the service. Will be set automatically  to the new service generated when a client is marked as Inactive, when the customer is activated, the service status will  automatically change to Active with the start date of the day of activation.
  * **Pending** - Status of the new service during the waiting period of a planned service change. Between the end date of the old service and the start date of the new.
  * **Archived** - status for services archived for future reference.

  <icon class="image-icon">![Info](information.png)</icon> **The relation between customer, service and invoice and service accounting:**


  1. If the customer has an `unpaid` recurring invoice (e.g. an invoice was created in `Billing day` date at 22:00 PM) and the customer doesn't pay the invoice before the date of `Payment due (days after billing day)`, the customer status will be changed to `Blocked`, but **their service (e.g. Internet service) is still active and accounted by billing**. If the customer has only the **one-time invoice** and it's not paid before `Payment due`, the `Blocked` status won't be applied to the customer, the one-time invoice will have `unpaid` status. The customer won't be `Disabled` after `Deactivation period` has passed as well;

  2. The recurring invoice status in period from `Billing day` to `Payment due` date is `unpaid`, from `Payment due` to `Deactivation period` and after `Deactivation period` the invoice will be considered  as `overdue`;

  3. If the customer with `Blocked` status pays the `overdue` invoice, the customer's status will be changed to `Active`;

  4. If the customer with `Blocked` status doesn't pay the invoice before the date of `Deactivation period` date, his status will be changed to `Inactive (doesn't use service)`. And after he decides to pay the invoice, the status will be changed to `Active`;

  5. If the customer has `Inactive (doesn't use service)` status, his service (e.g. Internet service) will be `disabled` (with `Start date` = `Billing day` date and `End date` = `Deactivation period` date) and the duplicate of the previous service will be created with `Stopped` status, its `Start date` = the date of `Deactivation period`.
  And after customer decides to pay the `overdue` invoice, the status of duplicate service will be changed to `Active`and its `Start date` will be changed to invoice payment date.

  ![](clar_img1.png)

  ![](clar_img2.png)

  6. Mind that the service (-s) with `Disable` status but **without** `End date` **is still accounted by billing**. If you want to **disable the charge for such service (-s) in the next month**, please set `End date` to service or change its status to `Archived` manually. Also, pay attention that the disabled customer service will be charged up for the whole month e.g. the disabled service `Start date` = 2022-01-01, the `End date` = 2022-01-25 (`Billing due` (value: 15 days) and `Deactivation period` (value: 10 days), as a result the disabled service is charged up to 2022-01-31)


------------

**Plan settings**

* **Router** - The router that API will use to connect to (for all API functions - Shaping, contention, address lists)

  <icon class="image-icon">![Warning](warning.png)</icon> This is only required when using API authentication methods in [Networking settings](networking\routers_settings\routers_settings.md)


* **Login** - the username used in services such as PPPoE or Hotspot. Login must be unique in active services.

* **Password** - the password for the login used in services

  <icon class="image-icon">![Warning](warning.png)</icon> If you don't create a password the password from the Main Information page will be used.

* **IPv4 assignment method** - the options are None (Router will assign IP), Permanent IP, Dynamic IP. (Make sure the IP's network is the same type of assignment when creating it in IPv4 manager)

* **IPv4** - IP address which will be assigned to customer's device. Available only when using **IPv4 assignment method**=Permanent IP.

* **Additional network** - this is the customer's network. Network route to this network will be added on the provider's router (NAS). Available only when **IPv4 assignment method**=Permanent IP.

* **IPv4 Pool** - the options are Any pool or a specific pool from the list of pools. Available only when **IPv4 assignment method**=Dynamic IP.

* **Mac(s)** - MAC address(es) of client device(s). Separated by comma.

  <icon class="image-icon">![Information](information.png)</icon> Only the first MAC address will be used if the **Authorization/Accounting** method for the router is set to **Hotspot (Users) / API Accounting** or **PPP (Secrets) / API Accounting**

* **Port ID** - the port ID


You can **edit** a service, **schedule a future change**, **change** the plan, view the **graph** for the service, apply **additional discounts**, **delete** or **geolocate** the service by these icons <icon class="image-icon">![Services actions](services_actions.png)</icon>, located in the actions column of the service table.

![Actions table](actions_table.png)


------------

**Change Plan from Administrator Portal**

The following steps will show how an administrator in Splynx can change customer service in correct way.

**NOTE:** It's required to have more than one `Internet/Voice/Recurring` tariff plan in Splynx in order to change from one to another.

For example, a customer uses `Ethernet_500Mbps` as his current Internet service and wants to change it to `Ethernet_100Mbps` (is created in `Tariff plans → Internet`). The `Ethernet_500Mbps` service had been already charged and customer had paid the invoice (period: (2022-01-01 - 2022-01-31)). The `Ethernet_500Mbps` service start date is 2022-01-01. The new `Ethernet_100Mbps` service should be started on 2022-01-20 according to customer request.

![image](change_service_0.png)


1. Find the necessary customer and go to `Services` tab of their profile. There is an active service that the customer uses at the moment.

2. Click on <icon class="image-icon">![icon](change_plan_icon.png)</icon> (Change plan) icon in *Actions* column of the required service:

![image](change_service_1.png)

3. In the new window, choose `New plan start date` (2022-01-20) and `New plan` (`Ethernet_100Mbps`) for customer and press **Apply** button:

**NOTE:** If the option `Refund unused money` is not used for recurring billing in `Config → Finance → Change plan`, you can change the tariff only after 2022-01-31.

More info about available settings you can find in [Change plan](configuration/finance/change_plan/change_plan.md) guide.

In our case we use the next settings:

* **Plan change refund:** `Refund unused money`;

* **Additional fee when changing to a less expensive plan:** `Additional fee when changing to a less expensive plan` (value: 30);

* **Create invoice after service change:** `Immediately till end of active month`.


![image](change_service_2.png)

4. As a result, the end date (2022-01-19) is added to `Ethernet_500Mbps` service and the new service `Ethernet_100Mbps` is appeared in the list with pending status, its start date is 2022-01-20. On customer balance we can see 8.71$ that were refunded:

![image](change_service_3.png)

![image](change_service_4.png)

![image](change_service_5.png)

<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>How it was calculated</b></summary>
<div markdown="1">

```
200$/31days = 6.4516$/day
19days*6.4516$/= 122.5804$
200$ - 122.5804 = 77.4196$
77.4196$ - 30$ (fee) = 47.4196$ ~ 47.42$

100$/31days = 3.2258$/day
3.2258$ * 12days (from 20 to 31 of January 2022) = 38.7096$ ~ 38.71$

47.42$ - 38.71$ = 8.71$

```
</div>
</details>

5. On January 20, the new service `Ethernet_100Mbps` will be activated and the previous one - `Ethernet_500Mbps` will be disabled:

![image](change_service_6.png)


<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>Another example</b></summary>
<div markdown="1">

<!-- task SPL-7321 -->

In case a customer decides to change their previous service (`Ethernet_100Mbps`, price R100) on the same day of its activation (e.g. the option `Use the customer creation date` as billing day is enabled in `Config → Finance → Settings`. The customer was created on Jan 12 (Billing day), the service start date is also 2022-01-12. And the customer was charged for `Ethernet_100Mbps` service on Jan 12 as well) to a new one (`Ethernet_500Mbps`, price R200), the previous service will be archived and new one will be activated on the same day.

![image](example_1.png)

![image](example_2.png)


</div>
</details>


Suggested read: [Change Plan from Customer Portal](customer_portal/change_plan_from_customer_portal/change_plan_from_customer_portal.md)
