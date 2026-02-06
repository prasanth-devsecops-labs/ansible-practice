Shell drawbacks:

No idempotency
No error handling
Little complex
Large scale server handling is bit tough
Distribution specific, homogenous


Ansible:

Configuration Management:

Provisioning servers and baselining as per our needs.

installing programming languages
creating system users and folders
installing system packages
downloading code
installing dependencies
creating systemctl services
start and enabling services

Ansible uses push based config approach.
connects using ssh protocol.
Ansible also has pull based approach where agents are installed on nodes and nodes pulls
updates from master(control manager where ansible installed).

Ansible uses YAML language

Ansible modules/collections are similar to Linux commands.

Ansible-playbook is nothing but groups of tasks to be performed against nodes.

Inventory file is nothing but having it contains info of nodes IP address where playbook runs
against inventory


sudo dnf install ansible -y

ansible localhost -m ping

ansible localhost -b -m dnf -a "name:nginx state:installed"
ansible localhost -b -m service -a "name:nginx state:started"

ansible-playbook -i hosts.ini 01.playbook.yaml
ansible webapp -i hosts.ini --list-hosts
ansible-inventory -i hosts.ini --graph

varibales:
    Play level variables
    task level variables
    common variable file
    inventory level variables
    command line based variables

precendence will comes into picture while resolving variables.
