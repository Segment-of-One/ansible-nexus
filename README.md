Role Name
=========

Ansible Sonatype Nexus role. Completely independent from any package manager.
Does not require root or sudo permission to run.

TODO
----
- Add datadir (plus entry nexus-work={{datadir}} in conf/nexus.properties
- Change default admin account (admin/admin123)



Role Variables
--------------

- **nexus_download_dir**: download path on the control machine that will be used. Defaults to *'/tmp'*
- **nexus_version**: Nexus version to be installed. Defaults to *'latest'*
- **nexus_installation_dir**: installation prefix that will be used on installation hosts. Defaults to *'/usr/share'*
- **nexus_work_dir**: working directory, aka sonatype-work
- **nexus_port**: TCP port

Dependencies
------------

wget (on host, not on clients)

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: jhinrichsen.nexus, nexus_installation_dir: '/opt' }

Testing
--------

Testing is done with [molecule](https://molecule.readthedocs.io/en/stable/). 
Install molecule with

    pip install molecule

Make also sure you have `docker` installed on your machine (and you can run docker commands).

Test molecule playbook with:

    molecule test

This tests include `yamllint`, `ansible-lint`, a test run for the playbook and an idempotence test and some asserts to check after the installation.

License
-------

MIT

Author Information
------------------

This playbook is heavily inspired by Alexander Ramos Jardim.
Any errors are probably my fault.
