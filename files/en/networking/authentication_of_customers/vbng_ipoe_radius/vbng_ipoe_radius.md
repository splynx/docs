netElastic vBNG: IPoE, Radius configuration
==========
In this article will be shown the configure of virtual **Broadband Network Gateway (vBNG)** solution from [netElastic](http://www.netelastic.com/) along with its integration with Splynx ISP Framework. This solution can be used to complete AAA (Authentication, Authorization & Accounting) coverage of your customers via Splynx Radius server. Successful IPoE connections rely on the DHCP server running with vBNG to assign IP address.

Let's say that we have already installed the instances of vBNG Router, vBNG Manager and Splynx. In our demo we will create a test user with certain parameters using our Splynx and then, connect him over IPoE session to Internet through vBNG device.


![](img_1.png)

To provide an IPoE connection for a customer using *vBNG (Virtual Broadband Network Gateway)*, we first need to connect such gateway to the Splynx radius server.

The process of configuring IPoE connections on the vBNG with Radius authentication, authorization and accounting involves the following steps:

1. Configuring access interface: VCI, VGI interfaces
2. Creating a domain, Authentication template, Radius Authentication group
3. Creating AAA Accounting template
4. Creating AAA Authorization template
5. Creating a IPoE template

------------

##### STEP 1 - Configuring access interface: VCI, VGI interfaces

How to install vBNG software and configure interfaces, you can find in its official [documentation](authentication_of_customers/vbng_ipoe_radius/netElastic_vBNG_Service_Configuration_Guide.pdf).

In our example we use Splynx with IP: `139.59.xxx.yyy` and vBNG with IP: `108.217.xxx.yyy`

In Splynx, open `Config → Networking → NAS-types` and add a new NAS-type - *netElastics*:

 ![](img_2.png)

After that add your vBNG to Splynx routers and get radius secret to connect it with Splynx. vBNG software has the two methods to send attributes to radius server

 ![](img_3.png)

 ![](img_4.png)

In our case, we should use the `method 2` to connect customers to Splynx. On the screenshot below we can see a request what was send from vBNG to Splynx

 ![](img_5.png)

 After you connect your vBNG to the Internet you should configure a LAN interface to which you plan to connect the customers. In this example you can see all interfaces' configurations such as: VCI interface, VGI1, WAN and gei-1/1/5 interface to which customers will be connected.

 ![](img_6.png)

##### STEP 2 - Creating a domain, Authentication template, Radius Authentication group

 On this screen you an see full domain configuration and authentication template what bind to domain

 ![](img_7.png)


Create an authentication group in order to point the IP address of radius server and the IP of your router

 ![](img_8.png)


 On the screenshot below you can see an authentication template configuration

 ![](img_9.png)


##### STEP 3 - Creating AAA Accounting template

Next step is to configure the radius accounting template

![](img_10.png)


##### STEP 4 - Creating AAA Authorization template

Then, create the authorization template:

![](img_11.png)


##### STEP 5 - Creating a IPoE template


After you created the previous templates and bind them to your domain you should configure IPoE template to use it for customers as well

![](img_12.png)


Finally, double check all your configurations, from *interfaces* to *domain* one.

------------

**The test example of all configuration** you can find [here](networking/authentication_of_customers/vbng_ipoe_radius/currentConfig.txt)
