K8S MultiNode Cluster Role
=========

This is a role which can setup a Kubernetes multinode cluster over your local VMs as well as on any cloud platform. 

Requirements
------------

You could find a playbook over my github itself which would spun scalable ec2 instances over your cloud. You could run the same and then run this role to setup the Kubernetes Multinode cluster over those instances. One manual step is required before running this role which is to add the IPs in the inventory and name the host group specifically as "master" and "worker". 
If you want to create the cluster on your local VM, create the inventory manually and run this role over the ansible controller node. 

Role Variables
--------------

A description of the settable variables for this role should go here, including  any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

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
