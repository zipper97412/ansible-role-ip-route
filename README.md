Ansible-Role-Ip-Route
=========

Configure ip routes with 'ip route' commands

Requirements
------------
* `iproute2`

Role Variables
--------------

```yaml
routes_default_gw: 172.17.0.254 #default gateway
routes_commands: # ip route commands to be run on post-up
  - ip route replace 172.18.0.0/24 via 172.17.0.1
  - ip route replace 172.18.1.0/24 via 172.17.0.2
```

Example Playbook
----------------
```yaml
---
- name: Configuring ip routes
  hosts: servers
  remote_user: root
  vars_files: ['var_routes.yml']  
  roles:
  - { role: ansible-role-ip-route }
```
License
-------
MIT
