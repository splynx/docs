DSL Telkom (Openserve) authentication
==========

South African provider Telkom allows smaller ISPs to resell their services. The services are sold under the Openserve trademark (http://openserve.co.za/). Splynx can communicate with Telkom/SAIX proxy servers and authenticate PPPoE DSL customers. But a few configuration steps are needed to allow Splynx to be able to communicate with Openserve proxies.


1. First of all, create a NAS type as DSL_Telkom or a similar name that will help you to recognise it as the Openserve server. Please add Radius attributes provided to you by Telkom. Please setup accounting intervals to the default SAIX intervals :
![NAS type](nas_type.png)


2. Then add all proxies as Routers to Splynx software, please specify the NAS type = DSL_Telkom (configured in previous step). Also define the Radius secret that is used for proxy server and Radius server communication.


3. Next step is to edit Radius extended settings under *Config / Networking / Radius extended*:

![(picture)](pic1.png)

An Important field is **Default NAS Id**. This is the ID of the Router in Splynx routers, that will "link" customers - to show that they are connected through it online.


4. The Last step is to add the missing attribute to the Freeradius dictionary, open the file `/etc/freeradius/dictionary` and add the line :
```
ATTRIBUTE Alcatel-Lucent-Service- 3002 integer
```

This setup is supported by Splynx version 1.x and 2.x, and Freeradius 2 and Freeradius 3 daemons.
