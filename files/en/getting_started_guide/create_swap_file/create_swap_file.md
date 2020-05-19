Create swap file
================

Run on your server:

```bash
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

These commands create a 2 GB file.
If you need more or less, change `count=32`:

* `count=16` - for 1 GB,
* `count=64` - for 4 GB.
