Network Weathermap Editor
=========================

To create a new map open the editor tool in Splynx under `Config → Networking → Network Weathermap`:

![Settings](menu.png)

![Welcome](welcome.png)


Define the name for the new MAP and create it. The new map "map1" was created and it is now empty:

![Map](map.png)


You need to have a device(s) added to the system. Weathermaps work with equipment that has been added to `Networking → Monitoring`. Therefore, to generate a visualization of the network, we need to add devices to Monitoring and configure their SNMP OIDs for interface traffic, CPU's, etc. Once devices are added, we can create a node clicking on *Add Node*, and then place it somewhere on the map.

![Map](map2.png)

To configure node settings click on the node, you can set the position, label, which device it is, graphs and the icon.

![Node properties](node_properties.png)

Then we can add a link between two nodes by clicking on *Add Link*:

![Map](map3.png)

![Map](map4.png)


Click on the link to configure it:

![Link properties](link_properties.png)


 It is possible to add graphs of the link and view them by hovering the mouse on the link. To add graphs, navigate to `Networking → Monitoring → List` and select the device you want to add graphs for:

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
