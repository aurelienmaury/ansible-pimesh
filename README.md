# Ansible Pi-Mesh
## Ansible modules to setup a R-Pi mesh network

* Get some R-Pi, SD Cards and Wifi dongles
* Flash your SD cards with a fresh wheezy install (June 2014 Raspbian
  at the time of writing)
* boot it and find it on your lan (with something like a: nmap -sS -p 22 192.168.42.0/24 |
  grep Rasp -B5)
* ssh into it and inject a ssh public key in /home/pi/.ssh/authorized_keys to be able to connect without any
  password
* expand the filesystem
* set your $HOME/.ssh/config to be able to connect via ssh $IP
* make a hostlist file with its IP
* run the playbook you need
