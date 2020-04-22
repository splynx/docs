Online backups
==============

An additional method to protect yourself from data loss is by storing an additional backup in our cloud.
This is especially useful when hard disks break, and local copies become inaccessible.


Backups are created automatically every 6 hours and sent to the cloud for storage. Please note that only **changes** are sent(incremental backup) and only in **encrypted** form.


To configure this feature the best way is to install the **splynx-remote-support** plugin.
([how to install it?](addons_modules/splynx_remote_support/splynx_remote_support.md))

>This plugin uses [Burp](https://github.com/grke/burp) inside a secure tunnel for data transmission.


----
If for some reason the plugin is inadmissible for you, but there is a need for backups, there is another way:

1. Your server needs a public IP

2. Allow access to your server via ssh from the host: `backup.splynx.com`

3. Send an e-mail to support@splynx.com, which states that you want to connect the online backup service, as well as the data for the ssh connection `PUBLIC_IP: PORT`

>In this case, the backup will be performed via rsync
