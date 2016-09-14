andrewrothstein.zookeeper-cluster
=================================

Configures a zookeeper cluster. Assumes there are two groups:
* zookeeper: all zookeeper hosts voting or not
* zookeeper-quorum: voting members of the zookeeper cluster

Assumption is that all hosts in the zookeeper group but not in the zookeeper-quorum group are observers.

Requirements
------------

See [meta/main.yml]

Role Variables
--------------

See [defaults/main.yml]

Dependencies
------------

See [meta/main.yml]

Example Inventory/Playbook
----------------

inventory.ini
[zookeeper]
host1 zookeeper_myid=1
host2 zookeeper_myid=2
host3 zookeeper_myid=3
....
hostN zookeeper_myid=N

[zookeeper-quorum]
host[1:7]

playbook.yml
    - hosts: zookeeper
      roles:
         - andrewrothstein.zookeeper-cluster

License
-------

MIT

Author Information
------------------

Andrew Rothstein andrew.rothstein@gmail.com
