Network Weathermap Editor
=========================

To create a new map open editor tool in Splynx `Config → Networking → Network Weathermap`:

![Settings](menu.png)

![Welcome](welcome.png)


Choose the name for new MAP and create it. New map "map1" was created and it's empty now:

![Map](map.png)


You need to have a device added. Weathermaps work with equipment which is added to `Networking → Monitoring`. So, to get some visualisation of the network we need to add devices to Monitoring and configure their SNMP OIDs for interface traffic, CPU etc.. Once devices are added, we can create a node clicking on Add Node, and then click somewhere on map.

![Map](map2.png)

To configure node settings click on the node. There you can set position, label, which device it is, graphs and the icon.

![Node properties](node_properties.png)

Then we can add a link between two nodes clicking on *Add Link*:

![Map](map3.png)

![Map](map4.png)


Click on the link to configure it:

![Link properties](link_properties.png)


 It's posible to add graphs of link and view them hovering the mouse on the link. To add graphs go to `Networking → Monitoring → List` and select the device you want to add graphs:

 ![Graph](graph.png)


 Then, write the label name, and select router and parameter you want to visualize:

 ![Graph](graph2.png)


 Then you can see graphs going to `Networking → Network Weathermap`  and hovering on devices or links, as it's shown in the following screenshot:

![Hold graph](hold_graph.png)


To view the legend click on Position Lengend and then click somewhere on the map. The legend will appear.

![Legend](legend.png)


Also it's posible to edit Map Properties and Map Style, where we can change some settings:

![Map properties](map5.png)

![Map style](style.png)
