Install Splynx ISP Framework
============================

**Base requirements:**

**_Clear_ Debian or Ubuntu server.**

**Supported OS(s): Debian 9 (without GUI) or Ubuntu 16.04 (server)**

Login to your server via CLI, as root:

For Ubuntu, use the following command to gain root access:

```bash
sudo su
```

For Debian, use the following command to gain root access:
```bash
su
```

To configure your Timezone, use the following command:

```bash
dpkg-reconfigure tzdata
```

To Update CA certificates for HTTPS, use the following commands:

```bash
apt-get install ca-certificates
update-ca-certificates
```

To Install Splynx, enter the following commands:
```bash
wget -qO- https://deb.splynx.com/setup | bash -
apt-get install splynx
```
To finish the installation process, please type the following order of URL in a browser - http://ip_address/admin (where ip_address is, replace it with the IP address of your Splynx server), add your license key and save it:

![Screenshot](install_splynx1.png)

After applying your license, you will be redirected to the "Finish setup" menu (you can skip this part but we highly recommend completing these steps to complete the initial set up of your Splynx server):

![Screenshot](install_splynx2_1.png)

![Screenshot](install_splynx3.png)

![Screenshot](install_splynx4.png)

![Screenshot](install_splynx5.png)

![Screenshot](install_splynx6.png)


To Update your server:
```bash
apt-get update
apt-get dist-upgrade
```

If you make an error when entering your license code, or mysql root password you can re-enter it with:

```bash
dpkg-reconfigure splynx
```
