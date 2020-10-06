# Accel-PPP with IPoE

This is an example how Splynx can be used with Accel-PPP to authenticate customers via IPoE. In this manual we use VLAN monitoring module to dynamically create VLANs for customers. This is also known as 'VLAN per user'.

### Accel-PPP installation

For Accel-PPP we need a separate server or virtual machine with Ubuntu 20.04 installed.  
Login as root:

```
sudo su -l
```

Install required packets:

```
apt update && apt install -y build-essential cmake gcc linux-headers-`uname -r` git libpcre3-dev libssl-dev liblua5.1-0-dev
```

Clone Accel-PPP code from Github:

```
git clone https://github.com/xebd/accel-ppp.git /opt/accel-ppp-code
```

Compile Accel-PPP code:

```
mkdir /opt/accel-ppp-code/build
cd /opt/accel-ppp-code/build/
cmake -DBUILD_IPOE_DRIVER=TRUE -DBUILD_VLAN_MON_DRIVER=TRUE -DCMAKE_INSTALL_PREFIX=/usr -DKDIR=/usr/src/linux-headers-`uname -r` -DLUA=TRUE -DCPACK_TYPE=Ubuntu20 ..
make
```

Create deb packet and install it:

```
cpack -G DEB
dpkg -i accel-ppp.deb
```

Copy and modify configuration file:

```
cp /etc/accel-ppp.conf.dist /etc/accel-ppp.conf
nano /etc/accel-ppp.conf
```

Set:

```
[modules]
# uncomment:
ipoe
shaper
connlimit
# end of uncomment

# comment these lines:
#pptp
#l2tp
# end of comment

[ipoe]
username=lua:username
lua-file=/etc/accel-ppp.lua

vlan-mon=ens19,10-200
# where: ens19 - interface name where Accel-PPP listens for DHCP discovery packets.
# 10-200 - Accel-PPP listens DHCP packets only with VLAN tags in this range.
# Accel-PPP automatically creates VLAN interface

interface=re:^ens19.*
# where: ens19 - interface name where Accel-PPP listens for DHCP discovery packets.
# we use regexp here because VLAN interfaces should be also included

gw-ip-address=192.0.2.1
#this is router IP address for IPoE sessions

[radius]
#nas-ip-address=127.0.0.1
# comment this ^^^

server=192.0.2.10,testing123,auth-port=1812,acct-port=1813,req-limit=50,fail-timeout=0,max-fail=10,weight=1
dae-server=0.0.0.0:3799,testing123
# where: 192.0.2.10 - IP address of Splynx server
# testing123 - RADIUS secret
acct-timeout=0

[client-ip-range]
#10.0.0.0/8
disabled
```

Create lua file:

```
cat >/etc/accel-ppp.lua <<EOF
#!lua
function username(pkt)
    mac=pkt:hdr('chaddr')
    return mac
end
EOF
```

Start Accel-PPP system service:

```
systemctl start accel-ppp
systemctl enable accel-ppp
```

Create logrotate rule:

```
cat >/etc/logrotate.d/accel-ppp <<EOF
/var/log/accel-ppp/*.log {
        missingok
        sharedscripts
        postrotate
                test -r /var/run/accel-pppd.pid && kill -HUP \`cat /var/run/accel-pppd.pid\`
        endscript
}
EOF
```

Create sysctl config:

```
cat >/etc/sysctl.d/accel-ppp.conf <<EOF
net.ipv4.ip_forward = 1
net.ipv4.neigh.default.gc_thresh1 = 4096
net.ipv4.neigh.default.gc_thresh2 = 8192
net.ipv4.neigh.default.gc_thresh3 = 12288
net.ipv6.neigh.default.gc_thresh1 = 4096
net.ipv6.neigh.default.gc_thresh2 = 8192
net.ipv6.neigh.default.gc_thresh3 = 12288
EOF
```

If firewall MASQUERADE rule is needed, this is an example:

```
apt -y install iptables-persistent
iptables -t nat -A POSTROUTING -o ens18 -j MASQUERADE
iptables-save >/etc/iptables/rules.v4
```

where **ens18** - uplink interface

### Splynx configuration

1. Requirements  
   Create a [Splynx ipv4 network](https://docs.splynx.com/networking/ip_address_management/ipv4)  
   Create a [Splynx internet tariff](https://docs.splynx.com/configuring_tariff_plans/internet_plans)

2. Create [internet service](https://docs.splynx.com/customer_management/customer_services) for customer  
   login=MAC address of DHCP-client  
   password - any  
   IPv4 assignment method=permanent  
   IP=IP  
   MAC=MAC address of DHCP-client

3. Create a NAS type  
   Config / Networking / NAS types  
   Create NAS type "Accel-PPP". MikroTik API disabled

4. Add a router  
   Networking / Routers / Add  
   NAS type=Accel-PPP  
   Authorization/Accounting=PPP RADIUS/RADIUS

   After router is created, set RADIUS secret. The secret must be the same as in file `/etc/ accel-ppp.conf` (see above)

5. Configure Radius  
   Config / Networking / Radius  
   Nas Type = "Accel-PPP"  
   Load  
   Allow with no account balance - enabled  
   Process accounting without IP - enabled  
   Rate-Limit attributes: `Filter-Id={{ tx_rate_limit / 1000 }}/{{ rx_rate_limit / 1000 }}`  
   Save  
   Restart radius

### DKMS for vlan and ipoe modules

When Accel-PPP is built from source and then installed as deb packet (see above), kernel modules **ipoe** and **vlan** are being installed only for current kernel. Each time Linux kernel is updated, it is required to (re)build **vlan** and **ipoe** kernel modules. This task can be automatized using DKMS.

Install required packets:

```
apt install dkms debhelper
export C_INCLUDE_PATH=/usr/src/$( uname -r)/
export KERNELDIR=/lib/modules/$( uname -r)/build
```

#### IPoE module

Create DKMS configuration:

```
cd /opt/accel-ppp-code/drivers/ipoe
cat >dkms.conf <<EOF
PACKAGE_NAME="accel-ppp-ipoe-dkms"
PACKAGE_VERSION=1.0
REMAKE_INITRD=no
AUTOINSTALL=yes
BUILT_MODULE_NAME="ipoe"
DEST_MODULE_LOCATION="/kernel/misc"
EOF
```

Create deb packet and install it:

```
dkms mkdeb --source-only
cd ..
dpkg -i accel-ppp-ipoe-dkms-dkms_1.0_all.deb
```

#### VLAN module

Create DKMS configuration:

```
cd /opt/accel-ppp-code/drivers/vlan_mon
cat >dkms.conf <<EOF
PACKAGE_NAME="accel-ppp-vlan-mon-dkms"
PACKAGE_VERSION=1.0
REMAKE_INITRD=no
AUTOINSTALL=yes
BUILT_MODULE_NAME="vlan_mon"
DEST_MODULE_LOCATION="/kernel/misc"
EOF
```

Create deb packet and install it:

```
dkms mkdeb --source-only
cd ..
dpkg -i accel-ppp-vlan-mon-dkms-dkms_1.0_all.deb
```

Now, each time Linux kernel is updated, these modules will be built automatically
