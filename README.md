[![License](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)
[![Build Status](https://travis-ci.org/grycap/ansible-role-mesos.svg?branch=master)](https://travis-ci.org/grycap/ansible-role-mesos)

Mesos Role
==========

Installs a Mesos cluster (recipe for EC3). Mesos current stable version: 1.1.0

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows.

	# Type of node to install: master/front or slave/wn
	mesos_type_of_node: "master"
	mesos_log_dir: "/var/log/mesos"

	# Common
	mesos_executor_registration_timeout: 10mins
	mesos_cluster_name: "MesosCluster"
	mesos_quorum: "1"
	mesos_front_private_ip: "{{ansible_default_ipv4.address}}"
	mesos_docker_opts: ""
	mesos_version: "latest"

	# Defaults file for mesos-salve
	mesos_slave_port: 5051
	mesos_containerizers: "docker,mesos"
	mesos_slave_work_dir: "/var/lib/mesos"
	mesos_slave_image: "indigodatacloud/mesos-slave:{{ mesos_version }}"

	# Defaults file for mesos-master
	mesos_zookeeper_group: zookeeper_servers
	mesos_master_port: 5050
	mesos_master_work_dir: "/var/lib/mesos"
	mesos_master_image: "indigodatacloud/mesos-master:{{ mesos_version }}"

	# Zookeeper
	zookeeper_client_port: "2181"
	zookeeper_server_group: zookeeper_servers
	zookeeper_peers_nodes: "{{mesos_front_private_ip}}:{{zookeeper_client_port}}"


Example Playbook
----------------
```
  - hosts: server
  roles:
  - { role: 'grycap.mesos', mesos_type_of_node: "master"}
```
```
  - hosts: client
  roles:
  - { role: 'grycap.mesos', mesos_type_of_node: "slave"}
```

Contributing to the role
========================
In order to keep the code clean, pushing changes to the master branch has been disabled. If you want to contribute, you have to create a branch, upload your changes and then create a pull request.  
Thanks
