vagrant-cassandra
=======================

A work in progress.

Installs:
* Cassandra
* Ops Centre

Prereqs:
* Vagrant
* Ansible (for provisionining)

To get going:
```
vagrant up
vagrant ssh
```

Then on the box:

```
cqlsh <Node-IP> 9042
nodetool status
```
```
Connection to the opps Centre
http://192.168.56.13:8888 
```
