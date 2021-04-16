Mikrotik: DHCP with Radius
==========

### Step 1 - Configure RADIUS server on a router

First of all we need to configure the RADIUS server on the router to communicate with Splynx.

![radius_server](radius_server.png)

In this case 10.250.32.1 is the Splynx server IP and 10.250.32.2 is the router IP. The RADIUS secret should be specified in the `Secret` field - we will use this in Splynx in the router settings and then enable the `DHCP` service.

Lastly we need to enable `RADIUS incoming`:

![incoming](radius_incoming.png)

### Step 2 - Configure DHCP server on a router

We can setup the DHCP server manually or using the setup wizard.

![dhcp_server](dhcp_server.png)

The main options here are: `Address pool=static-only` (it means that Splynx (Radius server) will assign the IP) and `use RADIUS=yes`. Specify the name, correct interface, lease time and save the settings.

### Step 3 - add new router in Splynx

Now we need to add a new router in Splynx under _Networking -> Routers -> Add_ :

![router](router_in_splynx.png)

The main parameters here are:

1. **IP / Host** - IP of the router;

2. **Authorization / Accounting** - PPP/DHCP (Radius) / Radius acounting;

3. **Radius secret** - the same as the RADIUS secret on the router;

4. **NAS IP** - IP of the router.

### Step 4 - create IP network in Splynx

#### IP assignment - static IPs (recommended)

In case you will use static IPs in Splynx you need to navigate to _Networking / IPv4 Networks / Add_ and add a network with `Type of usage = static`:

![ip_network](ip_network_static.png)

#### IP assignment - assign IP from pool

In this case we need to create IPv4 network with `Type of usage = Pool`:

![pool](make_network_pool.png)

### Step 5 - add the internet service for a client

#### Static IP (recommended)

Under _Customers -> List_ select the customer, open the _Services_ tab and add a new internet service with following networking parameters:

![client_service_mac_static](client_service_1mac_static.png)

Select `IPv4 assignment method = Permanent IP(from static IPs)`, select the IP address and specify the MAC address of the interface on the CPE that will be receiving the IP.

Once this done the client should be connected:

![lease_mac1](lease_mac1.png)

On the router under the _Leases_ tab we can see the DHCP lease with the IP that we specified in Splynx.

In Splynx we can see that customer is online.

![online](online_in_splynx.png)

We can add more MAC addresses to the service field _MAC(s)_ separated by a comma:

![client_service_mac2_](client_service_2mac_static.png)

So a customer connection with the second MAC address can be authenticated:

![](lease_mac2.png)

Blocking of static IP customers will be performed using their own static IP in the address list. More information about customer blocking here - [Blocking of customers in Splynx](networking/blocking_customers/blocking_customers.md)

#### IP from pool

Under _Customers -> List_ select the customer, open the _Services_ tab and add a new internet service with following networking parameters:

![ip_from_pool_](service_assign_pool.png)

and this connection will receive an IP from the specified pool:

![](lease_pool.png)

Some advanced parameters for RADIUS can be configured under [Config/Networking/Radius](../../../configuration/network/radius/radius.md) and [Config/Networking/Radius Extended](../../../configuration/network/radius_extended/radius_extended.md).

Blocking of customers will be performed with using of reject IP pools in the address list. More information about customer blocking here - [Blocking of customers in Splynx](networking/blocking_customers/blocking_customers.md)

### Please note!

For DHCP to report accounting correctly queues have to be applied dynamically via radius. API queues will not report the accounting stats to Splynx.

### Troubleshooting

#### Additional network issue for services with static IPs

If you set additional network(s) in Splynx internet services, network routes will be sent to the router (NAS) during authorization. The router will then send all traffic with destination=additional network to the customer device. It is possible that these routes will also appear on the customer's device. To fix this issue, set use-framed-as-classless to disabled in the DHCP server settings:

![use-framed](use_framed.png)
