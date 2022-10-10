Radius Proxy Accounting
=======================

Splynx has the abillity to proxy<sup>[[1]](#one)</sup> RADIUS accounting packets to another RADIUS server. In this case, customers' traffic will be accounted on more than one RADIUS server.

## Radius Accounting process
During RADIUS authorization, if the customer is allowed to connect, the RADIUS server<sup>[[2]](#two)</sup> sends a **RADIUS-Accept** packet to the NAS<sup>[[3]](#three)</sup> with an **Acct-Interim-Interval** Attribute (among other attributes). This attribute contains the number of seconds, of how frequently the NAS should send traffic usage updates<sup>[[4]](#four)</sup> to the RADIUS server.
You can change this time in Splynx under *Config → Networking → Radius → (choose NAS type) → Load → Accounting interval (in sec)*.

![(image)](1.png)

## Radius Proxy Accounting

After a session starts, the NAS sends traffic statistics every **Accounting interval (in sec)** seconds, as  mentioned. If you enable **Proxy accounting** under *Config → Networking → Radius advanced*, Splynx will copy these RADIUS Accounting packets to the _IP:Port_ specified in the **Radius host** field.

![(image)](2.png)

## Splynx as Remote RADIUS Accounting server
To use Splynx as a Remote RADIUS Accounting server, create a Router under **Networking → Routers**.

![(image)](3.png)

**IP/Host** - IP address (hostname) of the Splynx proxy server.
**NAS IP** - IP address of the router (NAS)

***
<a name="one"></a>[1] RADIUS Proxy Accounting behaviour in Splynx is a bit different from the descriptions in [RFC 2866](https://tools.ietf.org/html/rfc2866). Splynx RADIUS server answers to the NAS immediately and simply copies Accounting data to the other server. "Classic" RADIUS Proxy Accounting servers, first sends Accounting Request to the remote server and only answers to the NAS after the Accounting Accept is received from the remote server.
<a name="two"></a>[2] Splynx server.
<a name="three"></a>[3] Network Access Server, **Router** in Splynx terminology.
<a name="three"></a>[4] Interim-Updates
