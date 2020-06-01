Authentication of users
==========

Splynx supports different ways of customers' central authentication within the network of Internet providers. It always depends on the topology of the ISP and the technology that the ISP decides to use. Access technologies are widely used and their advantages and disadvantages are described below:

* **PPPoE** - easy to maintain and implement. Customer sets up username and password on the CPE device, and all networking settings received by the CPE comes from the PPPoE NAS (Network Access Server). It also provides encryption if needed and accounting for getting usage statistics. It had issues with MTU in past, but in the last few years these issues were fixed by main vendors.

* **IPoE (or DHCP)** - DHCP is based on the MAC address of the client. It can also be linked to a port of the switch where the customer is connected ([DHCP option 82](networking/authentication_users/dhcp_option_82/dhcp_option_82.md)). Several vendors do not provide accounting capabilities (Mikrotik routers)

* **Wireless Authentication** - when ISP's has a wireless network, they need to maintain access of CPE devices to their Access Points. For this purpose several wireless authentication methods are used, such as a password inside TDMA protocols or wireless access-lists

* **Hotspot** - customers' has to enter their username's and password's on a webpage before using the Internet. Many hotspot networks allow free limited access and then charge customers for additional usage or advanced plans.

* **Static IP addressing** - some ISP's don't have central management of authentication and setup static IP addresses to CPE devices. With the Mikrotik RouterOS platform, Splynx can manage even customers who has static IP's in Vlan per customer scenario or plain IPv4 connection. Also, Splynx can grab statistics from Mikrotik routers for such customers.


Below are manuals for different types of user authentication in Splynx ISP Framework:


* [Mikrotik: DHCP using Radius](networking/authentication_of_customers/mikrotik_dhcp_radius/mikrotik_dhcp_radius.md)

* [Mikrotik: PPPoE and other PPP tunnels using Radius](networking/authentication_of_customers/mikrotik_pppoe_radius/mikrotik_pppoe_radius.md)

* [Mikrotik: Hotspot with Radius](networking/authentication_of_customers/mikrotik_hotspot_radius/mikrotik_hotspot_radius.md)

* [Mikrotik: Hotspot Login from Splynx portal](networking/authentication_of_customers/mikrotik_hotspot_from_portal/mikrotik_hotspot_from_portal.md)

* [Mikrotik: Static IPs with API](networking/authentication_of_customers/mikrotik_static_api/mikrotik_static_api.md)

* [Mikrotik: Local auth with Mikrotik API](networking/authentication_of_customers/mikrotik_local_auth_api/mikrotik_local_auth_api.md)

* [Mikrotik: OpenVPN, Radius](networking/authentication_of_customers/mikrotik_openvpn_radius/mikrotik_openvpn_radius.md)

* [DSL Telkom (Openserve) authentication](networking/authentication_of_customers/dsl_telkom_openserve/dsl_telkom_openserve.md)

* [Cambium: Wireless Authentication via Radius](networking/authentication_of_customers/cambium_wireless_auth_radius/cambium_wireless_auth_radius.md)

* [Ubiquiti: Wireless authentication with Radius](networking/authentication_of_customers/ubiquiti_wireless_auth_radius/ubiquiti_wireless_auth_radius.md)

* [Ubiquiti: PPPoE authentication on Edge Routers](networking/authentication_of_customers/ubiquiti_pppoe_edge/ubiquiti_pppoe_edge.md)

* [Cisco IOS: PPPoE with Radius server](networking/authentication_of_customers/cisco_pppoe_radius/cisco_pppoe_radius.md)

* [Cisco IOS XE: PPPoE with Radius server](networking/authentication_of_customers/cisco_xe_pppoe_radius/cisco_xe_pppoe_radius.md)

* [Juniper: PPPoE with Radius server](networking/authentication_of_customers/juniper_pppoe_radius/juniper_pppoe_radius.md)

* [Accel-ppp: Server for Linux](networking/authentication_of_customers/linux_accel/linux_accel.md)
