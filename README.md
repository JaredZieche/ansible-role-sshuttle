Role : sshuttle
=========

Installs [sshuttle](https://sshuttle.readthedocs.io/en/stable/index.html) as a system service

![Ansible Role](https://img.shields.io/ansible/role/55708?logo=ansible)

Requirements
------------

SSH connectivity to a remote host where tunnel will e established
Linux Host

Role Variables
--------------

- sshuttle_user: The user under which the service will run
- sshuttle_group: The group under which the service will run
- sshuttle_package: name of the sshuttle package to install
- sshuttle_hosts: a dictionary od remote servers and their resolved subnets. This will be converted to json for the service configuration file
- sshuttle_options: Options from [manpage](https://sshuttle.readthedocs.io/en/stable/manpage.html) to describe the sshuttle connections in [shuttle.py](templates/shuttle.py.j2).
- sshuttle_args: Options from [manpage](https://sshuttle.readthedocs.io/en/stable/manpage.html) to describe additional arguments in [shuttle.py](templates/shuttle.py.j2).
- ssh_cmd_args: Options from [manpage](https://sshuttle.readthedocs.io/en/stable/manpage.html) to describe the ssh command in [shuttle.py](templates/shuttle.py.j2).
- remote_auth: true/false, if true role will attempt to authorize user to remote tunnel host. Default is false.
- remote_ip: IP address of the remote host through which sshuttle will connect.
- remote_user: Username that can be used to authorize with remote_host.
- remote_hostname: name for the remote host entry in your .ssh/config.


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
