Authentication of users
==========

Splynx supports different ways of  customers' central authentication in the network of Internet provider. It always depends on topology of ISP and technology that ISP decides to use. Access technologies are widely used and their advantages and disadvantages are described below:

* **PPPoE** - easy to maintain and implement. Customer on CPE device setups username and password and all networking settings CPE receives from PPPoE NAS (Network Access Server). Also provides encryption if needed and accounting for getting statistics of usage. Had issues with MTU in past, but in last years these issues were fixed by main vendors.

* **IPoE (or DHCP)** - DHCP is based on MAC address of client. Also can be linked to port of switch were customer is connected ([DHCP option 82](networking/authentication_users/dhcp_option_82/dhcp_option_82.md)). In several vendors don't provide accounting capability (Mikrotik routers)

* **Wireless Authentication** - when ISP has a wireless network, he needs to maintain access of CPE devices to his Access Points. For this purpose several wireless authentication methods are used, such as a password inside TDMA protocols or wireless access-lists

* **Hotspot** - customer has to enter his username and password on the webpage before using the Internet. Many hotspot networks allow free limited access and then charge customers for addtional usage or advanced plans.

* **Static IP addressing** - some ISPs don't have central management of authentication and setup static IP addresses to CPE devices. With Mikrotik RouterOS platform Splynx can manage even customers who's got static IPs in Vlan per customer scenario or plain IPv4 connection. Also Splynx can grab statistics from Mikrotik routers for such customers.


Below are manuals for different types of user authentication in Splynx ISP Framework:


* [Mikrotik: DHCP using Radius](networking/authentication_users/mikrotik_dhcp_radius/mikrotik_dhcp_radius.md)

* [Mikrotik: PPPoE and other PPP tunnels using Radius](networking/authentication_users/mikrotik_pppoe_radius/mikrotik_pppoe_radius.md)

* [Mikrotik: Hotspot with Radius](networking/authentication_users/mikrotik_hotspot_radius/mikrotik_hotspot_radius.md)

* [Mikrotik: Hotspot Login from Splynx portal](networking/authentication_users/mikrotik_hotspot_from_portal/mikrotik_hotspot_from_portal.md)

* [Mikrotik: Static IPs with API](networking/authentication_users/mikrotik_static_api/mikrotik_static_api.md)

* [Mikrotik: Local auth with Mikrotik API](networking/authentication_users/mikrotik_local_auth_api/mikrotik_local_auth_api.md)

* [Mikrotik: OpenVPN, Radius](networking/authentication_users/mikrotik_openvpn_radius/mikrotik_openvpn_radius.md)

* [DSL Telkom (Openserve) authentication](networking/authentication_users/dsl_telkom_openserve/dsl_telkom_openserve.md)

* [Cambium: Wireless Authentication via Radius](networking/authentication_users/cambium_wireless_auth_radius/cambium.md)

* [Ubiquiti: Wireless authentication with Radius](networking/authentication_users/ubiquiti_wireless_auth_radius/ubiquiti_wireless_auth_radius.md)

* [Ubiquiti: PPPoE authentication on Edge Routers](networking/authentication_users/ubiquiti_pppoe_edge/ubiquiti_pppoe_edge.md)

* [Cisco IOS: PPPoE with Radius server](networking/authentication_users/cisco_pppoe_radius/cisco_pppoe_radius.md)

* [Cisco IOS XE: PPPoE with Radius server](networking/authentication_users/cisco_xe_pppoe_radius/cisco_xe_pppoe_radius.md)

* [Juniper: PPPoE with Radius server](networking/authentication_users/juniper_pppoe_radius/juniper_pppoe_radius.md)

* [Accel-ppp: Server for Linux](networking/authentication_users/linux_accel/linux_accel.md)

