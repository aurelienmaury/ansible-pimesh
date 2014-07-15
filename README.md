# Ansible Pi-Mesh
## Ansible modules to setup a R-Pi mesh network

* Get some R-Pi, SD Cards and Wifi dongles
* Flash your SD cards with a fresh wheezy install (June 2014 Raspbian
  at the time of writing)
* insert a wifi dongle, boot it and find it on your lan (with something like a: nmap -sS -p 22 192.168.42.0/24 |
  grep Rasp -B5)
* ssh into it and inject a ssh public key in /home/pi/.ssh/authorized_keys to be able to connect without any
  password
* expand the filesystem
* set your $HOME/.ssh/config to be able to connect via ssh $IP
* make a hostlist file with its IP
* run the playbook you need


There is 3 roles :

* *mesh-gateway:* It has the cable! This node is supposed to gate to
  internet via its eth0 (dhcp). It hosts NTP, DHCP and DNS(masq) for
  the whole mesh network.
* *mesh-ap:* It is a wifi access point with WPA2 security for devices
  that can't take part in the ad-hoc network.
* *mesh-node:* a simple member of the mesh.

A node can be both gateway AND access point. To do that, see example
in the 'hostlist' file, you need to state the ip of the gateway in 3
groups: mesh-gateway and mesh-ap, then run the playbook PB01.
