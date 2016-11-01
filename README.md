Certbot Ansible role
=========

Installs certbot from github sources. Fetch SSL certificate from Let's Encrypt CA for the target `ansible_host`.

[![Build Status](https://travis-ci.org/paulRbr/ansible-certbot-role.svg?branch=master)](https://travis-ci.org/paulRbr/ansible-certbot-role)

Example Playbook
----------------

Basic example playbook:

    - hosts: servers
      roles:
         - role: paulrbr.certbot
           cerbot_agree_tos: "--agree-tos"
           certbot_admin_email: "admin@example.org"
           certbot_www_dir: "/var/www"

License
-------

GPLv3
