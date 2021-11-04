Realms add-on
=========

The *Realms* add-on module is designed to simplify the process of grouping customers that use one or different [partners](administration/main/partners/partners.md) according to the logical areas. The *Realm* - the ending after `@`(at) sign that is used as customer login in their Internet service, e.g. `john@managed.com`, where `@managed.com` is a *Realm* entity.

### Add-on installation

The add-on can be installed in two methods, via the CLI or the Web UI of your Splynx server.

To install the add-on via CLI, the following commands can be used:

```
apt-get update
apt-get install splynx-realms
```
To install the add-on from the Web UI:

Navigate to `Config → Integrations → Add-ons`:

![(image)](1.png)

Locate or search for the `splynx-realms` add-on and click on the *Install* icon in the *Actions* column:

![(image)](2.png)

Click on the **OK, confirm** button to begin the installation process:

![(image)](3.png)

### Add-on settings

After the installation process has completed, all parameters for the add-on can be found in `Config → Integrations → Modules list`.

![(image)](4.png)

Locate or search for the `splynx-realms` add-on module and click on the
<icon class="image-icon">![edit](edit.png)</icon> (*Edit*) icon in the *Actions* column,

![(image)](5.png)

Double check if **Entry points status for portal** parameter is `Enabled`.

![(image)](6.png)

The configuration of add-on **Entry points** can be found in `Config → Integrations → Modules list`, near the `splynx-realms` module item in *Actions* column, click on the <icon class="image-icon">![entry_point](entry_point.png)</icon> (*Edit entry points*) icon. More information about *Modules list* can be found [here](configuration/integrations/modules_list/modules_list.md).

## Using the Realms add-on

**Add new Realm values to the existing Partner (-s)**

Navigate to `Config → Administration → Partners`:

![(image)](7.png)

Locate the necessary *Partner* and click on the <icon class="image-icon">![edit](edit.png)</icon> (*Edit*) icon.

![(image)](8.png)

In the new window in the **Realms** field, specify the required values and save changes.

**NOTE:**

- Each value should be started with a new line. The `@` (at) sign can be optionally added at the beginning of the value as well, it will not lead to such characters duplication in the `Service login` formation;

- One partner can have multiple *Realms*. The *Realms* names are not unique, it means that same *Realm* can be used by many *Partners*.

![(image)](9.png)

**Select the particular Realm in Internet service**

Open `Customers → List`, search the needed customer and open their profile, navigate to **Services** tab and click on the <icon class="image-icon">![edit](edit.png)</icon> (*Edit*) icon near the Internet Service

![(image)](10.png)

In new window, find **Realm** field and click on the <icon class="image-icon">![](view_set.png)</icon> button.

![(image)](11.png)

Afterwards, choose the necessary *Realm* value from drop-down list and press the <icon class="image-icon">![](select.png)</icon> button and save changes. It's **possible to choose only *Realm* that belong to specific partner with which the customer is associated**.

![(image)](12.png)

![(image)](13.png)

Then, double check if the `Service login` has been changed.

![(image)](14.png)

**NOTE:**

- In order to remove the *Realm* value from the `Service login` field, you can select empty item from drop-down list of available values

![(image)](15.png)

or erase the particular *Realm* value in *Partner* configuration window. Do not forget to save changes.

![(image)](16.png)

**Show all customers according to the specific Realm**

Navigate to `Customers → List` and in the **Search** field type the name of *Realm* to show the customers relation:

![(image)](17.png)

In case **Realm** field is disabled in the list of customers, click on the breadcrumbs <icon class="image-icon">![](enable_fields.png)</icon> icon at the bottom of the table and enable the same-name toggle.

![(image)](18.png)

додати у статтю Partners лінку на Realms
