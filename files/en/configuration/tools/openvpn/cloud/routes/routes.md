OpenVPN client / Routes
==========
Format:
------
**IP [netmask] [gateway] [metric]**

One route per line

Example
------
```
192.168.76.1
192.168.77.0 255.255.255.0
192.168.78.0 255.255.255.0 192.168.78.1
192.168.79.0 255.255.255.0 192.168.79.1 10
```

Description
------
**192.0.2.1** #route to host 192.0.2.1 via OpenVPN remote side

**192.0.2.0 255.255.255.0** #route to network 192.0.2.0/24 via OpenVPN remote side

**192.0.2.0 255.255.255.0 198.51.100.1** #route to network 192.0.2.0/24 via router 198.51.100.1 available on the OpenVPN remote side

**192.0.2.0 255.255.255.0 198.51.100.1 10** #route to network 192.0.2.0/24 via router 198.51.100.1 available on the OpenVPN remote side. Route metric 10. Default metric is 0.

Default netmask is **255.255.255.255**

More information
------
[Site-to-site VPN routing explained in detail](https://openvpn.net/vpn-server-resources/site-to-site-routing-explained-in-detail/)

[Reference manual for OpenVPN 2.4](https://openvpn.net/community-resources/reference-manual-for-openvpn-2-4/)
