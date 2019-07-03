CPE management
==========


Splynx is able to manage CPE (Customer Premises Equipment), and apply some QoS (Quality of Service) rules. At the moment this feature is limited to MikroTik equipment.

To add a CPE choose the Customer where the CPE is located and set the IP and Login/Password of API user (remember to add this user on the device). Select the service the CPE is assigned to and enable QoS if you'd like to set some rules.

![Customer](select_customer.png)

If all data is entered correctly, you will be able to see the status of the device.

![CPE Status](cpe_management_status.png)

Once the CPE is connected, we can set some QoS rules to prioritize and guarantee some outgoing services. For example, we can set a rule to prioritize VOIP traffic and guarantee a minimum speed. DST address is the external location where the internal traffic is sent/received to/from.

Priority 8 is the lowest priority, 1 is the highest.

![Add QoS](add_qos_button.png)

![Create QoS](create_qos.png)


CPE management allows control over the WLAN settings. If the CPE has a built-in WLAN the system will automatically add the AP. The WLAN is editable and we can make changes eg. SSID, password, interface, protocol, mode, security, encryption and disable it.

![WLAN edit](wlan_edit_button.png)

![Edit AP](edit_ap.png)

The other way is to add it manually and set all information.

![WLAN add](wlan_add_button.png)

![Create AP](create_ap.png)

It's possible to view the CPE status, it displays information about API status, board name, version CPU, last status, and also you can check interfaces by clicking on <icon class="image-icon">![Status](status_button.png)</icon>.

![Status](cpe_status.png)

It's possible to see information about rates, data transmitted/received, errors and status.

![ETH1](eth1.png)

We can create backups of the CPE if the FTP service on the router is enabled - this is especially useful for restoring a backup in case of device failure.

![Backup button](CPE_backup_button.png)

We can download the backups and also view the differences between different versions of backups.

![CPE Backups](cpe_backups.png)

Finally, you can enable DHCP server from CPE and set interface, network, pool etc.

![DHCP](dhcp.png)
