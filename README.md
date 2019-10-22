### ec2-with-apache-over-ansible

> *This repo has a playbook of running an apache server in EC2 instances using ansible*

###### Mainly four tasks has been used in this playbook

- creating an instance with exact count 1 and register it as __ec2__

- add this instance private IP to create host into the inventory file by using *__add_host__* module
  - *__add_host__* module use variables to create new hosts and groups in inventory for use in later plays of the same playbook.
- waiting for ssh to make the instance ready for ssh access by using *__wait_for__* module
  -  *__wait_for__* module will wait for a port to become available when services are not immediately available 
- installing apache using *__delegate_facts__* , creating index page and restart apache
  - By default, any fact gathered by a delegated task are assigned to the inventory_hostname (the current host) instead of the host which     actually produced the facts (the delegated to host)
