Ansible Role: MongoDB Repository
=========

An Ansible Role that to manage MongoDB Yum repository

Requirements
------------

This role needs no special requirements, except sudo access

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):


```yaml
---
repo_location:              international   # available options: international, vagrant
mongodb_enabled:            yes
mongodb_version:            3.4
```

Dependencies
------------

None

Example Playbook
----------------

We can use this roles multiple times with different `mongodb_version` like this:

```yaml
---
- name: Prepare CentOS 7 server
  hosts: centos7
  roles:
    - role: adipriyantobpn.repo-mongodb
      repo_location:              vagrant
      mongodb_enabled:            yes
      mongodb_version:            3.4
    - role: adipriyantobpn.repo-mongodb
      repo_location:              international
      mongodb_enabled:            no
      mongodb_version:            3.2
    - role: adipriyantobpn.repo-mongodb
      repo_location:              international
      mongodb_enabled:            no
      mongodb_version:            3.0
```
Just make sure that odd-numbered minor release versions (e.g. 2.5) are development versions and are unsuitable for production use.

source : https://docs.mongodb.com/manual/tutorial/install-mongodb-on-red-hat/

License
-------

BSD

Author Information
------------------

This role was created in 2017 by [Adi Priyanto](https://github.com/adipriyantobpn) as a learning purpose for community.