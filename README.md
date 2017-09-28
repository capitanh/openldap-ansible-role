OpenLDAP Ansible Role
=========

This role installs openldap and loads some example data

Requirements
------------

None

Role Variables
--------------

This role requires the following variables to be defined elsewhere in the playbook that uses it:
```yaml
ldap_username:         admin							# LDAP root user name
ldap_password:         secret							# LDAP root password
ldap_basedn:           dc=golili,dc=net   # Base DN
```

Dependencies
------------

None

Example Playbook
----------------

Register the role in requirements.yml:
```yaml
- src: capitanh.openldap-ansible-role
  name: openldap
```
Include it in your playbooks:
```yaml
- hosts: servers
  roles:
    - openldap
```

License
-------

BSD
