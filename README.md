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

Most of these variables need to be defined or overwritten. Check default/main.yml file for more.

<pre>
xdmod_db_user: ""
xdmod_db_pass: ""

xdmod_org:
  - { name: "Organization name", abbrev: "Organization abbreviation" }

xdmod_updtchck:
  - { email: "email", name: "name", org: "organization", enabled: true }

xdmod_resources:
  - { resource: "shortName", resource_type_id: "1", name: "longName" }

xdmod_resource_specs:
  - { resource: "shortName", processors: "60", nodes: "5", ppn: "12" }

xdmod_logofile_name: "organization-logo.jpg"

xdmod_psets_siteAddr: "http://localhost:8080/"

xdmod_psets_contact_page_recipient: "email@example.com"
xdmod_psets_tech_support_recipient: "email@example.com"

xdmod_psets_center_logo: "/etc/xdmod/{{ xdmod_logofile_name }}"
xdmod_psets_center_logo_width: "154"

xdmod_psets_mailer_sender_name: "Admin Name"
xdmod_psets_mailer_sender_email: "{{ xdmod_psets_tech_support_recipient }}"

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
