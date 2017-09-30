Certbot Ansible role
=========

Installs certbot from github sources. Fetch SSL certificate from Let's Encrypt CA for the target `ansible_host`.

[![Build Status](https://travis-ci.org/swcc/ansible-certbot-role.svg?branch=master)](https://travis-ci.org/swcc/ansible-certbot-role) [![Ansible Galaxy](https://img.shields.io/ansible/role/18534.svg)](https://galaxy.ansible.com/swcc/certbot-role/)

Example Playbook
----------------

Basic example playbook:

    - hosts: webservers
      roles:
         - role: swcc.certbot
           certbot_agree_tos: "--agree-tos"
           certbot_admin_email: "admin@example.org"
           certbot_www_dir: "/var/www"
           certbot_auto_renew: true
           certbot_deploy_hook: "/etc/init.d/nginx reload"

Makefile for easier Ansible usage
------------------

I have written a small Makefile to make your future ansible runs easier. Don't hesitate to [check it out](https://github.com/paulRbr/ansible-makefile/blob/master/Makefile).

Copy it in your ansible configuration directory and start using it via `make help`.

License
-------

GPLv3
