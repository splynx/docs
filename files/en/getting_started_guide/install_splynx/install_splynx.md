Install Splynx ISP Framework
============================

**Base requirements:**

**_Clear_ Debian or Ubuntu server.**

**Supported OS: Debian 8, 9 (without GUI) or Ubuntu 16.04 (server)**

Enter as root:

Ubuntu:
```bash
sudo su
```
Debian:
```bash
su
```
Timezone configuration:
```bash
dpkg-reconfigure tzdata
```
Update CA certificates for HTTPS:

```bash
apt-get install ca-certificates
update-ca-certificates
```
Install:
```bash
wget -qO- https://deb.splynx.com/setup | bash -
apt-get install splynx
```
Update:
```bash
apt-get update
apt-get dist-upgrade
```
If you make error when enter license code, or mysql root password you can reenter it with:
```bash
dpkg-reconfigure splynx
```
