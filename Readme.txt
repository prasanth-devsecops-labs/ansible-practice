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


variable precedence from top to bottom
1. command line args
2. task level
3. file level
4. prompt level
5. play/global level
6. inventory level


conditions: 
    when: condition(true/false)

loops: {{ item }}
    loop:
        - item 1
        - item 2

loop: {{ item.key, item.value }}
    - { key : value, key : value }
    - { key : value, key : value }

register variable to store previous run command outcome
set_fact to set custom variable

gather facts using : ansible_facts

filters: to VAR_NAME | FILTER  example: to_nice_json, dict2items, items2dict etc..

Ansible builtin command vs shell
command:  more secure, less features to access like | and > will not works.
shell: less secure, all shell environment accessible and all features works here like | and >

list [ ]
map { }
string ""
bool true/false


test
