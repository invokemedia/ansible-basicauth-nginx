Ansible Letsencrypt Nginx
=========================

> Ansible script that sets up basic auth for Nginx

Requirements
------------

This role assumes you already have Nginx installed. It also assumes you have a line in your Nginx conf like `try_files $uri $uri`.

Installation
------------

`git clone https://github.com/invokemedia/ansible-basicauth-nginx roles/invokemedia.basicauth-nginx`

Role Variables
--------------

```
# username to use
auth_username: authuser
# password to use
auth_password: mypassword
# the nginx conf file to update
auth_nginx_conf: /etc/nginx/sites-enabled/default
```

Dependencies
------------

None.

Example Playbook
-------------------------

Here is how you would use the default setup setup.

```
- hosts: web
  sudo: yes
  vars:
    auth_username: authuser
    auth_password: mypassword
  roles:
    - { role: invokemedia.basicauth-nginx }
```

License
-------

MIT

Author Information
------------------

* [Invoke Media](http://www.invokemedia.com/)
* <webmaster@invokemedia.com>

References
----------

* [certbot installation docs](https://certbot.eff.org/#ubuntuxenial-nginx)
