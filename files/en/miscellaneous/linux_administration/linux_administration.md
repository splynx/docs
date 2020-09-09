Linux Administration
========

Here are a few useful commands to use during Linux administration of your Splynx server.

## Linux administration/Linux disk usage


To check disk usage on Linux, the following command can be used to install the "NCDU" package:

```
apt-get install ncdu
ncdu
```

## Linux administration/Create swap file

To create a swap-file, the following commands can be used:

```
if [[ ! -f /swapfile ]]; then
    echo "Building swapfile..."
    dd if=/dev/zero of=/swapfile bs=64M count=32
    mkswap /swapfile
    chmod 0600 /swapfile
    swapon /swapfile

    # Mount on reboot
    if [[ -z "$(cat /etc/fstab | grep swapfile)" ]]; then
        echo "/swapfile none swap sw 0 0" | tee -a /etc/fstab > /dev/null 2>&1
    fi
fi
```

This will create a 2 GB file, if you need more or less, please change bs=64M count=32 - 32 to 16 for 1 GB, 64 for 4 GB.

## Linux administration/Setup system time from NTP

To configure the time on your server, please use the following commands and process:

It is necessary to first **Stop NTP** services:

```
service ntp stop
```

Thereafter, run the following command to **Sync time:**

```
ntpdate -s time.nist.gov
```

*time.nist.gov is a load balancer that will find the best server for any particular location.*

The final step is to simply **Start NTP** services again:

```
service ntp start
```

## Linux administration/Setup linux timezone

You can configure the time-zone of your server with the following command:

```
dpkg-reconfigure tzdata
```
