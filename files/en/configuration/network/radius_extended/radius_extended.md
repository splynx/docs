Radius Extended
===============

![icon](icon.png)

In addition to the main Radius configuration, in this section, we can configure additional features of Radius.

To change Radius Extended configurations, navigate to `Config/Networking/Radius extended`

![settings](settings_1.png)

## Radd Server

In Splynx we have two Radius servers. We use Freeradius as an **external** Radius server; it accepts connections from clients (from routers). Freeradius transfers Radius requests to the internal Radius server called **splynx_radd**. Here we can configure where **splynx_radd** listens to connections.

* **Listen Ip** - IP of the **splynx_radd** server.  
* **Listen port** - **splynx_radd** port.

**NOTE!** If you change the configuration here, you should also change it in the **PeerAddr** and **PeerPort** configuration in the _/etc/freeradius/splynx/splynx.pl_ file.

## Debug / Logs

* **Short log** - enables/disables Radius short logs;  
* **File (short log)** - Radius short.log file location;  
* **Debug** - enables/disables Radius debug log(/var/www/splynx/logs/radius/debug.log);  
* **Debug level** - debug level (0 - 10), 10 - more detailed;  
* **Console** - push debug messages to console, not recommended;  
* **Syslog** - push debug messages to syslog, not recommended;
* **File** - push debug messages to file: /var/www/splynx/logs/radius/debug.log

## Radius extended

* **Check online** - checks if a customer is already online. If online - do not allow a new connection (with the same credentials). If disabled, customers can connect multiple times with the same credentials;

* **DHCP (Send framed-route attribute)** - Send a framed-route from the Radius server;

* **DHCP (Add customer to online after login)** - when we use DHCP, add customers to the online list, immediately after they connect. If disabled, customers will be added to the online list, only when their traffic reaches the accounting limit (under _Config / Networking / MikroTik API_"min bytes for accounting");

* **Bind MAC address on first connect** - If the  MAC attribute is empty in the internet service settings - this adds the MAC/IP from where the customer connects for the first time;  

* **Maximum unique MAC addresses** - maximum number of MAC addresses that can be added into the internet service settings.

![settings 2](settings_2.png)

## Administrative access

* **Allow admin access without NAS** - allows administrators access in case the NAS is not found on Splynx;
* **Default NAS ID** - NAS ID, needed if access without NAS is enabled.

## Radius NAS settings

* **Force network to use one NAS** - enables/disables forcing a network to use only one NAS;

* **Network** - specify the network (for example: 10.10.0.0/20) if the previous settings is enabled;   

* **Default NAS ID** - NAS ID which will be used by default for the network from the previous setting;  

* **Set static IP on connect** - If enabled, static IP's will be set to services on connecting.

## Proxy accounting

* **Enable proxy accounting** - enables/disables proxy accounting;  
* **Radius host** - IP:Port;  
* **Radius secret** - Radius secret;
* **NAS type ID** - request for this NAS Type will be proxied to the next radius, 0 - all.

## IP From pools (assignment)

* **Link locations** - Link customer location to IP Pool location, this will work in a case where, in the customer service,  "Any pool" is selected, and all locations will cover different pools;

* **Use IP pool with "Location = All"** - In case of the pool associated with the customer location is not found, we can use Pools with Location = All.

![settings 3](settings_3.png)

## Periodic RADIUS server restart

We can specify periodic restarts of the RADIUS server to prevent memory leaks here. The use of this feature is highly recommended.

* **Enable** - enables/disables periodic restarts;

* **Restart once per** - select a period for the periodic restart(day, week, month);

* **Hour** - time when the RADIUS server will be restarted. Recommended time - late at night, midnight or after.


## RADIUS tools

* **Restart RADIUS** - using this button the RADIUS server can be restarted. Recommended to use after new configurations have been made to apply changes, after the reboot. **Be attentive - customers can be disconnected**
