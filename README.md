[![License](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)
[![Build Status](https://travis-ci.org/grycap/ansible-role-mesos.svg?branch=master)](https://travis-ci.org/grycap/ansible-role-mesos)

Mesos Role
==========

Installs a Mesos cluster (recipe for EC3). Mesos current stable version: 1.1.0

Example Playbook
----------------
```
  - hosts: server
  roles:
  - { role: 'grycap.mesos', mesos_install_mode: "front"}
```
```
  - hosts: client
  roles:
  - { role: 'grycap.mesos', mesos_install_mode: "wn"}
```

Contributing to the role
========================
In order to keep the code clean, pushing changes to the master branch has been disabled. If you want to contribute, you have to create a branch, upload your changes and then create a pull request.  
Thanks
