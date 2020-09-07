Linux Administration
========

## Linux administration/Linux disk usage


Who use disk on linux?

```
apt-get install ncdu
ncdu
```

## Linux administration/Create swap file

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

This was create file with size 2 GB, if you need more or less change bs=64M count=32 - 32 to 16 for 1 GB, 64 for 4 GB.

## Linux administration/Setup system time from NTP


**Stop NTP:**

```
service ntp stop
```

**Sync time:**

```
ntpdate -s time.nist.gov
```

**Start NTP:**

```
service ntp start
```

## Linux administration/Setup linux timezone

```
dpkg-reconfigure tzdata
```
