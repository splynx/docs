PPTP Connection between Splynx and Mikrotik
==========

If Splynx and your Mikrotik router, are on different networks, the solution to this scenario is through creating a PPTP tunnel between the two.


### Configuration on Splynx:

First install the pptp server. In the CLI of your Splynx server, run the following command:

```
sudo apt install pptpd
```

Then you have to add the DNS servers, you can do this with the following command:
```
nano /etc/ppp/pptpd-options
```
Once the editor has opened, change the following:
```
#ms-dns 10.0.0.1
#ms-dns 10.0.0.2
```
To the addresses below:
```
 ms-dns 8.8.8.8
 ms-dns 8.8.4.4
```


After that you have to add the pptp secrets. This can be done with the following command:

```
nano /etc/ppp/chap-secrets
```
Here you can Add users and secrets as depicted below:

```
# Secrets for authentication using CHAP
# client   server      secret             IP addresses

user1      *           user1-password     *

user2      *           user2-password     *
```

Now you have to allocate local and remote IP's. Run the following command:

```
nano /etc/pptpd.conf
```
Then Add or Edit the following.
```
localip X.X.X.X
remoteip X.X.X.X-X
```

Then in the file:

```
nano /etc/sysctl.conf
```
Uncomment the following line.

```
net.ipv4.ip_forward = 1
```

Save the changes:
```
sudo sysctl -p
```

---
Configure the Firewall for IP Masquerading.

```
sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
```

Restart pptp daemon to apply changes.
```
sudo /etc/init.d/pptpd restart
```

---
Also you have to add static routes to your local network ranges, that will point to the tunnel interface, for example :
```
route add -net 10.0.1.0 netmask 255.255.255.0 gw 172.16.200.2
```
Where 10.0.1.0/24 is the local network and 172.16.200.2 is the IP address of interface (or it can be set to ppp0)



### On the Mikrotik router side:

```
/interface pptp-client

add connect-to=localserverIP disabled=no name=pptp-out1 password=user1-password user=user1
```
