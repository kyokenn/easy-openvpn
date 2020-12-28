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
./easy-openvpn.py user@host
```
It will generate the following files:
* dh.pem - copy it to server
* ca_cert.pem - copy it to server
* ca_key.pem - keep this file on a certificate management machine for generating new client's certificates
* **host**_cert.pem - copy it to server "host"
* **host**_key.pem - copy it to server "host"
* **host**.conf - copy it to server "host"
* **user**.ovpn - copy it to client "user"

For the next run you can keep your certificate chain files and generate certificate for the new client using:
```
./easy-openvpn.py user2@host
```
It will generate the following files:
* **user2**.ovpn - copy it to client "user2"

Generate full certificate chain for the first client and server *without embedding client certificates and keys*:
```
./easy-openvpn.py user@host --no-embed
```
It will generate the following files:
* dh.pem - copy it to server
* ca_cert.pem - copy it to client and server
* ca_key.pem - keep this file on a certificate management machine for generating new client's certificates
* **host**_cert.pem - copy it to server "host"
* **host**_key.pem - copy it to server "host"
* **host**.conf - copy it to server "host"
* **user**_cert.pem - copy it to client "user"
* **user**_key.pem - copy it to client "user"
* **user**.conf - copy it to client "user"
