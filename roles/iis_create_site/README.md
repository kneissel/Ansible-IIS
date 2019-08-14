**iis_create_site** an Ansible role to create/modify Windows IIS site
=========

This role handle Windows IIS site creation or modification.

Requirements
------------

  - IIS already installed
  - IIS Application pool installed


Role Variables
--------------

**IIS Web Site** related variables

| name | mandatory | defaults | description |
|------|:---------:|----------|-------------|
| ```websitedefault``` | no | *empty string* | Set to 1 to delete Default Website |
| ```websitename``` | yes | *empty string* | **name** of the Website |
| ```websitestate``` | no | *empty string* | State of the Website (absent, started, stopped, restarted) |
| ```websiteport``` | no | *empty string* | Website port, used if there's not webbindport variable set or if values are differents |
| ```websiteip``` | no | *empty string* | Website ip, used if there's not webbindip variable set, if value are different or if websiteport and webbindport values are differents |
| ```websitepool``` | no | *empty string* | Application pool name |
| ```websitepath``` | no | *empty string* | The physical path on the IIS server host of the website files |
| ```websitessl``` | no | *empty string* | Enable ssl binding (not working due to an ansible bug) |
| ```websitelogdir``` | no | *empty string* | The physical path on the IIS server host of the website log files |


Dependencies
------------

  - iis_create_pool Role
  

Example Playbook
----------------

Examples playbook are included in tests: 

```bash
ansible-playbook iis_create_site.yml
```


License
-------

BSD

Author Information
------------------

2019-08-09 - 
