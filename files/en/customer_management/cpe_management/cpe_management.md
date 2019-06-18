CPE management
==========


Splynx is able to manage Customer Premises Equipment, and apply some QoS rules. At the moment it works only on MikroTik.


To add CPE choose the Customer who owns this equipment and set IP and Login/Password of API. Select service customer is using with that CPE and enable QoS if you'd like to set some rules.

![Customer](select_customer.png)

If all data is correct, you will see the signal of CPE.

![Signal strength](signal_strength.png)


Once CPE is connected, we can set some QoS rules to prioritize and guarantee some services. For example, we set a rule to prioritize VOIP traffic and guarantee a minimum speed.

![Add QoS](add_qos_button.png)

![Create QoS](create_qos.png)


CPE management allows to control some WLAN settings. In this case the WLAN settings appear in the box. WLAN is editable and we can make changes from Splynx, for example, change SSID, password, interface, protocol, mode, security, encryption and disable it.

![WLAN edit](wlan_edit_button.png)

![Edit AP](edit_ap.png)


The other way is to add it manually and set all information.

![WLAN add](wlan_add_button.png)

![Create AP](create_ap.png)


Another feature is managing of CPE status, it shows information about API status, board name, version CPU, last status, and also you can check interfaces by clicking on  <icon class="image-icon">![Status](status_button.png)</icon>.

![Status](cpe_status.png)


It's posible to see information about rates, data trasmited/recieved, erros and status.

![ETH1](eth1.png)


Finally, you can enable DHCP server from CPE and set interface, network, pool and other features.

![DHCP](dhcp.png)
