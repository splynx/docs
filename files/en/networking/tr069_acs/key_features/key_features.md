Key features
==========

<details>
<summary><b>Relation with inventory</b></summary>
<p markdown="1">
It is possible  to **assign device by ACS identifier (Barcode or Serial number) to customer** before device establishes first connection to ACS. Splynx checks for some value in a field `Barcode` of inventory item, if `Barcode`, on the first connection, matches with `Serial number` device field - customer will be linked automatically. If field `Barcode` is empty or does not match `Serial number` of a device - in this case field `Serial number` will be used from inventory item. In this way you can add an inventory item with a barcode or serial number specified and assign it to a customer:

![item](inventory_item.png)

After this you can setup some group and auto provisioning, for example to push PPPoE login & password, WI_FI SSID & password on first connect. During the first connection a TR-069 device will be automatically assigned to a customer and an initial configuration will be pushed:

![group_mikrotik](group.png)

and after first connect:

![first](device_assigned.png)

</p>
</details>

------------

<details>
<summary><b>Device management by customer from Portal page</b></summary>
<p markdown="1">
The customer can **reboot the router and change SSID and Wi-Fi password for assigned devices** directly from portal page on menu `Service → Hardware`:

![manage](device_on_portal.png)

</p>
</details>

------------
