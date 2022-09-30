Admin login to Juniper (JUNOS)
==========

First of all, we need to add router to Splynx and define NAS Type = Juniper.

![NAS type](junos_add_router.png)

If you choose the wrong NAS Type, authentication of administrators will not work. The difference between JunOS's Radius admin login and other vendors is that Juniper does not send Session-Type in the Radius packet when administrator tries to login to the system. Because we set the NAS type to Juniper, Splynx expects this behavior and knows that it is the administrator, checks the DB and if the admin is there, the admin will be allowed to login to the router.

 Below is an example of the packet format sent to the Radius server in Access-request when an administrator logs in to a Juniper router :

![JunOS](junos.png)

How to configure a Juniper router for Radius admin login :

```
test@VMX-spl> configure
Entering configuration mode

[edit]

test@VMX-spl# show

system {
host-name VMX-spl;
authentication-order [ radius password ];

radius-server {
172.16.200.1 {
secret "$9$JQGHqP5Qn9Af5hS"; ## SECRET-DATA
timeout 5;
source-address 10.0.1.199;
}
}
services {
ssh;
}
```

Statement authentication-order [ radius password ]; defines that we want to use Radius and then local login.

Also we define the Radius server IP and services that we will use to login to the router, which here, is SSH.

If we also want to have local logins, the following configuration can help us achieve it :
```
groups {
global {
system {
login {
user test {
uid 2001;
class super-user;
authentication {
encrypted-password "$6$jGuS4u2w$KxLWzdpnDq2faqVV1Tp/isD2Azbz/w90275EkcRkZBBhAxOR6As84BpSblR05HbsRLifO1h5Uu/Ecdgu10c4e."; ## SECRET-DATA
}
}
}
}
}
}
apply-groups global;
```

---
The version of JunOS that was used for testing is:

Model: vmx
Junos: 17.2R1.13
