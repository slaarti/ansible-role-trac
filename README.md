# Trac

This Ansible role installs the [Trac ticket tracking system][trac].

[trac]: http://trac.edgewall.org/

This role currently installs the package, and creates a `trac` user and
group. That's *it*.

It does *not* initialize or configure any particular Trac environment
(that kind of thing is complex, and also you may be importing/upgrading an
existing environment, as I am at the time of writing this, so this is
taken as a manual step). It does *not* do anything to initialize any kind
of Trac service (my recommendation is to use the [`cchurch.uwsgi`
role][cchurch] to run it under [uWSGI][], or present it as a site on the
Internet (I recommend the [`geerlingguy.nginx` role][geerlingguy] to front
the uWSGI service with [Nginx](http://nginx.org/)).

[cchurch]: https://github.com/cchurch/ansible-role-uwsgi
[uWSGI]: https://uwsgi-docs.readthedocs.org/en/latest/
[geerlingguy]: https://github.com/geerlingguy/ansible-role-nginx

Dependencies
------------

No explicit required dependencies, but see above when it comes to my
recommendations for what to do with Trac once this role installs the
package.

Example Playbook
----------------

    - hosts: servers
      roles:
         - slaarti.trac

License
-------

Unlicense; see the LICENSE file.

Author Information
------------------

Chris Pinard <slaarti@gmail.com>
