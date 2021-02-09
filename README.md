K8S MultiNode Cluster Role
=========

This is a role which can setup a Kubernetes multinode cluster over AWS Cloud platform. 

Requirements
------------

If you have your ec2 instances ready you need to create the inventory and before running this role add the IPs in the inventory and name the host group specifically as "master" and "worker". 

if you would want to create the ec2 instances there it self : You could find a playbook over my github which would spun scalable ec2 instances over your AWS cloud. [Link for the reference]( https://github.com/Dakshjain1/DevOps_Project_Files/tree/main/playbook_k8sMultiNodeCluster)
You could run the same and then run this role to setup the Kubernetes Multinode cluster over those instances. Manual addition in the inventory is not required in this case. 


Role Variables
--------------

No role variables are required for this role.

Dependencies
------------

Standalone role which works without depending over other roles.

Example Playbook
----------------
```
- hosts: master
  gather_facts: no
  tasks:
          - command: curl http://ipv4.icanhazip.com
            register: ip
          - debug:
                  var:  ip.stdout
          - name: Call the role
            include_role:
                    name: khushi20218.AnsibleGalaxy_K8SMultiNodeCluster
            vars:
                    master_ip: "{{ ip.stdout }}"
- hosts: worker
  gather_facts: no
  tasks:
          - command: curl http://ipv4.icanhazip.com
            register: ip 
          - debug:
                  var: ip.stdout
          - name: Call the role
            include_role:
                  name: khushi20218.AnsibleGalaxy_K8SMultiNodeCluster
                  
```

License
-------

BSD

Author Information
------------------

Role created by Khushi Thareja. 
For any queries or suggestion contact: https://www.linkedin.com/in/khushi-thareja/
