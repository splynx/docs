What we need is a separate server/VM with Ubuntu 20.04 installed.

Login as root:  
#> sudo su -l

Install packets for building:  
#> apt update && apt install -y build-essential cmake gcc linux-headers-`uname -r` git libpcre3-dev libssl-dev liblua5.1-0-dev

Clone AccelPPP code:  
#> git clone https://github.com/xebd/accel-ppp.git /opt/accel-ppp-code

Compile AccelPPP code:  
#> mkdir /opt/accel-ppp-code/build
#> cd /opt/accel-ppp-code/build/
#> cmake -DBUILD_IPOE_DRIVER=TRUE -DBUILD_VLAN_MON_DRIVER=TRUE -DCMAKE_INSTALL_PREFIX=/usr -DKDIR=/usr/src/linux-headers-`uname -r` -DLUA=TRUE -DCPACK_TYPE=Ubuntu20 ..
#> make

Create deb packet and install it:  
#> cpack -G DEB
#> dpkg -i accel-ppp.deb

Copy and modify config file:  
#> cp /etc/accel-ppp.conf.dist /etc/accel-ppp.conf
#> nano /etc/accel-ppp.conf

Set:  
[modules]
# uncomment:  
ipoe
shaper
connlimit

# comment:  
#pptp
#l2tp

[ipoe]
username=lua:username
lua-file=/etc/accel-ppp.lua

vlan-mon=ens19,10-200
# where: ens19 - interface name where accelPPP listens for DHCP discovery packets. 
# 10-200 - AccelPPP listens DHCP packets only with vlan tags in this range.
# AccelPPP automatically creates vlan interface

interface=re:^ens19.*
# where: ens19 - interface name where accelPPP listens for DHCP discovery packets. 
# we use regexp here because vlan interfaces should be also included

gw-ip-address=192.0.2.1
#this is router IP address for IPoE sessions

[radius]
#nas-ip-address=127.0.0.1
# comment this ^^^

server=192.168.99.49,testing123,auth-port=1812,acct-port=1813,req-limit=50,fail-timeout=0,max-fail=10,weight=1
dae-server=0.0.0.0:3799,testing123
# where: 192.168.99.49 - Splynx server IP address
# testing123 - RADIUS secret
acct-timeout=0

[client-ip-range]
#10.0.0.0/8
disabled

#END of config file


Create lua file:  
#> cat >/etc/accel-ppp.lua <<EOF
#!lua
function username(pkt)
    mac=pkt:hdr('chaddr')
    return mac
end
EOF

Start accel-ppp system service:  
#> systemctl start accel-ppp
#> systemctl enable accel-ppp

Create logrotate rule:  
#> cat >/etc/logrotate.d/accel-ppp <<EOF
/var/log/accel-ppp/*.log {
        missingok
        sharedscripts
        postrotate
                test -r /var/run/accel-pppd.pid && kill -HUP \`cat /var/run/accel-pppd.pid\`
        endscript
}
EOF

Create sysctl config:  
#> cat >/etc/sysctl.d/accel-ppp.conf <<EOF
net.ipv4.ip_forward = 1
net.ipv4.neigh.default.gc_thresh1 = 4096
net.ipv4.neigh.default.gc_thresh2 = 8192
net.ipv4.neigh.default.gc_thresh3 = 12288
net.ipv6.neigh.default.gc_thresh1 = 4096
net.ipv6.neigh.default.gc_thresh2 = 8192
net.ipv6.neigh.default.gc_thresh3 = 12288
EOF

# if you need create MASQUERADE rule, this is an example:  

#> apt -y install iptables-persistent
#> iptables -t nat -A POSTROUTING -o ens18 -j MASQUERADE
#> iptables-save >/etc/iptables/rules.v4
# where ens18 - uplink interface



# Splynx configuration
0. Requirements
Create Splynx ipv4 network
Create Splynx internet tariff

1. Create internet service for customer
login=mac address of DHCP-client
password - any
IPv4 assignment method=permanent
IP=IP
MAC=mac address of DHCP-client

2. Create NAS type
Config / Networking / NAS types
Create NAS type "Accel-PPP". MikroTik API disabled


3. Add router
Networking / Routers / Add
NAS type=Accel-ppp
Authorization/Accounting=PPP radius/radius

After router is created, set Radius secret. The same as in accel-ppp.conf

4. Configure Radius
Config / Networking / Radius
Nas Type = "Accel-PPP"
Load

Allow with no account balance - enabled
Process accounting without IP - enabled
Rate-Limit attributes: Filter-Id={{ tx_rate_limit / 1000 }}/{{ rx_rate_limit / 1000 }}

Save
Restart radius
