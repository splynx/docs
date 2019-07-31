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
Finish installation you should from the web. Open URL in browser - http://ip_address/admin (where ip_address it's IP address of your Splynx server), add your license key and save it:
![Screenshot](install_splynx1.png)

After checking license you will redirect to the "Finish setup" menu (you can skip it, but we recommend to complete these steps):

![Screenshot](install_splynx2.png)

![Screenshot](install_splynx3.png)

![Screenshot](install_splynx4.png)

![Screenshot](install_splynx5.png)

![Screenshot](install_splynx6.png)


Update:
```bash
apt-get update
apt-get dist-upgrade
```
If you make error when enter license code, or mysql root password you can reenter it with:
```bash
dpkg-reconfigure splynx
```
