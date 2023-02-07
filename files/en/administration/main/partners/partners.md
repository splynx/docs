Partners
========

A partner in Splynx is basically a service provider or any sub-provider of your services.

![Partners](icon.png)

The partners table shows a list of all Partners on the system with the number of customers assigned to them and number of online customers.  If you click on each number in the Customers' column, the full list of customers associated with the Partner appears.

![Partners](partners.png)

If it is a long list of customers and you have to check them by a particular status you can sort them in the top right corner of the page:

![Filter](filter.png)

**Another way to filter or search for** customers who belong to the same Partner is by clicking on the *Partner field* in *Customers → Search*.

![Search](search.png)

_______________________________________________________________

To **add a new partner** in *Administration → Partner*, click the *Add* button at the top right corner of the table:

![Create partner](create_partner.png)

You can also **edit the partner's name** by clicking on the *Edit icon* <icon class="image-icon">![ViewIcon2](view_icon2.png)</icon> in the Actions column.

![Edit partner](edit_partner.png)

You might also be interested in [Realms add-on](addons_modules/realms/realms.md) tutorial.

____________________________________________________________________

Here are a few more tips on the configuration of Partners:

1. **Not only Customers can be assigned to a particular Partner, but also Routers and Tariff plans.**

In *Networking → Routers → List* you can check the full list of **Routers** and filter the table by *Partner*. If you'd like to change or add a partner to the particular router, you have to click on it in the *Title* column or click on *Edit* <icon class="image-icon">![ViewIcon2](view_icon2.png)</icon> in the Actions column.

![Routers list](routers_list.png)

The window will appear where you can make the changes:

![Change partner](change_partner.png)

![Sort by partner](sort_by_partner.png)

__________________________________________________________

The same procedure can be used for **Tariff Plans**. When you click on *Tariff plans → Internet* (for example), a full list of Internet Tariff Plans will appear, where you can filter the table by *Partner*.

If you'd like to change or add a partner to the particular Tariff Plan, you have to click on it in the *Title* column or click the *Edit* <icon class="image-icon">![ViewIcon2](view_icon2.png)</icon> icon in the Actions column.

![Plans list](plans_list.png)

The window will appear, where you can make the changes:

![Edit plan](edit_plan.png)

2. **There is a way to limit access to information for admins in Splynx by selecting only one partner.**

Administrators will be able to operate with all information associated with one particular partner if you associate them with only one specific partner. You can find this option in *Administration → Administrators*. 

Click on the Edit <icon class="image-icon">![ViewIcon2](view_icon2.png)</icon> icon in the Actions column and a window will appear where it will be possible to select one partner or the option *Any*.

![Edit administrator](edit_administrator.png)

**You can also change permissions for adding, editing or deleting partner(-s) for the particular administrator** by clicking on the permissions <icon class="image-icon">![ViewIcon3](view_icon3.png)</icon> icon in the Actions column. 

In the window that appears, click on the *Administration* section, enable Partner and select permissions to add, edit or delete Partners:

![Partners permissions](partners_permissions.png)

3. **It is possible to set up a commission for partners from each payment made by customers for partners services.**

You can set it up in *Config → System → Company Information*. In *Company Information*, select the desired Partner to work with and in the *Partner percent field*, specify the percentage for the Partner's commission.

![Partner](template_values.png)

After the commission has been set up, you will be able to check the amount paid to the partner in *Finance → Invoices*. 

At the top of the window choose an appropriate *Partner* (with Period of time and Payment Status, if necessary) and below the list of Invoices you will see the "*Totals*" table, displaying total amount paid and the amount of commission for the partner.

![Commission](commission.png)
