Role Name
=========

Configure and run Mesos components (master or slaves) in a docker container using the images `indigodatacloud/mesos-master:latest` or `indigodatacloud/mesos-slave:latest`.

This role has been specifically developed to be used for the deployment of Mesos in the framework of INDIGO-DataCloud project.

Role Variables
--------------

Common vars:

- `mesos_install_mode`: "master" or "slave"
- `zookeeper_peers`
- `zookeeper_client_port` (default: 2181)

Master

- `mesos_cluster_name` (default: "IndigoCluster")
- `mesos_version` (default: latest)
- `mesos_master_image` (default: "indigodatacloud/mesos-master:{{ mesos_version }}")
- `mesos_master_quorum` (optional)

Slave

- `mesos_executor_registration_timeout` (default: 10mins)
- `mesos_version` (default: latest)
- `mesos_slave_image`(default: "indigodatacloud/mesos-slave:{{ mesos_version }})
- `mesos_containerizers` (default: "docker,mesos")
- `mesos_slave_work_dir` (default: "/tmp/mesos")
- `mesos_masters_list`
 

Dependencies
------------

- `indigo-dc.docker`

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
