Change Plan from Customer Portal
==========

The variety of Splynx settings complements an out-of-the-box customer portal system to help the customers manage their account. Among other things, the portal lets your customers request the change or change their tariff plans by themselves. The last self-serve option will reduce the need for your customers to contact your support team for their tariff management. As a result it gives you the time to focus on other important aspects of your business.
This comprehensive guide reviews the settings that the administrator can adjust to enable or disable certain features.

**Note:** It's required to have more than one *Internet/Voice/Recurring* plan in Splynx in order to send a request or change it from one to another. Double check if the necessary tariff plans are selected in the `Tariff plans available in customer portal` field of the current customer's plan.

For example, a customer uses *Ethernet_100Mbps* as his current Internet service and wants to change it to *Ethernet_500Mbps* plan or just send the request to change the plan by support representative. To maintain such capability, the administrator should [add](configuring_tariff_plans/internet_plans/internet_plans.md) a new *Ethernet_500Mbps* plan into Splynx. Then, go back to the list of all Internet tariff plans and near the *Ethernet_100Mbps*, in *Actions* column, click on <icon class="image-icon">![Edit](edit.png)</icon> (Edit) icon, find the field `Tariff plans available in customer portal` in drop down list choose newly created plan (-s) - *Ethernet_500Mbps* and press `Save` button.

![](img_ks_000001.png)

Follow the step-by-step guide to configure the required settings:

<details>
<summary><b>Request for tariff plan change</b></summary>
<p markdown="1">

**Step 1**

Open `Config → Main → Portal`, click on **PER PARTNER SETTINGS** tab, in case you use the different settings for each [Partner](administration/main/partners/partners.md), choose the necessary one the customer is related to, otherwise use the `Default` one. Be sure that in **Menu** section, in the field **Items**, the `Services` value is selected.

![](img_ks_000002.png)

**Step 2**

Scroll down and find the **Services** section, in the **Internet service** field click on drop down list and select which Internet service fields should be displayed on customer portal. The value `Request tariff plan change` must be selected. After that press `Save` at the bottom of the page.

![](img_ks_000003.png)

**Step 3**

Click on **Customers** item, in the **List** on the left sidebar, find the customer with *Ethernet_100Mbps* Internet plan and open the profile. On **INFORMATION** tab click on `Actions` button and in drop down list choose `Login as customer` option in order to simulate the customer steps.

![](img_ks_000004.png)

**Step 4**

On customer portal on the left sidebar click on **Services** item, the active service (-s) will be visible. In *Actions* column click on <icon class="image-icon">![Change plan](change_plan.png)</icon> (Change plan) icon

![](img_ks_000005.png)

In new window we can select the **New plan start date**, select the **New plan** (the opportunity to choose the plan is available only when in the field `Tariff plans available in customer portal` are selected multiple ones), the **Price of change** value will be set according to the settings in [Change plan](configuration/finance/change_plan/change_plan.md)

![](img_ks_000006.png)

After you press `Request tariff plan change` button, the new window will be opened, the window will be the same as when you create the ticket

![](img_ks_000007.png)

The new ticket will be created in Splynx for support team.

![](img_ks_000008.png)

The support representative, using admin portal, can change the customer's service in customer profile, in **SERVICES** tab by clicking on *Change plan* icon.

![](img_ks_000009.png)

In order to change tariff for multiple customers, please use the following guide - [Tariff Change](configuring_tariff_plans/tariff_change/tariff_change.md)

</p>
</details>



<details>
<summary><b>Self-change tariff plan</b></summary>
<p markdown="1">


**Step 1**

Open `Config → Main → Portal`, click on **PER PARTNER SETTINGS** tab, in case you use the different settings for each [Partner](administration/main/partners/partners.md), choose the necessary one the customer is related to, otherwise use the `Default` one. Be sure that in **Menu** section, in the field **Items**, the `Services` value is selected.

![](img_ks_000002.png)

**Step 2**

Scroll down and find the **Services** section, in the **Internet service** field click on drop down list and select which Internet service fields should be displayed on customer portal. The value `Self-change tariff plan` must be selected. After that press `Save` at the bottom of the page.

![](img_ks_000010.png)

**Step 3**

Click on **Customers** item, in the **List** on the left sidebar, find the customer with *Ethernet_100Mbps* Internet plan and open the profile. On **INFORMATION** tab click on `Actions` button and in drop down list choose `Login as customer` option in order to simulate the customer steps.

![](img_ks_000004.png)

**Step 4**

On customer portal on the left sidebar click on **Services** item, the active service (-s) will be visible. In *Actions* column click on <icon class="image-icon">![Change plan](change_plan.png)</icon> (Change plan) icon

![](img_ks_000005.png)

In new window we can select the **New plan** (the opportunity to choose the plan is available only when in the field `Tariff plans available in customer portal` are selected multiple ones), the **Price of change** value will be set according to the settings in [Change plan](configuration/finance/change_plan/change_plan.md)

![](img_ks_000011.png)

After you press `Apply` button, the new service with will be added in `Pending` status. The service will be changed automatically on the date specified.

![](img_ks_000012.png)

In order to change tariff for multiple customers, please use the following guide - [Tariff Change](configuring_tariff_plans/tariff_change/tariff_change.md)

</p>
</details>
