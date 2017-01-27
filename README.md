Ansible MySQL database and users [![Build Status](https://travis-ci.org/ewypych/mysql-db-user.png?branch=master)](https://travis-ci.org/ewypych/mysql-db-user)
=========

This role creates one or more MySQL databases and users with privileges for them.

Requirements
------------

Requires the MySQLdb Python package on the remote host.

Role Variables
--------------

```yaml
# vars/main.yml
databases:
  testingadb:
    name: testdb
    user: adm_test
    userhost: localhost
    password: "{{ db_pass_test }}"
  seconddb:
    name: seconddb
    user: adm_second
    userhost: localhost
    password: "{{ db_pass_second }}"

# vars/secure.yml
mysql_root_pass: rootpassword
db_pass_test: Mnbvcxz
db_pass_second: Zxcvbnm
```
You can Vault the secure.yml file.

There are some default variables stored in the defaults/main.yml file - you can change them to the your ones.

```yaml
# defaults/main.yml
mysql_root: "root"
mysql_port: 3306
```

Example Playbook
----------------

```yaml
    - hosts: all
      roles:
         - mysql-db-user
```

License
-------

[MIT](https://tldrlegal.com/license/mit-license)

Author Information
------------------

[Emil Wypych](https://github.com/ewypych) [@gmail](wypychemil@gmail.com)
