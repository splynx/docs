Openserve authentication (PTA Method)
==========

South African provider Telkom allows ISPs to resell their services. The services are sold under the Openserve trademark (https://openserve.co.za/). Splynx can communicate with Openserve proxy servers and authenticate PPPoE customers. A few configuration steps are needed to allow Splynx to be able to communicate with Openserve proxies.


1. First of all, create a NAS type as Openserve or a similar name that will help you to recognise it as the Openserve server. To do this, navigate to `Config -> Networking -> NAS types` and click on the "Add" button:

![add_nas](add_nas_type.png)

2. Configure the "Openserve" NAS type under `Config -> Networking -> Radius`:

![configure_radius](radius_settings.png)

 Please add Radius attributes provided to you by Telkom. Please setup accounting intervals to the default SAIX intervals :
![settings_1](radius_settings_1.png)
![settings_2](radius_settings_2.png)
![settings_3](radius_settings_3.png)

Example of Radius attributes:

```
Cisco-AVPair = ip:ip-unnumbered=Loopback1111
Cisco-AVPair += ip:addr-pool=xnet001ipc2
X-Ascend-Client-Primary-DNS = 196.46.XXX.XXX
X-Ascend-Client-Secondary-DNS = 196.46.XXX.XXX
```

Don't forget to save the changes.

3. Then add all Openserve NAS proxies as Routers to Splynx, please specify the NAS type = Openserve (configured in previous step). Also define the Radius secret that is used for proxy server and Radius server communication:

![router](router.png)


4. Next step is to edit Radius extended settings under `Config -> Networking -> Radius extended`

![go_to_advanced](radius_advanced.png)

![advanced](default_nas.png)

An important field is **Default NAS Id**. This is the ID of the Router in Splynx routers, that will "link" customers - to show that they are connected through it online.


5. The Last step is to add the missing attribute to the Freeradius dictionary, open the file `/etc/freeradius/dictionary` and add the line :
```
ATTRIBUTE Alcatel-Lucent-Service- 3002 integer
```

More information on this connection method can be found [here](RADIUS_Authentication_Information_For_IPC_Customers.pdf).

#Openserve authentication (PPPoE via L2tP Method)#

1. The technical documentation should be completed and sent to the Corporate account manager
2. L2TP LNS IP should advertised accross BGP to Openserve on the upstream
3. Establish the L2TP tunnel from your core device to Openserve.
4. The accepted Realms should be created on Openserve portal.

*Example config* 

***PPPOE to L2TP Basic Configuration***
```
/ppp l2tp-secret
add address=196.43.32.128/25 comment=OpenServe secret=<secret>
/interface l2tp-server server
set allow-fast-path=yes authentication=chap default-profile=<profile-name> enabled=yes keepalive-timeout=60 max-mru=1462 max-mtu=1462
```
Once the L2TP is established the PPPoE Realm in the CPE config and in Splynx' services should match that of what's configured in the Openserve portal.

You should now be able to establish the PPPoE across the L2TP connection by using normal Radius config as seen here [here](https://docs.splynx.com/networking/authentication_of_customers/mikrotik_pppoe_radius)
