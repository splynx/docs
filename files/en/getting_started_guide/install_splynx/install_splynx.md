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
To finish the installation please type this order of URL in a browser - http://ip_address/admin (where ip_address is, replace with the IP address of your Splynx server), add your license key and save it:
![Screenshot](install_splynx1.png)

After applying your license you will be redirected to the "Finish setup" menu (you can skip it but we recommend completing these steps):

![Screenshot](install_splynx2_1.png)

![Screenshot](install_splynx3.png)

![Screenshot](install_splynx4.png)

![Screenshot](install_splynx5.png)

![Screenshot](install_splynx6.png)


Update:
```bash
apt-get update
apt-get dist-upgrade
```
If you make an error when entering your license code, or mysql root password you can re-enter it with:
```bash
dpkg-reconfigure splynx
```
