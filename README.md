splunk-license-master
=========

Configures an existing Splunk Enterprise installation into a license master.

Requirements
------------

None.

Role Variables
--------------

|Variable|Default|
|--------|-------|
|`splunk_os_user`|splunk|
|`splunk_os_group`|splunk|
|`splunk_license_folder`|`/opt/splunk/etc/licenses/enterprise/`|
|`splunk_primary_license_file` | - |
|`splunk_alternative_license_file`| - |
|`splunk_license_type`|Enterprise|

Simply put the content of your Splunk Enterprise license file into the `splunk_primary_license_file` variable (ideally encrypted with ansible-vault). This is the only required variable.

There's also a `splunk_alternative_license_file` variable in case you want to provide a second license file for any reason.

Dependencies
------------

[`andrewmackett.splunk_common`](https://galaxy.ansible.com/andrewmackett/splunk_common)

Example Playbook
----------------

Example of passing the license file inline. This variable should really be encrypted with ansible-vault.

    - hosts: servers
      roles:
         - role: andrewmackett.splunk_license_master
           splunk_primary_license_file: |
             <?xml version="1.0" encoding="UTF-8"?>
             <license>
               <signature>KszXkdrH4swieCeFTY7XEVYcrCOh8ZrwaFCu2vu2dw==</signature>
               <payload>
                 ...
               </payload>
             </license>


License
-------

MIT

Author Information
------------------

https://github.com/andrewmackett
