Mikrotik routers
==========

Mikrotik routers are default router type that is set up in Splynx when you create a new router.

Splynx supports communication with routers using Mikrotik API or Radius protocol.


### Mikrotik API custom Rules

Splynx ISP Framework supports MikroTik API Custom rules

create file: ``/var/www/splynx/config/mikrotik.php`
header:
```
; <?php exit(); ?>
; Do not remove this lines
; Splynx Mikrotik API config file
```
Nas type ID:
```
[1]
```
Rules:
```
dhcp_leases['address'] = '{ip}';
dhcp_leases['mac-address'] = '{mac}';
dhcp_leases['comment'] = 'SpLUser_{customer_id}-{service_id}';
```
additional part (example):
```
dhcp_leases['server'] = '{customer_additional_route}';
```
You can use keys:
* service_key – {service_id} as example – key or additional attribute name
* customer_key – {customer_id} as exaple – key of additional attribute name

Example file: `/var/www/splynx/config/mikrotik.php`
```
; <?php exit(); ?>
; Do not remove this lines
; Splynx Mikrotik API config file

[1]
dhcp_leases['address'] = '{ip}';
dhcp_leases['mac-address'] = '{mac}';
dhcp_leases['comment'] = 'SpLUser_{customer_id}-{service_id}';
dhcp_leases['server'] = '{customer_additional_route}';
```

### Standart rules

#### dhcp_leases
```
dhcp_leases['address'] = '{ip}';
dhcp_leases['mac-address'] = '{mac}';
dhcp_leases['comment'] = 'SpLUser_{customer_id}-{service_id}';
```

#### filter_rule_1
```
filter_rule_1["chain"] = "forward"
filter_rule_1["action"] = "accept"
filter_rule_1["src-address"] = "{ip}"
filter_rule_1["src-mac-address"] = "{mac}"
filter_rule_1["comment"] = "SpLUser_{customer_id}-{service_id}-1"
```


#### filter_rule_2
```
filter_rule_2["chain"] = "forward"
filter_rule_2["action"] = "accept"
filter_rule_2["dst-address"] = "{ip}"
filter_rule_2["comment"] = "SpLUser_{customer_id}-{service_id}-2"
```

#### hs_users
```
hs_users["name"] = "{login}"
hs_users["password"] = "{password}"
hs_users["profile"] = "default"
hs_users["address"] = "{ip}"
hs_users["mac-address"] = "{mac}"
hs_users["comment"] = "SpLUser_{customer_id}-{service_id}"
```

#### ppp_secrets
```
ppp_secrets["name"] = "{login}"
ppp_secrets["password"] = "{password}"
ppp_secrets["profile"] = "default"
ppp_secrets["service"] = "any"
ppp_secrets["remote-address"] = "{ip}"
ppp_secrets["routes"] = "{routes}"
ppp_secrets["comment"] = "SpLUser_{customer_id}-{service_id}"
```

#### simple_user
```
simple_user["name"] = "SpLSQ_{customer_id}-{service_id}"
simple_user["max-limit"] = "{out}/{in}"
simple_user["limit-at"] = "{out_at}/{in_at}"
simple_user["priority"] = "{priority}/{priority}"
simple_user["target-addresses"] = "{ip}"
simple_user["burst-limit"] = "{b_out}/{b_in}"
simple_user["burst-threshold"] = "{bt_out}/{bt_in}"
simple_user["burst-time"] = "{b_time}/{b_time}"
simple_user["queue"] = "{qs}"
simple_user["comment"] = "{login}"
```

#### simple_tree_user
```
simple_tree_user["name"] = "SpLSTQ_{customer_id}-{service_id}"
simple_tree_user["max-limit"] = "{out}/{in}"
simple_tree_user["limit-at"] = "{out_at}/{in_at}"
simple_tree_user["priority"] = "{priority}/{priority}"
simple_tree_user["target-addresses"] = "{ip}"
simple_tree_user["burst-limit"] = "{b_out}/{b_in}"
simple_tree_user["burst-threshold"] = "{bt_out}/{bt_in}"
simple_tree_user["burst-time"] = "{b_time}/{b_time}"
simple_tree_user["queue"] = "{qs}"
simple_tree_user["comment"] = "{login}"
```
