[![License](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)

Mesos Role
==========

Installs a Mesos cluster (recipe for EC3)

Example Playbook
----------------
```
  - hosts: server
  roles:
  - { role: 'grycap.mesos', mesos_install_mode: "master"}
```
```
  - hosts: client
  roles:
  - { role: 'grycap.mesos', mesos_install_mode: "slave"}
```

Contributing to the role
========================
In order to keep the code clean, pushing changes to the master branch has been disabled. If you want to contribute, you have to create a branch, upload your changes and then create a pull request.  
Thanks