Role Name
=========

Joins an ubuntu machine to an active directory domain.

Requirements
------------


Role Variables
--------------

* `dc_hostname`: The hostname of the domain controller
* `ad_realm`: The active directory realm (e.g. domain.samdom.com)
* `ad_domain`: The domain shortname (e.g. SAMDOM)
* `ad_dc_ip`: The ip address of the domain controller.

Dependencies
------------


Example Playbook
----------------

```yml
- hosts: dm01
  become: yes
  vars:
    ad_dc_ip: "{{hostvars['dc01']['ansible_default_ipv4']['address']}}"
    dc_hostname: dc01
    ad_realm: "test.ptrampert.com"
    ad_domain: "ptrampert"
    ad_admin_pass: "Asdfasdf1"
  roles:
    - ubuntu-domain-member
```

License
-------

MIT

Author Information
------------------

https://github.com/PaulTrampert
