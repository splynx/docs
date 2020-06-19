Cambium: Wireless Authentication via Radius
==========

Cambium access points have the ability to authenticate CPE's via a Radius server. This means that, admin's doesn’t have to maintain local passwords for wireless authentication, each CPE/radio can have its own account in the Splynx ISP Framework, and our Radius server will authenticate the Cambium CPE's.

All files required for this setup can be downloaded here: [Cambium-Files](networking/authentication_users/cambium_wireless_auth_radius/cambium-certs.zip)

1. Copy the "camb-ca.crt" file into the /etc/ssl/camb-ca.crt directory

2. Copy the "cert-829.pem" file into the /etc/ssl/certs/cert-829.pem directory

3. Copy the "key-829.pem" file to the /etc/ssl/private/key-829.pem directory

4. Run the following command in the CLI of the server:
```
chown root:ssl-cert /etc/ssl/private/key-829.pem
```

  As well as:
```
chmod 640 /etc/ssl/private/key-829.pem
```

6. Within the file: /etc/freeradius/3.0/mods-available/eap - find `tls-config tls-common` and edit it as follows:

```
tls-config tls-common {
#    private_key_password = *user-defined password*
    private_key_file = /etc/ssl/private/key-829.pem
    certificate_file = /etc/ssl/certs/cert-829.pem
    ca_file = /etc/ssl/camb-ca.crt    
}
```
7. Within Splynx, navigate to `Config / Networking / Radius extended` - and set the following parameters:

```
Force network to use one NAS - YES
Network - Any network can be used
Default NAS Id - set correct NAS ID (Device that will show online users)
```
