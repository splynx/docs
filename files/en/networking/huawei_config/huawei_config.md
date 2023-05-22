Huawei GPON configuration (commands)
==================================

In this article, you can find helpful commands that can be used for the configuration of Huawei MA5800-X7 GPON from within Splynx. Huawei instead of the `show` use the `display` command. Also, there is enable mode, similar to Cisco devices. If we need to delete part of the configuration – use `undo some_command` instead of `no some_command`.

The basic information of the system `display version` give the understanding of the version of equipment and OS running on it.

It shows interfaces, for instance, MEth0. Now it’s showing GPON ports: `display interface`

The most important commands show running and startup configurations:

```
display saved-configuration
display saved-configuration
```

Get information about configured IPs and also the routing table:

```
display ip interfaces
display ip routing-table
```

## How to set user and config default route

Use:

`ip route-static 0.0.0.0 0.0.0.0 10.0.0.1`

`ssh user "test" authentication-type password`

Before configuring GPON and VLANs we need to install physical cards to chassis slots and initiate them with commands similar to:

This command is adding a card on board 0, slot 5. And it’s defining that it’s a 16 port GPON card. In our case, we have one H901GPHF (GPON 16 port) and H901MPLA (SFP+ Ethernet) card:

`board add 0/5 H901GPHF`

## How to configure GPON

1. SET VLANS. ID depends on the design, let’s assume that 100 is management, 200 Internet, 300 voice and 400 is IPTV

(config)

```
vlan 100 smart
vlan 200 smart
vlan 300 smart
vlan 400 smart
```

2. SET VLANs to the UPLINK PORT

Our UPLINK port is located in the board 0, slot 0, SFP port 0. It means “0/8 0”

(config)

```
port vlan 100 0/8 0
port vlan 200 0/8 0
port vlan 300 0/8 0
port vlan 400 0/8 0
```

3. Defining DBA profiles. This defines upload speed (capability of the service on one ONT)

Here it says that upload for MGNT is a maximum 1Mbps, for the Internet is from 10Mbps to 200Mbps, Voice is 4Mbps and TV is up to 5 Mbps.

```
dba-profile add profile-id 100 profile-name "MGNT" type1 fix 1024
dba-profile add profile-id 102 profile-name "INTERNET" type3 assure 10000 max 200000
dba-profile add profile-id 103 profile-name "VOICE" type1 fix 4096
dba-profile add profile-id 104 profile-name "CUSTOM_TV" type1 fix 5192
```

4. Configure traffic tables and define real speed limitations

We define MGNT to 1 Mbps Up and down, Voice to 4 Mbps, TV to 10 Mbps, and the Internet to 100/20 Mbps.

```
traffic table ip index 100 name "MGNT" cir 512 cbs 329680 pir 1024 pbs 329680 color-mode color-blind priority 7 priority-policy local-setting
traffic table ip index 101 name "INTERNET_100_DOWN" cir 10000 cbs 329680 pir 100000 pbs 329680 priority 0 priority-policy local-Setting
traffic table ip index 102 name "INTERNET_20_UP" cir 4096 cbs 329680 pir 20000 pbs 329680 priority 0 priority-policy local-Setting
traffic table ip index 103 name "VOICE_SMART" cir 2048 cbs 329680 pir 4096 pbs 329680 color-mode color-blind priority 7 priority-policy local-setting
traffic table ip index 104 name "CUSTOM_TV_COOL" cir 5192 cbs 329680 pir 10240 pbs 329680 color-mode color-blind priority 7 priority-policy local-setting
```

5. SYNC PROFILES/BUNDLE

(config)

`ont-lineprofile gpon profile-id 20 profile-name "FTTH-100"`

Here we defined `ont-lineprofile` for FTTH-100 tariff bundle, that includes voice, IPTV, internet and management.

Following configuration lines are put under `ont-lineprofile` config:

```
tcont 1 dba-profile-id 100
tcont 2 dba-profile-id 102
tcont 3 dba-profile-id 103
tcont 4 dba-profile-id 104
```

```
gem add 1 eth tcont 1
gem add 2 eth tcont 2
gem add 3 eth tcont 3
gem add 4 eth tcont 4
```

```
gem mapping 1 1 vlan 100
gem mapping 2 2 vlan 200
gem mapping 3 3 vlan 300
gem mapping 4 4 vlan 400
commit
```

6. SERVICE PROFILE

```
ont-srvprofile gpon profile-id 20 profile-name "FTTH-100"
ont-port pots adaptive eth adaptive
commit
```

7. ONT CONNECTION

Auto find can be enabled this way:

```
interface gpon 0/5
port 0 ont-auto-find enable
```

SET PROFILES to CUSTOMER:

```
interface gpon 0/5
ont add 0 1 sn-auth "4857544352E92103" omci ont-lineprofile-id 20 ont-srvprofile-id 20 desc "CUSTOMER-1"
```

8. The last is the most difficult command – it’s defining service ports for each VLAN for ONT

```
service-port 1001 vlan 100 gpon 0/5/0 ont 1 gemport 1 multi-service user-vlan 100 tag-transform translate inbound traffic-table index 10 outbound traffic-table index 10
service-port 1002 vlan 200 gpon 0/5/0 ont 1 gemport 2 multi-service user-vlan 200 tag-transform translate inbound traffic-table index 102 outbound traffic-table index 101
service-port 1003 vlan 300 gpon 0/5/0 ont 1 gemport 3 multi-service user-vlan 300 tag-transform translate inbound traffic-table index 103 outbound traffic-table index 103
service-port 1004 vlan 400 gpon 0/5/0 ont 1 gemport 4 multi-service user-vlan 400 tag-transform translate inbound traffic-table index 104 outbound traffic-table index 104
```

## Commands to check the displaying status

When everything is configured, there are a few helpful commands for displaying status.

* Show all configured ONT devices:

`display ont info 0 5 0 all`

`display ont info summary 0/5`

`display service-port all`

* Show auto-discovered ONTs:

`display ont autofind all`

* Show physical module installed on Huawei OLT chassis:

`display board 0`

* Show specific module installed:

```
display board 0/SlotID
display board 0/5
```

* Show all configuration:

`display display current-configuration`

* Show GPON dba profile:

`display dba-profile all`

* Show traffic table that is used for speed limitations:

`display traffic table ip from-index 0`

* Show service port:

`display service-port all`

* Show ont lineprofile:

`display ont-lineprofile gpon all`

* Show ont service profile:

`display ont-srvprofile gpon all`

## How to remove ONT from configured Huawei ONL

The first step is to delete all associated service ports:

```
undo service-port 1001
undo service-port 2001
undo service-port 3001
undo service-port 4001
```

The second step is to delete ONT itself:

```
interface gpon 0/5
ont delete 0 0
```