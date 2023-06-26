Remote Support
=====================

This package is designed to simultaneously solve two issues:

1. Secure remote access for technical support. This simplifies the service when you contact us with questions.

2. Creating backup copies in the cloud, which can be very useful in case of loss or damage to local data.

During the installation of the add-on, the user *splynx-remote-support* will be added to the server as a UNIX user and as an administrator of Splynx. For this user, two-factor authentication is enabled, and the password is regularly changed to avoid password brute-force attacks.

To prevent the transfer of your data over the internet, the package uses OpenVPN to create a private encrypted tunnel between your server and our cloud.

The advantage of this approach is that you do not need to share the server. You can limit SSH or web access at your discretion. For maintenance, it is enough to allow traffic within our tunnel.


## Installation

The add-on can be installed in two methods: via CLI or the Web UI.

To install the SSH Term add-on via CLI, the following commands can be used:

```bash
apt-get update
apt-get install splynx-remote-support
```

To install it via the Web UI, navigate to *Config → Integrations → Add-ons:*


![Add-ons](0.png)

Locate or search for the *"splynx-remote-support"* add-on and click the *Install* button in the *Actions* column:  

![](web1.png)

Click the `OK, confirm` button to begin the installation process:

![](web2.png)

__________

After the installation process has been completed, you can test the tunnel using the ping command:

```
op@splynx22:~$ ping 172.29.64.1                                                                          
PING 172.29.64.1 (172.29.64.1) 56(84) bytes of data.                                                     
64 bytes from 172.29.64.1: icmp_seq=1 ttl=64 time=49.0 ms                                                
64 bytes from 172.29.64.1: icmp_seq=2 ttl=64 time=49.2 ms                                                
^C                                             
```

---
> ***Please do not remove these users and do not close the SSH and WEB TCP ports on the firewall of the OpenVPN interface.***
