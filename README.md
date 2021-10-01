ansible-role-teleport
=========

Ansible role to install [Teleport Access Plane](https://goteleport.com/docs/getting-started/) on a Linux server.

Requirements
------------
Each server has its role. Mainly there are 3 roles : auth, proxy, node. Please see [Teleport Architecture Overview](https://goteleport.com/docs/architecture/overview/)

For proxy node, please provide your own SSL certificate and key file. Place it under `/var/lib/teleport/webproxy_cert.pem` and `/var/lib/teleport/webproxy_key.pem`. Please make sure `openssl` package is installed. Otherwise self-signed certificate will be used.

Role Variables
--------------

Dependencies
------------
None.

Example Playbook
----------------

Example playbook for node servers.

    - hosts: node
      vars:
        teleport_auth_servers: "auth.example.com:3025"
        teleport_auth_token: "abc-xyz"
      roles:
         - { role: roboticpuppies.teleport}

After you deploy an auth server, you must create your first Teleport user. For example you can use this command to create user with username `teleport-admin` with roles `editor,access` and is allowed to log into SSH hosts as any of the principals `root`, `ubuntu` or `ec2-user`

```
tctl users add teleport-admin --roles=editor,access --logins=root,ubuntu,ec2-user
```
You will be provided an URL to set that user's password.

Please see Teleport [getting started guide](https://goteleport.com/docs/getting-started/linux-server/)

License
-------

BSD

Author Information
------------------

This role was created in 2021 by [M. Syaifuddin K.](https://msyaifuddin.my.id)