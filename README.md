Ansible Consul role
=========

[![Build Status](https://travis-ci.org/clayman74/ansible-consul.svg?branch=master)](https://travis-ci.org/clayman74/ansible-consul)

This role create and start Consul agent into Docker container on your server.

Requirements
------------

This role requires:
  - ansible 2.2
  - dopy>=0.3.2

Role Variables
--------------

    consul_install_in_docker: no

    consul_network: backend
    consul_image: consul
    consul_container_name: consul

    consul_log_driver: json-file
    consul_log_options:
      labels: consul

    consul_client_interface: eth0

    consul_published_ports:
      - 8500:8500

    consul_restart_policy: on-failure


Docker conitainer [logging settings](https://docs.docker.com/engine/admin/logging/overview/)


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
