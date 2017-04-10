nginx Ansible role
==================


This role will install nginx from the nginx PPA. It is very basic, and the
possible configuration pretty limited.

The intent is to have a basic config in place. Later, in your specific roles,
you just need to add entries in `/etc/nginx/sites-available`, link the file in
`/etc/nginx/sites-enable` and restart nginx.

Requirements
------------

None

Role Variables
--------------

  - `nginx_root`: web directory root for 'default' vhost (default: `/var/lib/nginx/`)
  - `nginx_worker_connections`: sets the maximum number of simultaneous connections that can be opened by a worker process (default: 1024)
  - `nginx_mode`: whether we'll run php5-fpm (default: php5-fpm)
  - `nginx_add_default`: do we add a default vhost (default: yes)

Tags
----

  - nginx

Dependencies
------------

None

Example Playbook
----------------

Specs
-----

To run tests locally in a Vagrant machine, just hit:

    vagrant up
    vagrant ssh -c specs

If you want to run the test playbook fast (i.e., without re-installing Ansible),
just run:

    vagrant ssh -c 'specs -p'

There is a sample Guardfile if you want to work on the role in TDD mode. You need to install guard and guard-shell gems, and then run guard:

    gem install guard
    gem install guard-shell
    guard

Now the specs will run whenever you save a file in the role, the specs will be run.

License
-------

MIT

Author Information
------------------

Created for @erasme by @leucos.

