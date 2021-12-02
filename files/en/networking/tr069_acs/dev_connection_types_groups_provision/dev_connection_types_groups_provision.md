Device connection, types, groups and auto-provision flow
==========

## Connect your Mikrotik device

We will use a Mikrotik device with TR-069 client as an example.

First of all, **TR-069 package** should be installed on Mikrotik. If this package is not installed, use the next steps to install it:

1. Open [Winbox](https://mt.lv/winbox64) and connect to the router (use [Wine](https://wiki.winehq.org/Ubuntu) to run Winbox on Ubuntu);

2. Update router to latest stable version `System → Packages → Check for updates` and update if required;

3. Navigate to Mikrotik [download page](https://mikrotik.com/download) and download the package for your device;

4. Extract the downloaded archive and find `tr069-client-X.XX.npk`;

5. Upload `tr069-client-X.XX.npk` file into your device and reboot Mikrotik (`System → Reboot`);

6. After reboot you should see a **TR-069** option in menu:

![tr-mikrotik](tr-mikrotik.png)

Click on **TR069** item and configure **connection to the ACS server**:

1. Put the check-mark to **Enable** client;

2. Put your **ACS URL** - it's a *URL* from menu on **step 3** for a *CWMP* (ends with port `:7547/`);

![URL](urls.png)

In our example, we are using the *domain name* instead of IP address - *192.168.105.80*.

3. Specify username and password with values from **global** parameters (**step 1**);

4. Enable **Periodic Inform Enabled** option.

After these steps you should have the next result:

![connected](connected_device.png)

The values in **Connection Request Username** and **Connection Request Password** fields should appear automatically. **Do not change these values unless absolutely necessary** (e.g. when you need to reconnect your device with an ACS server, these values can be removed and re-enable client - with new connection you will see a new values)..

**IMPORTANT (for Mikrotik devices only)**: if you are using **HTTPS/SSL** on your Splynx server you can get **an error about SSL, asking for the local certificate**. In this case you need to run 2 commands in Mikrotik terminal:

```
/tool fetch https://letsencrypt.org/certs/isrgrootx1.pem
```
```
/certificate import file-name=isrgrootx1.pem passphrase="
```

<details>
<summary>To remove the expired cert use the next</summary>
<div markdown="1">

Example:

```
/certificate remove trustid-x3-root.pem.txt_0

```


</div>
</details>

and **do not change any other config in TR-069 client** (**Client certificate** option must be "none"), just **re-enable TR-069 client**.

After that device will be registered under GenieACS:

![device under genie](device_under_genie.png)

as well as under Splynx:

![device in Splynx](device_in_splynx.png)

Devices can be in the following statuses: `Online`, `Online today`, `Offline`.

Main parameters for ACS are configured and device is connected so you can manage the device remotely now. Also we have a few more options to configure: **Attributes**, **Types** and **Groups**.

![additional config](more_config.png)

## Types:

Simply add different types of devices:

![types](types.png)

## Groups:

**NOTE!** Before configuring ACS groups you need to connect some device to ACS server.

Under groups you can create new entries to group devices.

![groups](groups.png)

Here can be selected the next parameters and the inventory [product](inventory/products/products.md) name (if existed), selected photo of device etc. You can use auto-provision feature to grab some parameters from a device.

## Provisioning flow

Groups is used for **auto-provision** devices and load device's parameters and properties from the correct TR069 attributes.

Once some device is added you can create a group base on that device, provision the configuration parameters from that device, edit such parameters and save. After that these parameters can be used for configuration of other devices based on this group, using previously exported parameters.

![wizzard](wizzard.png)

We have a few options here:

![wizzard options](wizzard_options.png)

|   |   |
| ------------ | ------------ |
| **I have one fully configured device (and ready to reset configuration, (I have backup of full config)**  | this option can be used when you have configured one device (Device 1) of this type and you need to configure another clear device (Device 2) with existed parameters. Splynx will grab parameters from Device 1, check what parameters can be used for Device 2 configuration and pull these changes. Or you have a backup what can be used for configuration  |
| **I have one non configured device and ready to configure this device (or I have backup of config and ready to apply it on next steps)**  |  vice versa to a previous method  |
| **I have two similar devices (One is fully configured, and one is not configured)**  | need 2 devices, one is fully configured and another one is not-configured. The configuration from both routers will be downloaded, only after that this config can be updated  |
| **I have one device and ready to play with manual insert of parameters**  | download configuration from a device and edit this config manually  |
| **I have a configuration file for import and want to import this file**  | in this step you need to import a .csv file with a configuration what can be imported  |
| **I want to insert config manually**  | manual way to configure a device |

If to choose **I want to insert config manually** step, you will see a window with the editor of device objects with its attributes. In this configuration menu you can **create** new object and attribute related to the object, **update**, **delete** or apply the **mass actions** (*enable*, *disable*, *delete*) the existing object and its attribute (-s).

![provisioning attributes](provisioning_attributes.png)

![](mass_actions.png)

We can apply **4 actions to the object**:

![object actions](object_actions.png)

- **create** - create an object with the attributes specified in the configuration, but if we already have an object with these attributes, a new object will not be created;
- **update** - update the object's attribute value (-s);
- **delete** - remove all objects according to the path, e.g. object `Device.Firewall.X_MIKROTIK_Filter.Chain.3.Rule` will remove all firewall rules from output chain on Mikrotik;

![object actions](delete_firewall_rules.png)

- **delete with equal condition** - remove the object if the attribute's `value` was specified in the configuration, e.g. remove all the disabled rules in firewall output chain.

![object actions](del_equal_condition.png)

If you select **template** as attribute option you can **use twig** to create field value.

![object actions](template_twig.png)

Also, by click on additional button near **Save** button

![object actions](import_export.png)

you can **preview**,  **export settings into a .csv format** (for future, use it for configuration of other devices)

![object actions](provision_preview.png)

**import an existing .csv file** with device settings (**NOTE!:** If there are already some settings on the device, they will be deleted during import)

![object actions](provision_import.png)

or **clean up** the existing device config.
