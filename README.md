easy-openvpn
============

No hassle easy OpenVPN certificate and config generation tool.

Features
--------

* Simple single file script
* Pure Python with no extra dependencies
* Generates Diffie Hellman key
* Generates CA, server and client certificates
* Generates server config
* Generates client .ovpn config with embedded certificates for easy 1-click import into VPN client

Usage
-----

Generate full certificate chain for the first client and server:
```
./easy-openvpn.py client1_name
```
It will generate the following files:
* dh.pem - copy it to server
* ca_cert.pem - copy it to client and server
* ca_key.pem - keep this file on a certificate management machine for generating new client's certificates
* server_cert.pem - copy it to server
* server_key.pem - copy it to server
* client1_name_cert.pem - copy it to client1
* client1_name_key.pem - copy it to client1

For the next run you can keep your certificate chain files and generate certificate for the new client using:
```
./easy-openvpn.py client2_name
```
It will generate the following files:
* client2_name_cert.pem - copy it to client2
* client2_name_key.pem - copy it to client2
