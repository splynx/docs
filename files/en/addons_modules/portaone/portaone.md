PortaOne
================================================

PortaOne add-on is used to import customers' calls from the PortaOne software into Splynx. 

It will be then possible to show calls and their prices in Splynx PDF invoices and invoice customers for those calls.

## Installation

The add-on can be installed in two methods: via CLI or the Web UI.

To install PortaOne add-on **via CLI**, the following commands should be used:

```bash
apt-get update
apt-get install splynx-portaone
```

To install the addon **via the Web UI**:

1. Navigate to *Config → Integrations → Add-ons*.

2. Locate or search for the **"splynx-portaone"** add-on and click on the install icon in the *Actions* column:

![Install](install.png)

3. Click on the `OK, confirm` button to begin the installation process:

![Confirm](confirm.png)

## Basic configuration

Navigate to *Config → Integrations → Modules list* and search for *splynx_addon_portaone*.

Then click the *Edit* (Config) button to perform the basic configuration:

![image](modules_list.png)

### API settings

![ap_settings](ap_settings.png)

<icon class="image-icon">![image](warning.png)</icon> API domain, API key and API secret are already provided by default after the add-on installation. It is not recommended to change them.

### PortaOne API settings

![portaone_ap](portaone_ap.png)

* **API URL** - PortaOne API URL;
* **Login** - your login to access the PortaOne API;
* **Password** - your password to access the PortaOne API; 

<icon class="image-icon">![image](warning.png)</icon> PortaOne requires to change the password regularly.

* **Token** - your token to access the PortaOne API.

<icon class="image-icon">![image](note.png)</icon> The password is not required if the token is provided.

### Synchronization settings

![synchronization](synchronization.png)

* **Import CDR from date** - the date (in 'Y-m-d' format) used as the start date for the CDR import for new paired PortaOne customers. If left empty, the start date will be minus one day from the first import date;
* **Import CDR by cron** - import PortaOne CDR by [cron](https://opensource.com/article/17/11/how-use-cron-linux).

## Customer account settings

The *PortaOne customers ids* field will automatically appear after the add-on installation under the customer's *Additional information*.

When the basic configuration is done, add a PortaOne ID for each customer you want to import calls of: 

![portaone id](porta_id.png)

Besides that, set the customer's phone number for their voice service:

![add phone](add_phone.png)

## Voice processing configuration

The next step is to configure the Auto CDR processing.

You need first to import data source in [*Config → Voice → Import data source*](configuration/voice/import_data_source/import_data_source.md):

![import data source](data_source.png)

Then navigate to [*Config → Voice → Auto CDR processing*](configuration/voice/auto_cdr_processing/auto_cdr_processing.md) and create a new data source to import from:

![cdr processing](cdr_processing.png)

![cdr created](cdr_created.png)

Now the system will auto process voice calls from the addon local folder.