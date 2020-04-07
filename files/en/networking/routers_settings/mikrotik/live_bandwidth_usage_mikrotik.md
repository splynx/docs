### Mikrotik Live bandwidth usage

Implemented in Splynx 3.0 we have a new feature called "Live bandwidth usage" which can be used in conjunction with Mikrotik devices.

Requirements:
1. Radius authorization required;
2. API configured and enabled for a router;
3. NAS Type - Mikrotik only;
4. ROS should be newer than 6.43.


![Routers](routers_list.png)
Navigate to the "Edit" section of the router and select the tab "Mikrotik"

![Mikrotik tab](mikrotik_tab.png)

API should be configured and enabled, API status should be "OK" and running the “Test API connection” button should return successfully.

Click on the "Live Bandwidth usage" button to see the per-interface graph of the router:

![Router live graph](router_graph.png)

If the graph is available on the router - a customer who is connected to this router will also have this graph under the Statistic tab:

![Online customers](customers_online.png)

Navigate to a customer view and select "Statistics" tab:

![Customer graph](graph_customer.png)

If there’s no usage on the line - the graph will not populate.

*NOTE! If the graph on a router is available and for a customer, it's not. You can run the following command by logging into your server via SSH:*

**sudo service splynx_node restart**

If after restart of this module graph for customer still not available - create a ticket with this issue.

Another reason for this could be that the authentication is set to API - only Radius authentication will provide this graph.
