# Ansible-IIS
Playbook to install IIS with some tuning

To use tasks individually, there's tags in the main.yml task.

**iis_install** an Ansible task to install Windows IIS
=========

This role handle Windows IIS installation, pool creation or modification, site creation or modification and binding creation or modification.


Requirements
------------

None


Role Variables
--------------

**IIS Web Install** related variables

| name | mandatory | defaults | description |
|------|:---------:|----------|-------------|
| ```webinstallftp``` | no | *empty string* | If set to 1, install the ftp part of IIS |


**Win Account** related variables

| name | mandatory | defaults | description |
|------|:---------:|----------|-------------|
| ```win_user_name``` | yes | *empty string* | Service user name |
| ```win_account_user_password``` | yes | win_account generated password | Service user password |


**IIS Web Pool** related variables

| name | mandatory | defaults | description |
|------|:---------:|----------|-------------|
| ```webpoolname``` | yes | *empty string* | **name** of the application pool |
| ```webpoolstate``` | no | 'present' | State of the application pool (absent, present, restarted, started, stopped |
| ```webpoolpipeline_mode``` | no | *empty string* | managedPipelineMode (Integrated or Classic) |
| ```webpoolmanagedRuntime_version``` | no | *empty string* | Runtime Version |
| ```webpoolautostart``` | no | *empty string* | Autostart (yes or no) |


**IIS Web Site** related variables

| name | mandatory | defaults | description |
|------|:---------:|----------|-------------|
| ```websitedefault``` | no | *empty string* | Set to 0 to remove Default Website |
| ```websitename``` | yes | *empty string* | **name** of the Website |
| ```websitestate``` | no | *empty string* | State of the Website (absent, started, stopped, restarted) |
| ```websiteport``` | no | *empty string* | Website port, used if there's not webbindport variable set or if values are differents |
| ```websiteip``` | no | *empty string* | Website ip, used if there's not webbindip variable set, if value are different or if websiteport and webbindport values are differents |
| ```websitepool``` | no | *empty string* | Application pool name |
| ```websitepath``` | no | *empty string* | The physical path on the IIS server host of the website files |
| ```websitessl``` | no | *empty string* | Enable ssl binding (not working due to an ansible bug) |
| ```websitelogdir``` | no | *empty string* | The physical path on the IIS server host of the website log files |


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

 - win_account Role for AD Service Account

Example Playbook
----------------

Examples playbook are included in tests: 

```bash
ansible-playbook test.yml
```


License
-------

BSD

Author Information
------------------

2019-08-09 - 
