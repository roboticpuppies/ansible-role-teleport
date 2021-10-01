ansible-role-teleport
=========

Ansible role to install [Teleport Access Plane](https://goteleport.com/docs/getting-started/)

Requirements
------------
For proxy node, please provide your own SSL certificate and key file. Place it under `/var/lib/teleport/webproxy_cert.pem` and `/var/lib/teleport/webproxy_key.pem`. Please make sure `openssl` package is installed. Otherwise self-signed certificate will be used.

Role Variables
--------------

Dependencies
------------

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

This role was created in 2021 by [M. Syaifuddin K.](https://msyaifuddin.my.id)