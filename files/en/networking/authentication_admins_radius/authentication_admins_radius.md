Authentication of admins, Radius
==========

Part of Splynx Framework is a Radius server. Radius protocol is used for authentication, authorization and accounting purpose (AAA).

With Splynx you can setup that when administrators accesses equipment, their credentials will be checked over the Radius server database. If his Username/Password is correct, he will be able to login to equipment. If not, he will not get access. This is a very convenient approach compared to local login. Imagine if you hire a new administrator and you need to update hundreds of routers, APs and switches to create him a local login everywhere or you can give him one common Login/Password. But when person leaves the company, you should change these credentials everywhere. The better method is to connect all networking devices to the Radius server and verify administrator's login's using Radius protocol.

Below are tutorials of how to configure admin Login's using the Splynx Radius server on different platforms:

* [Mikrotik: Radius admin login to Mikrotik routers](networking/authentication_admins_radius/admin_login_to_mikrotik/admin_login_to_mikrotik.md)

* [Admin login to Cisco IOS and IOS XE devices](networking/authentication_admins_radius/admin_login_to_cisco/admin_login_to_cisco.md)

* [Juniper: Junos admin login using Radius protocol](networking/authentication_admins_radius/admin_login_to_juniper/admin_login_to_juniper.md)
