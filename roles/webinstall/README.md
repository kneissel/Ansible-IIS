**webinstall** an Ansible role to install Windows IIS binding
=========

This role handle Windows IIS installation.

Install IIS Web service with all subs.

Optionally install IIS Ftp service with subs.


Requirements
------------

None


Role Variables
--------------

**IIS Web Install** related variables

| name | mandatory | defaults | description |
|------|:---------:|----------|-------------|
| ```webinstallftp``` | no | *empty string* | If set to 1, install the ftp part of IIS |


Dependencies
------------

None

Example Playbook
----------------

Examples playbook in global *tests* directory are included: 

```bash
ansible-playbook fullinstall.yml
or
ansible-playbook webinstall.yml
```


License
-------

BSD

Author Information
------------------

2019-08-09 - 
