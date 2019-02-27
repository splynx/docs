Mikrotik: Local auth, API
==========

Instead of using Radius, Splynx is able to push authentication rules for customers to Mikrotik router via API. Advantage of this approach is that rules for authentication are created in routers and are stored there locally. It means, if Splynx or Radius server will not respond, customers will still  be able to get Internet access. Disadvantage is that router should be always specified in customer settings where customer is connected. Also customers can only get permanent IP from Splynx.


Authentication rules can be added via API:

* PPP Secrets
* DHCP Leases
* Hotspot users

In all types of API authentication is important to have Mikrotik API enabled on router and also in Splynx router settings:

![Router mikrotik](static_ip_api.png)
![API port](api_port.png)


When both things are enabled, it's useful to create a special admin account for Splynx, which will be used for API login to router and making changes there. You can create special access group with the following permissions and then include admin to this group:

![Group](group.png)

![User](user.png)

Below are described all types of API authentication and how Splynx covers it with Mikrotik RouterOS:


### Mikrotik PPP Secrets via API

First of all, select PPP secrets as type of authentication in Spynx router settings:

![Authorization/Accounting PPP/API](api_secrets.png)


Then in internet service of customer should be selected a router where Splynx will push authentication rules and also grab statistics from. Login and password should be specified there and also Permanent IP address. API authentication works well only with permanent IP assignments. In case of dynamic IP assignment, Splynx will not know which IP is used by customer and will not be able to gather statistics from IP accounting of Mikrotik router.

![Edit service](edit_service.png)

After saving, Splynx will connect to router and create entries in `PPP → Secrets`:

![Secret API](secrets_api.png)


### Mikrotik DHCP Leases via API

Please choose DHCP leases as type of authentication in Spynx router settings.

![DHCP/API](aa_dhcp.png)

In internet service of customer should be selected a router where Splynx will push authentication rules and also grab statistics from. It is important to set the MAC address of the customer. Only permanent IP works in API authentication because of limitations in grabbing accounting from Mikrotik IP accounting:

![Edit service](edit_service1.png)

When we save the service information, Splynx connects to the router and adds static DHCP Leases in *IP → DHCP Server → Leases*

![Leases](leases.png)

In settings of DHCP server you can set an option, that all non authenticated customers will get IPs from fake pool and all authenticated users will get IPs which are set in Leases by Splynx.



### Mikrotik Hotspot users via API

Select Hotspot users as type of authentication in Splynx router settings:

![Router information](router_info.png)


In internet service of customer: permanent IP address should be selected and router should be specified. Login and password are values for hotspot entry. In case of MAC authentication you can specify a MAC address of end user:

![Edit service](edit_service2.png)


When it saved, Splynx creates IP hotspot entries in Mikrotik router under `IP → Hotspot → Users`:

![Hotspot users](hs_users.png)

---
When authentication type is configured and Splynx pushed the rules to Mikrotik router, we can see clients coming online in 5 minute interval. Splynx grabs statistics from Mikrotik routers via API every 5 minutes. The log of accounting you should be able to find in `Splynx → Networking → Routers` under Mikrotik API log tab:

![Accounting](accounting.png)

### Troubleshooting

If PPP secret or DHCP lease or Hotspot user is not created on the router via API, please check if IP address is specified in customer's internet service settings. Also Router should be specified there. For DHCP also check MAC address. It should be set.

#### Accounting
If you see accounting records in Splynx Mikrotik log but accounting data is wrong, check if IP Fastpath is enabled - disable it:

![(fastpath)](fastpath.png)

---
If you do not see accounting records in Splynx Mikrotik log, check in database if there is correct time of last API connection for gathering accounting.
Issue this in command line:

* For Debian:
```bash
root@debian# echo "select last_accounting from routers_mikrotik;" | mysql splynx
```

* For Ubuntu:
```bash
user@ubuntu$ echo "select last_accounting from routers_mikrotik;" | mysql -u debian-sys-maint -p splynx
```
For Ubuntu you can find the password for debian-sys-maint MySQL user in the file `/etc/mysql/debian.cnf`.

If any of given times is in the future, you can reset all times by issuing:

* For Debian:
```bash
root@debian# echo "update routers_mikrotik set last_accounting = '0000-00-00 00:00:00';" | mysql splynx
```

* For Ubuntu:
```bash
user@ubuntu$ echo "update routers_mikrotik set last_accounting = '0000-00-00 00:00:00';" | mysql -u debian-sys-maint -p splynx
```
You can find the password for debian-sys-maint MySQL user in the file `/etc/mysql/debian.cnf`.