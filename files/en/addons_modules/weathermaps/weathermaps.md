Weathermap add-on
==========

To install network weathermaps run the following commands in the CLI of your server:
```
apt update
apt install splynx-network-weathermap
```

Or install the add-on in `Config → Integrations → Add-ons`:

![install](addon_install.png)

## Creating a new map

To create a new map, open the editor tool in Splynx under `Config → Networking → Network Weathermap`:

![Settings](menu.png)

![Welcome](welcome.png)


Define the name for the new MAP and create it. The new map "map1" was created and it is now empty:

![Map](map.png)


You need to have a device(-s) added to the system. Weathermaps work with equipment that has been added to `Networking → Hardware`. Therefore, to generate a visualization of the network, we need to add devices to Monitoring and configure their SNMP OIDs for interface traffic, CPU's, etc. Once devices are added, we can create a node clicking on *Add Node*, and then place it somewhere on the map.

![Map](map2.png)

To configure node settings click on the node, you can set the position, label, which device it is, graphs and the icon.

![Node properties](node_properties.png)

Then we can add a link between two nodes by clicking on *Add Link*:

![Map](map3.png)

![Map](map4.png)


Click on the link to configure it:

![Link properties](link_properties_3.png)


 It is possible to add graphs of the link and view them by hovering the mouse on the link. To add graphs, navigate to `Networking → Hardware → List` and select the device you want to add graphs for:

 ![Graph](graph.png)


 Then, define the title, and select a router, and the parameter you want to visualize:

 ![Graph](graph2.png)


 You will be able to see the graphs under `Networking → Network Weathermap`, by hovering over the devices or links, as depicted in the image below:

![Hold graph](hold_graph.png)


To view the legend, click on Position Legend and then click somewhere on the map, the legend will appear where you've clicked.

![Legend](legend.png)


It is also possible to edit the Map Properties and Style, where we can change a few settings of the Map:

![Map properties](map5.png)

![Map style](style.png)

## Networking

After successfully installing this feature, the Network Weathermap menu will appear under `Splynx → Networking`.


We've integrated a productive open source tool https://network-weathermap.com to Splynx. It is installed as a module and connected via API to our platform.

![Weathermap](Weathermaps.png)


To create a new map, open the editor tool in Splynx under `Config → Networking → Network Weathermap Editor`.

![Config weathermap](Weathermap_Editor.png)


Choose a name for the new MAP and create it. The first map was created and it is now empty.

![Map](Weathermap_map.png)


Let's add a device. Weathermaps works with the equipment which is added to `Networking → Hardware`. Therefore, to get a visualization of the network, we need to add devices to Hardware and configure their SNMP OIDs for interface traffic, CPU and similar values.

![Monitoring](Weathermap_monitoring.png)

Once the device is added to Hardware, we can now add the SNMP OID values and configure values to create graphs in Splynx:

![OIDs](Weathermaps_OIDs.png)

![edit](edit_graph.png)

![Graph](Weathermap_graphs.png)


When all devices are properly configured in Hardware, we can add them to the Weathermap. All configurations in the editor is very simple and straightforward: simply drag and drop to place the routers/devices on the map and connect the links.

![NodeProperties](Weathermap_config.png)


You can choose the device from the Splynx hardware list, define what will be shown as a main chart for the device and assign a picture for the element on the map.

![CPU](Weather_CPU.png)


When the router is added, we can add a second device and configure a link between our two devices. We've added a device "Internet" and will configure the link WAN, OIDs of this link we have on our LAB_AP router.

![Link](Weather_link.png)


We do not have to look for OIDs. Simply choose the OID from the link, and setup the chart you want to display as hover chart of the link and the main chart which will show the complete usage of the link on a separate page.

![Link properties](link_properties.png)


Once these steps have been completed, we can navigate back from configuration mode to view mode and check if the new picture was generated (please note that the topology map is generated every 5 minutes).

![Weathermap](weathermap1.png)


The legend shows the traffic loads. On the example, we can see that the Download on the LAB router is using almost all of the 10 Mbps available.

Charts are available in hover mode, topology can also be opened in a new window (which displays the usage for the last hour on the link):

![Weathermap](weathermap2.png)


If we click on the link, a new window will open with historical charts, showing usage per week, month and year:

![Graph](rrd_graph.png)
