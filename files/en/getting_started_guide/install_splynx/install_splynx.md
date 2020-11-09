Install Splynx ISP Framework
============================

**Base requirements:**

**_Clear_ Ubuntu server.**

**Supported OS: Ubuntu 20.04 (server)**

Login to your server via CLI, as root:

For Ubuntu, use the following command to gain root access:

```bash
sudo su
```

Timezone configuration:

```
dpkg-reconfigure tzdata
```

Install:

```
wget -qO- https://deb.splynx.com/setup_3_1 | bash -
apt-get install splynx
```

To Update CA certificates for HTTPS, use the following commands:

```bash
apt-get install ca-certificates
update-ca-certificates
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

**Upgrade:** Supported OS for upgrade: Ubuntu 20.04 (server) (Splynx version 3.1)

```
apt update
apt install splynx-7.4
```
**Update:**

```bash
apt-get update
apt-get dist-upgrade
```

#### Important notice!
If you are current running Splynx v3.0 or earlier, please contact support: support@splynx.com

If you make an error when entering your license code, or mysql root password you can re-enter it with:

```bash
dpkg-reconfigure splynx
```

Video tutorial:

<iframe frameborder=0 height=270 width=350 allowfullscreen src="https://www.youtube.com/embed/0KZAENbH5KE">Video on youtube</iframe>
