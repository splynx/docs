Console Commands
============

Here are a few useful commands when working with your Splynx server via CLI.

##  Splynx ISP Framework services

**Radius**

Splynx ISP Framework radius server

```
splynx_radd
```

usage:

```
service splynx_radd stop
service splynx_radd start
service splynx_radd restart

```
**Transport**

Splynx ISP Framework transport server php -> nodejs

```
splynx_transport
```
usage:

```
service splynx_transport stop
service splynx_transport start
service splynx_transport restart
```

**Node**

The Splynx ISP Framework nodejs service is used for notifications, monitoring, ping, and real-time file outputs.

```
splynx_node
```

usage:

```
service splynx_node stop
service splynx_node start
service splynx_node restart
```


## Console/Passwd



**Password change tools**

Usage:

```
/var/www/splynx/system/script/passwd
```

Output:

```
Usage:
./passwd admin --login=<admin> --password=<password>
Change password for administrator <admin>

./passwd customer --login=<login> --password=<password>
Change the password for customer <login>, you can enter :ALL: for all customers, password not required
```

Video how to use this script:

```
<youtube>st70gbFC69w</youtube>
```

## Console/Reset DB


**Reset DB tools**

Please note: all DB's will be restored, and all data will be erased.

Usage:

```
/var/www/splynx/system/script/reset_db
```

Output:

Please note after this action all information on your database will be deleted, you can not restore it without a backup.
The password for administrator 'admin' is required for this action.

Be sure you have a backup before you execute this action.

Usage:
```
./reset_db reset --confirm=YES
```

## Splynx ISP Framework tools script
Usage:

```
/var/www/splynx/system/script/tools
```

Output:

```
Usage: ./tools <action> <parameter>=<value>

actions:
clear-services - Clear all services for all customers and param type = all, internet, voip, custom
mikrotik-export - Export rules from mikrotik, params: --router_id=ID, --command="/queue/simple/print"
```

Video demo how to export customers from mikrotik with this script:


 <iframe frameborder=0 height=270 width=350 allowfullscreen src="https://www.youtube.com/watch?v=FzOZnqhPt8E&t=114s">Video on youtube</iframe>


## Splynx Mysql backup script
Usage:

```
/var/www/splynx/system/backup/backup
```

Output:

```
Usage: ./backup <action> <parameter>=<value>

./backup - make critical backup of system
./backup full=true - make full backup of system
```

## Splynx incremental remote backup system

We provide incremental backups system on our systems. Please send us a ticket with the subject containing: backup configuration and information: Company name, Splynx Public IP address (with access to ssh) (it may be on a different from port 22) and we will configure automation of backups for every 4 hours for your full system. (we store around 1 month of every 4 hours backups of your full Splynx server)


## Configuration of own incremental backup system
all actions are to be executed as root users, so don't forget to enter sudo su - on ubuntu, or just su on debian

**Generation of SSH keys**
To generate a public and private key run the following command on your backup server:

```
ssh-keygen -t rsa
```

We do not want a passphrase for this key because we want these computers to be able to connect to each other without our intervention. Press “ENTER” through all of the prompts to accept the defaults.

We now have a public and private key pair that will allow us to sign in to other servers from our backup server. We need to transfer our public key to the machine we will be backing up so that it knows that we are allowed to access it.

```
ssh-copy-id -i /root/.ssh/id_rsa.pub root@splynx.server
```


or just context of file /root/.ssh/id_rsa.pub to file /root/.ssh/authorized.key on splynx.server

Once that command executes, you should check that you are able to log-in to your server from your backup server without a password.

```
ssh root@splynx.server
```

Once you've verified that you can connect correctly, exit out so that you are able to work on your backup server again.

```
exit
```

## Configuring Rsnapshot

```
apt-get install rsnapshot
nano /etc/rsnapshot.conf
```
The first decision you will need to make is where you would like to store your backups. We will use the directory “/backup” as our backup location. Search for and edit the following variable to set the backup location.

```
snapshot_root			 /backup/
```

If this directory does not already exist, rsnapshot will create it when it runs.

You will also want to uncomment the cmd_ssh line to allow for remote backups. Remove the “#” from in front of the following line so that rsnapshot can securely transfer your data to the backup server.

```
cmd_ssh			/usr/bin/ssh
```

Remove the “#” from before the cmd_du line to enable accurate disk usage reports.

```
cmd_du				/usr/bin/du
```

**Configure backup intervals:**

```
#########################################
#           BACKUP INTERVALS            #
# Must be unique and in ascending order #
# i.e. hourly, daily, weekly, etc.      #
#########################################

retain		hourly  6
retain		daily   7
retain		weekly  4
retain		monthly 3
```

Finally, you’ll need to decide on what you would like to backup.

```
backup		 root@splynx.server:/var/www/ 		my_splynx_backup/
```

Save the file

**Test Rsnapshot configuration**

```
rsnapshot configtest
```

If your file saves without an error, you will receive a “Syntax OK” message. If you did not receive this message, you need to go back and fix the mistakes that it tells you about.

First backup:

```
rsnapshot hourly
```

**Automating the Process**
file: /etc/cron.d/rsnapshot

```
0 */4         * * *           root    /usr/bin/rsnapshot hourly
30 3          * * *           root    /usr/bin/rsnapshot daily
0  3          * * 1           root    /usr/bin/rsnapshot weekly
30 2          1 * *           root    /usr/bin/rsnapshot monthly
```
