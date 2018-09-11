PPTP Connection between Splynx and Mikrotik
==========

If Splynx and Mikrotik are in diferent networks, there is a solution to work as if they were in the same. The way to do it is throught a PPPTP tunel.


### On Splynx:

First install pptp server.
```
sudo apt install pptpd
```

Then you have to add DNS servers. Set the command:
```
nano /etc/ppp/pptpd-options
```
change
```
#ms-dns 10.0.0.1
#ms-dns 10.0.0.2
```
to
```
 ms-dns 8.8.8.8
 ms-dns 8.8.4.4
```


After that you have to add pptp secrets. Set the command.

```
nano /etc/ppp/chap-secrets
```
Add users like in the next table.

```
# Secrets for authentication using CHAP
# client   server      secret             IP addresses

user1      *           user1-password     *

user2      *           user2-password     *
```

Now allocate local and remote IP's.
```
nano /etc/pptpd.conf
```
Add / Edit.
```
localip X.X.X.X
remoteip X.X.X.X-X
```

And in that file:
```
nano /etc/sysctl.conf
```
Uncomment next line.
```
net.ipv4.ip_forward = 1
```

Save changes:
```
sudo sysctl -p
```

---
Configure Firewall for IP Masquerading.
```
sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
```

Restart pptp daemon to apply changes.
```
sudo /etc/init.d/pptpd restart
```

---
Also you have to add static routes to your local network ranges, that will point to tunnel interface, for example :
```
route add -net 10.0.1.0 netmask 255.255.255.0 gw 172.16.200.2
```
Where 10.0.1.0/24 is the local network and 172.16.200.2 is the IP address of interface (or it can be set to ppp0)



### On Mikrotik side:
```
/interface pptp-client

add connect-to=localserverIP disabled=no name=pptp-out1 password=user1-password user=user1
```
