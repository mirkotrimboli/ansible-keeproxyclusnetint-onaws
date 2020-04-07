# ansible-keeproxyclusnetint-onaws
Delivery of an HAproxy cluster exposed inside with Network Interface managed by keepalived on AWS

# AWS prerequisites
Make sure that the AWS environment has:

* Service Group with open Inbound rules for SSH connection
* that an ip has been given to the primary network card of each node
* that a Network Interface not associated with any node has been created in the same subnet and in same Service Groups

On the Ansible server:

* Download with git clone
* Inside the inventory path insert the "key.pem" for access in SSH
* Inside the inventory path, insert the awscliv2.zip package
* Modify the hosts file of the ansible server by adding the ip of the hosts to reach and naming them as specified in keeproxy.hosts

# Installation and initial configuration of the nodes

* check the variable in group_vars/all.yml
* if necessary change the values ​​of the variables according to your environment

launch the ansible playbook with the command:

* ansible-playbook -i keeproxy.hosts keeproxy.yml --key-file =./key.pem
