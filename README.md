UniSQ Ansible Role install Docker CE
=========

This is an ansible role to install docker-ce, from the official apt repo, with various options, such as installing docker-compose and disabling the docker iptables dynamic rules.

The role is adapted from Galaxy Role 0x646e78.docker_debian as well as code from Daniel F.

Requirements
------------

Make sure the Ansible controller has `sshpass` installed. Then install the role on the controller using `ansible-galaxy install`, and then create a playbook and a hosts file.  Run the playbook using `ansible-playbook -u usqstudent -i hosts -kK playbookdocker.yml`.

Role Variables
--------------

* `iptables: true` - Set to false to disable docker controlled iptables rules.
* `install_compose: false` - Set to true to install docker-compose

Dependencies
------------

None

Example Playbook
----------------

- hosts: myAZlab # 'hosts' file should contain [myAZlab] lab-xxxxx-azure.com ansible_port=50xx
  roles:
    - { role: username.rolename, iptables: false, install_compose: true }

License
-------

BSD

Author Information
------------------

UniSQ SD, 2024.  Based on work from 0x646e78 and Daniel F.
