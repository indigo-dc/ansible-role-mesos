Mesos Role
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
- `mesos_image_version` (default: latest)
- `mesos_master_image` (default: "indigodatacloud/mesos-master:{{ mesos_image_version }}")
- `mesos_master_quorum` (optional)

Slave

- `mesos_executor_registration_timeout` (default: 10mins)
- `mesos_image_version` (default: latest)
- `mesos_slave_image`(default: "indigodatacloud/mesos-slave:{{ mesos_image_version }})
- `mesos_containerizers` (default: "docker,mesos")
- `mesos_slave_work_dir` (default: "/tmp/mesos")
- `mesos_masters_list`
 

Dependencies
------------

- `indigo-dc.docker`

Example Playbook
----------------

This is an example of how to use `mesos` role:

For "master" nodes:

    - hosts: servers
      roles:
         - { role: indigo-dc.mesos, mesos_install_mode: "master", zookeeper_peers: ["10.10.0.1", "10.10.0.2", "10.10.0.3"], mesos_masters_list: ["10.10.0.10", "10.10.0.11", "10.10.0.12"] }

For "slave" nodes:

    - hosts: servers
      roles:
         - { role: indigo-dc.mesos, mesos_install_mode: "slave", zookeeper_peers: ["10.10.0.1", "10.10.0.2", "10.10.0.3"], mesos_masters_list: ["10.10.0.10", "10.10.0.11", "10.10.0.12"] }

License
-------

Apache Licence v2 [1]

[1] http://www.apache.org/licenses/LICENSE-2.0


