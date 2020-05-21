IP address management
==========

IP addresses are used in every corporate or ISP network. They are an essential component of  networking. There are several ways to manage IP address assignments. Many administrators, even in large companies, are still using Excel sheets due to a lack of smart IP address management tools. We recommend our engine for IP address management to ease the pressure on administrators and improve overall efficiency. This module is connected to the customer database in Splynx. When Splynx assigns an IP address or subnet to a customer for their access, the IP's will be assigned in the IP address management tab as well. The main advantage of this is avoiding IP conflicts when several customers get the same IP or an IP with the wrong range. Also, you always have an overview of the current state of your subnets.

#### How to configure IPAM in Splynx:

1. Create a root network and subnetworks.

  Create a large root network and add subnetworks to it. The root network is marked with the color yellow. For example, 172.16.0.0/9 is a root network and all /24 are end networks. From the Root network, it is not possible to assign any IP's as it is used as a parent for all real networks.

  IP addresses within the selected subnetwork are displayed in a table:

  ![Subnet list](subnet_list.png)


2. We can statically define what a certain IP address is used for. When you assign an IP address to a customer, it is locked in the IP address management tool, and if you try to assign an IP that has already been used, the system will prevent this.

  ![IP](ip.png)


3. As an extra feature, you can send a Mass ping to devices in the selected network, split the network into smaller subnets or merge the network into one large one. You can switch to a graphical map view with icons to get quick access to information. All red icons mean that the IP address is not responding to the Mass ping.

  ![network overview](net_overview.png)


There is also the ability to customize the colors and types of devices, as well as adding new types of equipment.

Below is an example of how to visualize small networks /29,/28 etc, in one common /24 network

![Customize](customize.png)
