CPE (Customer Premises Equipment) configuration
===

To configure features of CPE navigate to `Config → Networking → CPE`:

![icon](icon.png)

The following parameters can be configured here:

### Size

![size](size.png)

* **1KB is** - specify the amount of bytes for 1KB for CPE traffic accounting(1000 or 1024 bytes).

### API
![api](api.png)

* **Debug** - enables mikrotik debug log(for debug/test purposes);

* **Attempts** - select the connection attempts(1-10);

* **Timeout** - select timeout in seconds.

### QoS
![qos](qos.png)

* **Reverse in/out** -  enable this if you want to change upload by download and vice versa;

* **Queue type for download** - Set the queue download type;

* **Queue type for upload** - Set the queue upload type.

* **Default QoS rules** - QoS rules can be specified here in format 1 rule = 1 line;

* **Simple target (default)** - select a network.

### WLAN
![wlan](wlan.png)

* **Enable WLAN management** - enables/disables WLAN management.

### Customer blocking
![customer blocking](customer_blocking.png)

* **Enable blocking on CPE** - enables/disablse blocking on CPE with NAT rules;

* **IP** - specify the IP to send all traffic to;

* **Port** - specify the port to send all traffic to.


### DHCP (default configuration)

![dhcp](dhcp.png)

* **Enable** - enables/disables using of the default config on the CPE;

* **Name** - specify a name of the DHCP server;

* **Interface** - type of interface;

* **Lease time** - lease time in minutes;

* **Network** - specify the network;

* **Gateway** - specify the gateway;

* **Pool from** - use IPs start from this IP;

* **Pool to** - last IP to be used from pool;

* **DNS servers** - specify DNS servers separated by comma;

* **WINS servers** - specify WINS servers separated by comma.


**And don't forget to save settings after change.**
