**webbind** an Ansible role to create/modify Windows IIS binding
=========

This role handle Windows IIS binding creation or modification.

Requirements
------------

  - IIS already installed
  - An existing IIS website


Role Variables
--------------

**IIS Web Site** related variables

| name | mandatory | defaults | description |
|------|:---------:|----------|-------------|
| ```websitename``` | yes | *empty string* | **Name** of existing IIS website |

**IIS Web Binding** related variables

| name | mandatory | defaults | description |
|------|:---------:|----------|-------------|
| ```webbindprotocol``` | no | 'http' | Binding protocol (http, https or ftp) |
| ```webbindport``` | no | '80' | Binding port |
| ```webbindip``` | no | '*' | Binding ip, the default value mean all server ip |
| ```webbindheader``` | no | *empty string* | host header |
| ```webbindcerthash``` | no | *empty string* | Certificate hash (thumbprint) for the SSL binding |
| ```webbindflag``` | no | *empty string* | ssl_flags, used to enable or disable ssl, actually not working in ansible due to a bug |
| ```webbindstate``` | no | 'present' | State of the Binding (absent or present) |


Dependencies
------------

  - webinstall Role
  - webpool Role
  - website Role

Example Playbook
----------------

Examples playbook in global *tests* directory are included: 

```bash
ansible-playbook install.yml
or
ansible-playbook webbind.yml
```


License
-------

BSD

Author Information
------------------

2019-08-09 - 
