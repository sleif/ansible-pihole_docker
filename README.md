sleif.pihole_docker
============

This role runs a pihole instance on docker.

Requirements
------------

Use it on a machine setup with ansible role sleif.docker.

Role Variables
--------------
- container_storage_dir_base: '/srv'
- docker_network_name (can be defined in sleif.docker)
- pihole_password
- pihole_external_web_port

* settings about local dns domain
- pihole_rev_server: False
- pihole_rev_server_target: 192.168.178.1
- pihole_rev_server_domain: fritz.box
- pihole_rev_server_cidr: "192.168.178.0/24"
- pihole_whitelist_entries: []

Dependencies
------------

Needs sleif.docker to make sure Docker is configured as needed.

Example Playbook
----------------

    - hosts: "server"
      user: root
      vars:
        docker_network_name: 'custom_docker_network'
      roles:
        - { role: sleif.pihole_docker, tags: "pihole_docker", pihole_external_web_port: '8081:80/tcp' }

License
-------

MIT

Author Information
------------------

Created in 2021 by Sebastian Berthold
