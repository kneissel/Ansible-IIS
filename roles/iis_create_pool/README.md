**iis_create_pool** an Ansible role to create/modify Windows IIS pool
=========

This role handle Windows IIS pool creation or modification.

Requirements
------------

  - IIS already installed


Role Variables
--------------

**IIS Web Pool** related variables

| name | mandatory | defaults | description |
|------|:---------:|----------|-------------|
| ```webpoolname``` | yes | *empty string* | **name** of the application pool |
| ```webpoolstate``` | no | 'present' | State of the application pool (absent, present, restarted, started, stopped |
| ```webpoolpipeline_mode``` | no | *empty string* | managedPipelineMode (Integrated or Classic) |
| ```webpoolservice_user``` | no | *empty string* | Service user name |
| ```webpoolservice_password``` | no | win_account generated password | Service user password |
| ```webpoolmanagedRuntime_version``` | no | *empty string* | Runtime Version |
| ```webpoolautostart``` | no | *empty string* | Autostart (yes or no) |


Dependencies
------------

  - iis_install Role
  - win_account Role for AD Service Account
  

Example Playbook
----------------

Examples playbook are included in tests: 

```bash
ansible-playbook iis_create_pool.yml
```


License
-------

BSD

Author Information
------------------

2019-08-09 - 
