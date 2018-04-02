Certbot Ansible role
=========

Installs certbot from github sources. Fetch SSL certificate from Let's Encrypt CA for the target `ansible_host` domain.

[![Build Status](https://travis-ci.org/swcc/ansible-certbot-role.svg?branch=master)](https://travis-ci.org/swcc/ansible-certbot-role) [![Ansible Galaxy](https://img.shields.io/ansible/role/18534.svg)](https://galaxy.ansible.com/swcc/certbot-role/)

Example Playbook
----------------

Basic example playbook:

    - hosts: webservers
      roles:
         - role: swcc.certbot
           certbot_agree_tos: "--agree-tos"
           certbot_admin_email: "admin@example.org"
           certbot_www_dir: "/var/www" # Used to validate domains with http file verification. Make sure you serve `/.well-known` uri on your webserver with files from the specified `www_dir`.

Optional parameters
----------------

| Variable      | Type          | Description  |
| ------------- |:-------------:| ------------|
| `certbot_auto_renew` | `boolean` | Whether to auto renew your certificate with a cron setup |
| `certbot_deploy_hook`| `string`  | Command to execute after a successful renewed certificate. E.g. `/etc/init.d/nginx reload`. |
| `certbot_host` | `string`        | Custom domain used to issue the certificate (if not provided defaults to `ansible_host`) |
| `certbot_extra_hosts` | `array`  | A list of extra domains for which the certificate will be valid for (will provide a multi-domains certificate) |
| `certbot_cert_name`   | `string` | The filename of the issued certificate by certbot. This will ensure your certificate is at `/etc/letsencrypt/live/{{ certbot_cert_name }}/fullchain.pem` path on your server. |


Makefile for easier Ansible usage
------------------

I have written a small Makefile to make your future ansible runs easier. Don't hesitate to [check it out](https://github.com/paulRbr/ansible-makefile/blob/master/Makefile).

Download the `*.deb` package from the github releases, install it and start using it with `ansible-make help`.

License
-------

GPLv3
