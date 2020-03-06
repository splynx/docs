CPE management
==========


Splynx has the ability to manage CPE's (Customer Premise Equipment). At the moment this feature is limited to MikroTik equipment.

To add a CPE to a customer profile, navigate to the respective customer that the CPE belongs to and click on the CPE tab. If a CPE has not been configured for the customer, you will be presented with the window to add one. Simply fill in the required details and click *Add*

![Customer](select_customer.png)

**Title** - name of the CPE<br>
**IP/Host** - IP address which Splynx can reach the CPE on<br>
**Login (API)** - username of the API user on the Mikrotik router<br>
**Password** - password of the API user on the Mikrotik router<br>
**Port(API)** - API port used to access the router<br>
**Type** - type of device (manufacturer)<br>
**Qos/Shaping** - enable or disable Qos rules<br>
**Qos Target** - Target IP the QOS will be applied to<br>
**Service** - Select the service which local queues will be based on & QOS rules will applied to<br>

If all data is entered correctly the status of the device will show <icon class="image-icon">![API OK](apiok.png)</icon> , if there is a problem with the credentials you will see <icon class="image-icon">![API Error](apierror.png)</icon>


Once the CPE is successfully added to the system, it will display the CPE status, providing  information about API status, board name, version CPU and last updated status.

![Status](cpe_status.png)

In addition, you can also check interfaces of the CPE by clicking on <icon class="image-icon">![Status](status_button.png)</icon>, this will display information about rates, data transmitted/received, errors and status of the interface.

![ETH1](eth1.png)


Once the CPE is connected, we are able to set QoS rules to prioritize and guarantee outgoing services. For example, we can set a rule to prioritize VOIP traffic and guarantee a minimum speed. DST address is the external location where the internal traffic is sent/received to/from.


![Add QoS](add_qos_button.png)

![Create QoS](create_qos.png)

Priority 8 is the lowest priority, 1 is the highest.

CPE management allows control over the WLAN settings. If the CPE has a built-in WLAN the system will automatically add the AP. The WLAN configuration is editable and we are able to make changes from Splynx to settings like the SSID, password, interface, protocol, mode, security, encryption and disable the WLAN.

![WLAN edit](wlan_edit_button.png)

![Edit AP](edit_ap.png)

The other way is to add it manually and set all information.

![WLAN add](wlan_add_button.png)

![Create AP](create_ap.png)

We can create backups of the CPE if the FTP service on the router is enabled - this is especially useful for restoring a backup in case of device failure.

![Backup button](CPE_backup_button.png)

We can download the backups and also view the differences between different versions of backups.

![CPE Backups](cpe_backups.png)

Finally, you can enable and configure a DHCP server on the CPE and set interface, network, pool etc.

![DHCP](dhcp.png)
