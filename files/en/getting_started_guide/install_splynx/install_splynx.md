Install Splynx ISP Framework
============================

<icon class="image-icon">![Important](warning.png)</icon> **Basic requirements & Supported OS:**

- **fresh installed `Ubuntu 20.04 (server)`**;

- [hardware requirements](getting_started_guide/hardware_requirements/hardware_requirements.md).

<icon class="image-icon">![INF](information.png)</icon> **To install Splynx on your server**, please make the following steps:

- Login to your server via CLI, as **root**:

For Ubuntu, use the following command to gain root access:

```bash
sudo su
```

- Perform timezone configuration:

```
dpkg-reconfigure tzdata
```

- Install:

```
wget -qO- https://deb.splynx.com/setup_4_0 | bash -
apt-get install splynx
```

- To Update CA certificates for HTTPS, use the following commands:

```bash
apt-get install ca-certificates
update-ca-certificates
```

After installation is completed, type in the address line of web browser - http://IP_address (e.g.http://192.168.0.239/admin) (where the `IP_address` is the address of your Splynx server).

After that, enter your license key and save it:

![Screenshot](install_splynx1.png)

After your license key is applied, you will be redirected to the *Initial setup menu* (you can skip this part, but we highly recommend following these steps to complete the initial setup of your Splynx server):

![Screenshot](install_splynx2_1.png)

![Screenshot](install_splynx3.png)


![Screenshot](install_splynx4.png)


<icon class="image-icon">![INF](information.png)</icon> **To Update your server**:

**Upgrade:** Supported OS for upgrade: Ubuntu 20.04 (server) with Splynx v3.1 installed

```
apt update
apt install splynx-7.4
```
**Update:**

```bash
apt-get update
apt-get dist-upgrade
```

<icon class="image-icon">![Important](warning.png)</icon> **IMPORTANT:**

If you are current running Splynx v3.0 or earlier, please contact support via `support@splynx.com`

If you made a mistake when entering your license code (or mysql root password) you can re-enter it with:

```bash
dpkg-reconfigure splynx
```

Video tutorial:

<iframe frameborder=0 height=270 width=350 allowfullscreen src="https://www.youtube.com/embed/0KZAENbH5KE">Video on youtube</iframe>
