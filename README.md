[![License](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)
[![Build Status](https://travis-ci.org/grycap/ansible-role-mesos.svg?branch=master)](https://travis-ci.org/grycap/ansible-role-mesos)

Mesos Role
==========

Installs a Mesos cluster (recipe for EC3). Mesos current stable version: 1.1.0

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows.

  	# Type of node to install: front or wn
	mesos_type_of_node: front
  	# SSH user
  	mesos_ssh_user: "grycap"
  	# Prefix to set to the Mesos working nodes
  	vnode_prefix: wn
  	# Directory to save the Mesos log
  	mesos_log_dir: "/var/log/mesos"
  	# Max number of nodes of the cluster
  	max_number_of_nodes: 3
	# IP address of the mesos master
	mesos_master: {{ ansible_default_ipv4.address }}
	# Hostname of the WN
	wn_hostname: "{{ ansible_hostname }}"


Example Playbook
----------------
```
  - hosts: server
  roles:
  - { role: 'grycap.mesos', mesos_type_of_node: "front" }
```
```
  - hosts: client
  roles:
  - { role: 'grycap.mesos', mesos_type_of_node: "wn", vnode_prefix: 'wn'}
```

Contributing to the role
========================
In order to keep the code clean, pushing changes to the master branch has been disabled. If you want to contribute, you have to create a branch, upload your changes and then create a pull request.  
Thanks
