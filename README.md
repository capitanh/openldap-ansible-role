OpenLDAP Ansible Role
=====================
This role installs openldap and loads some example data

Requirements
------------
None

Role Variables
--------------
This role requires the following variables to be defined elsewhere in the playbook that uses it:
```yaml
    ldap_basedn:       dc=golili,dc=net           # Base DN
    ldap_server_uri:   ldap://localhost:389       # LDAP server URI
    ldap_bind_pw:      secret                     # bind password
```

Additionally, to load users and groups, you should define the following structure
```yaml
    ldap_users:
      user_id1:
        cn: Name1 Surname1
        givenname: Name1
        sn: Surname1
        mail: userid1@golili.net
        userpassword: password
      user_id2:
        cn: Name2 Surname2
        givenname: Name2
        sn: Surname2
        mail: userid2@golili.net
        userpassword: password
    ldap_groups:
      - name: group1
        members:
          - user_id1
      - name: group2
        members:
          - user_id1
          - user_id2
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
