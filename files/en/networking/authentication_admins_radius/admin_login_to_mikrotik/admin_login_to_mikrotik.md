Admin login to Mikrotik routers
==========

It is possible to authenticate administrators locally on the router or using the Splynx Radius server.

To configure the Radius Server, click on `Config → Networking → Radius` and click on load at the bottom of the page.

![Radius](radius.png)

![Load](load.png)

Turn the mode Use admin login on:
![Radius](radius2.png)

Select the router you want to configure with Radius. Click on `Networking → List`, select the router and write down the Radius secret password that is going to be used in the router Radius configuration.

![Radius secret](radius_secret.png)

Open Winbox, click on System → User and the User List window will pop up. Click on AAA (Authentication and Accounting), flag Use Radius.
![Radius secret](aa.png)


Click on `System → User`, the User List window will pop up. Select the tab *Active Users*, click on Radius, click on the default service and flag the Radius service you want to use: *ppp, hotspot, dhcp, login*. Insert the Radius Server, the Radius secret password, the source address of the interface connected to the Radius server.

![Radius source](radius_source.png)

In Splynx, click on `Administration → Administrators`, click on Add and fill up the administrator's fields.

![Administrators](administrators.png)

![Create administrator](create_admin.png)

It is possible to chose **the role of the administrator:** Administrator, Customer Creator, Financial Manager, Manager, Super Administrator. In Router access (radius) the default permission are: read, write, full.

It is possible to edit, change the permissions or delete the administrator with ![Icons](conf_administrator.png).

Now, if you try to connect the new Administrator to the winbox-router, you will see the new user created with the Radius server in User list.

![Sysadmin](sysadmin.png)

It is possible to see all operations of each Administrator. Click on `Administration → Logs → Operation`.

![Logs](logs_operations.png)


If you click on ![](operation_details.png), you will see a pop up window with the operation in details.
![Operation details](operation_details2.png)


If you need a short log of the Radius login, click on `Administration → Logs → Operation` and click on the icon ![Operation details](logs_files_actions.png)

![Logs](logs_operations.png)
![Radius shortlog](radius_shortlog.png)
