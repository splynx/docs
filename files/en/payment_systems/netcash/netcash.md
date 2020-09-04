Netcash
====================

Using the Netcash addon, customers can pay for their invoices with a few clicks from the customer portal.

The addon can be install in two methods, via the CLI or Web UI of your Splynx server.

To install the addon via the Web UI, navigate to **Config → Integrations → Add-ons**

![icon](icon.png)

Locate or search for the "splynx-netcash" addon and click on the install button in the *Actions* column:

![install](install.png)

To install it via CLI, the following commands can be used:

```bash
apt update
apt install splynx-netcash
```

After the installation  process has completed, the addon has to be configured, to do this navigate to **Config → Integrations → Modules list**

![modules list](icon_modules.png)

Locate or search for the "splynx-netcash" addon and click on the edit button in the *Actions* column:

![netcash](edit_module.png)

![settings](settings_1.png)
![settings2](settings_2.png)

The "Service key" field must be inserted with your PayNow service key:

![netcash profile](netcash_profile.png)

Under the "Payment notifications" section, you have to configure the Accept URL, Decline URL and Re-direct URL with the value in the following format: **https://yourSplynx.com/netcash/result** (Splynx URL + /netcash/result).


The rest of the parameters doesn't have to be changed or you can configure an additional service fee(if needed) and other common settings.

After the configuration of the addon, entry points(widgets for portal) should be enabled:

Navigate to **Config / Integrations / Module list**, locate or search for the "splynx-netcash" module and click on the entry points icon in the *Actions* column:


![entry points](edit_entry_points.png)

![enable entry](enable_entry.png)


Entry points (widgets) on the customer's portal for customers to pay their invoices can be enabled/disabled here.

We've enabled 2 entry points and they are available from the customer's portal:

On the dashboard:
![widget 1](widget_1.png)

![pay 1](pay_widget_1.png)

And under Finance/Invoices:
![pay 2](pay_widget_2.png)

We also have a widget for prepaid customers to add an amount of money directly from the customer portal. To enable it navigate to the addon's entry points menu and locate the following entry point/widget:

![prepaid widget](prepaid_widget.png)

You will then see it on the customer's portal:

![prepaid pay](prepaid_pay.png)

Netcash logs can be found under **Administration → Logs → Netcash logs**

![Logs](logs.png)

As you can see on our screenshot, we also have Netcash debit order logs because we have installed this addon as well. Only use the selected log on the screenshot log entry for the Netcash addon.
