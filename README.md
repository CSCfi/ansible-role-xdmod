ansible-role-xdmod
=========

Configure and install XDMOD

http://xdmod.sourceforge.net/architecture.html

Requirements
------------

 - EPEL is added via provisioning

Role Variables
--------------

See defaults/main.yml

These variables are False by default. If you want to import schemas/mess with the tar ball then set these variables to True while running ansible.
<pre>
 xdmod_import_schemas: False
 xdmod_tarball_install: False
</pre>

Example ansible:
<pre>
ansible-playbook -i hosts xdmod.yml -e xdmod_tarball_install=True -e xdmod_import_schemas=True
</pre>

These variables needs to be defined with the username/password for xdmod's dbuser
<pre>
 xdmod_db_user: ""
 xdmod_db_pass: ""
</pre>

Dependencies
------------


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: ansible-role-xdmod }

License
-------

MIT

Author Information
------------------
