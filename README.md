Role : sshuttle
=========

Installs [sshuttle](https://sshuttle.readthedocs.io/en/stable/index.html) as a system service

![Ansible Role](https://img.shields.io/ansible/role/55708?logo=ansible)

Requirements
------------

SSH connectivity to the remote host specified in your config.
Linux system running systemd service handler

Role Variables
--------------

- sshuttle_user: The user under which the service will run
- sshuttle_group: The group under which the service will run
- sshuttle_package: name of the sshuttle package to install
- sshuttle_hosts: a dictionary od remote servers and their resolved subnets. This will be converted to json for the service configuration file
- sshuttle_options: Options from [manpage](https://sshuttle.readthedocs.io/en/stable/manpage.html) to describe the sshuttle connections in [shuttle.py](templates/shuttle.py.j2).
- sshuttle_args: Options from [manpage](https://sshuttle.readthedocs.io/en/stable/manpage.html) to describe additional arguments in [shuttle.py](templates/shuttle.py.j2).
- ssh_cmd_args: Options from [manpage](https://sshuttle.readthedocs.io/en/stable/manpage.html) to describe the ssh command in [shuttle.py](templates/shuttle.py.j2).


Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: jaredzieche.sshuttle }

License
-------

MIT

Author Information
------------------
[Jared Zieche](https://github.com/jaredzieche)
