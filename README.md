Ansible Consul role
=========

This role create and start Consul agent into Docker container on your server.

Requirements
------------

This role requires:
  - ansible 2.2
  - dopy>=0.3.2

Role Variables
--------------

    consul_network: 'backend'
    consul_image: 'consul'
    consul_container_name: 'consul'

Example
----------------

Inventory should be looks like:

    localhost ansible_connection=local

    [machines]
    consul_master

Playbook should be looks like:

    - hosts: machines

      roles:
        - role: clayman74.consul
          consul_network: 'consul'
          consul_image: 'consul'
          consul_container_name: 'consul'

License
-------

MIT

Author Information
------------------

Kirill Sumorokov
