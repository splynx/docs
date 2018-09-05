Install Splynx ISP Framework
============================

For the installation, please use a clear Debian or Ubuntu server.

Log in as root:

Ubuntu:

`sudo su`

Debian:

`su`

Insert Timezone configuration:

`dpkg-reconfigure tzdata`

Update CA certificates for HTTPS:

`apt-get install ca-certificates`
`update-ca-certificates`

Install Splynx:

`wget -qO- https://deb.splynx.com/setup | bash -`
`apt-get install splynx`

or update it:

`apt-get update`
`apt-get install splynx`

If you make a mistake when you enter the license code, or the mysql root password you can use:

`dpkg-reconfigure splynx`

The installation procedure has been tested on:

* Debian 7, 8
* Ubuntu 14.04, 15.04, 15.10, 16.04, 16.10