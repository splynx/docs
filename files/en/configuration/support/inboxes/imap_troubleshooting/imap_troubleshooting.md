IMAP - Troubleshooting SSL/TLS Errors
=============

If your mail server work on old outdated TLS V1 you can allow Splynx server to work with this server by following config:

For Ubuntu 20.04 (from Splynx 3.1) you should add to file `/etc/ssl/openssl.cnf`:
after line: `oid_section		= new_oids`
```
openssl_conf = default_conf

[ default_conf ]
ssl_conf = ssl_sect

[ ssl_sect ]
system_default = system_default_sect

[ system_default_sect ]
MinProtocol = TLSv1
CipherString=DEFAULT:@SECLEVEL=1
```

After that php7.4-fpm should be restarted by:
```
service php7.4-fpm restart
```

Also you can try different IMAP ports: 143, 993
