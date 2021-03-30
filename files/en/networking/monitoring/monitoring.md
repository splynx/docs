Monitoring (Hardware)
==========

Using monitoring in Splynx you can track the status of your network and in case any device goes down, the system will automatically notify the responsible admins via the portal, email, SMS or each method comdined. Splynx is using SNMP and ping tools to monitor devices.


### Add a new device

To add a new device navigate to dashboard and under **Networking** section find **Hardware** option:

![hardware](dashboard.png)

Inside this menu you can add a new device using "Add" button, display list of all devices, view recently selected monitoring device and check backups of these devices.

Let's click on "Add" button and add a new device into monitoring:

![new_device](add_device.png)

* **Title** - name of the device;
* **Parent** - select a parent device( if exists). You can build a parent-child relations in Splynx monitoring;
* **Vendor** - vendor name. You can add more vendors under _Config/Networking/Monitoring_;
* **Product/Model** - information about the device model;
* **IP address** - IPv4 of the device to which SNMP and Ping tools will connect;
* **Port** - SNMP port;
* **Ping this device** - If enabled, Splynx will ping the device to track connectivity;
* **SNMP Monitoring** - If enabled, Splynx will connect via SNMP to device and load available information. Should be also enabled on a device;
* **SNMP community** - define community, using "public" is insecure. We recommend to create some custom community on a device and use it;
* **SNMP Version** - select version (2 is recommended);
* **Type** - select type. You can add more types under _Config/Networking/Monitoring_ ;
* **Group** - define a group for device. This field is using for notifications configuration;
* **Partners** - defines the partner that can see the device;
* **Location** - defines a location;
* **Address** - information about the address where device is installed;
* **Send notifications** - enable/disable sending of notifications if device goes down/up;
* **Delay timer for notification** - set a delay in minutes to send notification about status change. If device is down, Splynx will wait for 10 minutes and is status doesn't change - will send a notification.


When device is up and running we can see the status:

![device_info](device_info.png)

As you can see Splynx is able to ping this IP. If device is unreachable ping will be also unreachable and status of "Last ping statuses" will be negative.

### Graphs

That was initial configuration to get ping and SNMP status of the device. To monitor some advanced parameters we can use SNMP OIDs to get the values and measure such thing as CPU performance, memory usage, voltage or interface's speed. First of all we need to get available SNMP OIDs to build some graphs. We can do this under tab "SNMP OID":

![SNMP_OID](snmp_tab.png)

You can run SNMP walk to get all available OIDs or add it manually using "Add SNMP OID" button. Let's click on "SNMP walk" to load OIDs automatically and avoid manual input mistakes:

![snmp_walk](run_snmp_walk.png)

Here you can load all OIDs or for interfaces only. Let's click on "Get all" button and wait 1-2 minutes for a result.

Once this done click on "SNMP walk" to see all OIDs what we received from a device:

![snmp_walk_result](snmp_walk_result.png)

For example we need to monitor **ether1** port bandwidth so we need to click on "+" under these values:

![add_oid](add_oid.png)

![add_oid2](add_oid_2.png)

As a result we added 2 SNMP OIDs for monitoring in/out values of ether1 interface. Now we can create a graph with these OIDs.

**NOTE!** First - add OIDs, next build a graph.

![add_oid3](add_oid_3.png)

To build a graph let's switch to "GRAPHS" tab and click on "Add graph":

![add_graph](add_graph.png)

![add_graph2](create_graph.png)

Here you need to specify title, vertical title and the most important is add data sources. In this case i need to select data source "ether1 in" and click add and after that select "ether1 out" and add. **If you are going to measure the interface speed - factor value should be 8 and "value in" = Bps**. Click on "Color" field to select a color and click on "Draw" field to select a way of displaying data(line or area). Click on "Preview" button to generate a preview and click on "Add" button to create a graph.

![list_of_graphs](graphs.png)

Now under "Operations" near each graph you can click on "Edit", "View graph", "Delete" buttons. Let's click on "View graph":

![view_graph](final_graph.png)

You can select different periods of time here.

### Backups

Devices added to the monitoring list can also be configured for backups. Simply configure the login details, port to communicate(SSH),the command, and specify the hours which you would like to run backups:

![configure_ssh](backups.png)

click on "Test connection" and "Test backup configuration" to ensure that it works:

![test_connection](test_connection.png)

![test_backup_config](test_backup.png)

We are using MikroTik "export" command to get an export of all settings.

Here we have a first backup of our device:

![backups_list](backups_list.png)

Under "Operations" you can click on "Download" button or on "View difference" button. To see difference you should have at least 2 backups.

Under _Networking / Hardware / Backups_ you can find a list of all backups for all devices:

![all_backups](networking_monitoring_backups.png)

### Logs

Under **Logs** tab you can find log records:

![logs](logs.png)


### Notifications

It is possible to send a notifications when some device goes down. First action to do is to add a notifications group under _Networking / Monitoring / Groups_:

![monitoring](monitoring.png)

scroll down and find window "Groups":

![groups](groups.png)

![add_group](add_group.png)

With this setup I want to create a group "Engineers" where only administrator "admin" consists and this administrator will receive email notification + portal notification on a dashboard. The subject of an email will be "Device alert!" and body of a message is defined with email template what can be updated.

Once this done we need to change a group for a device:

![select_group](select_group.png)

So as per device configuration an administrator from a group "Engineers" should receive a notification if device is down for more than 10 minutes:

![email_alert](email_alert.png)

### Other

Charts and SNMP values from Monitoring can be used in [Splynx Weathermap add-on](../weathermaps/weathermaps.md) as on example below:

![Weathermap](weathermap.png)

Please follow the video tutorials to find out more about Splynx monitoring:

<iframe frameborder=0 height=270 width=350 allowfullscreen src="https://www.youtube.com/embed/2XDbqc7b-cI?wmode=opaque">Video on youtube</iframe>


Ping tools :

<iframe frameborder=0 height=270 width=350 allowfullscreen src="https://www.youtube.com/embed/BebSml0tQ-U?wmode=opaque">Video on youtube</iframe>


CPU usage :

<iframe frameborder=0 height=270 width=350 allowfullscreen src="https://www.youtube.com/embed/jr_HKAT4qHA?wmode=opaque">Video on youtube</iframe>


Memory usage :
<iframe frameborder=0 height=270 width=350 allowfullscreen src="https://www.youtube.com/embed/yIlq_msIpmA?wmode=opaque">Video on youtube</iframe>
