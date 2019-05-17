PostgreSQL-role
=========

Postgresql role here. Currently it installs only for 9.6 version.

### How do I setup? ###

To change any variable you need to set hash_behaviour to merge in your ansible.cfg
~~~~
hash_behaviour = merge
~~~~

After that place postgresql_conf in your inventory to hosts where you want to install postgresql.
You can place only those variables that you need. No need for copying whole postgresql_conf from defaults.
~~~~
postgresql_conf:
  listen: '127.0.0.1'
~~~~
For more variables to adjust please refer to defaults/main.yml

Your typical playbook will looks like this.
~~~~
---
- hosts: dbservers
  user: root
  roles:
    - postgresql-role
~~~~

TODO
=======
* Fix Readme.
* Add more variables. (logs and other stuff)
* Add tests.
* Add installation of different than 9.6 postgresql version.
* master ip should be dynamically generated.
