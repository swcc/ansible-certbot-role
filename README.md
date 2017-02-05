Certbot Ansible role
=========

Installs certbot from github sources. Fetch SSL certificate from Let's Encrypt CA for the target `ansible_host`.

[![Build Status](https://travis-ci.org/paulRbr/ansible-certbot-role.svg?branch=master)](https://travis-ci.org/paulRbr/ansible-certbot-role)

Example Playbook
----------------

Basic example playbook:

    - hosts: servers
      roles:
         - role: paulRbr.certbot
           certbot_agree_tos: "--agree-tos"
           certbot_admin_email: "admin@example.org"
           certbot_www_dir: "/var/www"
           certbot_auto_renew: true

Makefile for easier Ansible usage
------------------

I have written a small Makefile to make your future ansible runs easier. Don't hesitate to [check it out](https://github.com/paulRbr/ansible-makefile/blob/master/Makefile).

Copy it in your ansible configuration directory and start using it via `make help`.

License
-------

GPLv3
