# HW1
### CSC-DevOps-HW1-ArunJaganathan

Used Ubuntu Xenial for the VMs:
```
vagrant init ubuntu/xenial64
```
Uncommented the following in the Vagrant Files:

node0:
```
config.vm.network "private_network", ip: "192.168.33.40"
```

node1:
```
config.vm.network "private_network", ip: "192.168.33.41"
```

Inventory file Contents:

```
[node0]
192.168.33.40 ansible_ssh_user=vagrant ansible_ssh_private_key_file=keys/node2/private_key
[node1]
192.168.33.41 ansible_ssh_user=vagrant ansible_ssh_private_key_file=keys/node3/private_key
```

Command to start the playbooks:
```
ansible-playbook playbooks/script.yml -i inventory -e ansible_python_interpreter=/usr/bin/python3
```

Ansible script for setting up Coffeemaker - [coffeemaker_setup](coffeemaker_setup.yml)

Ansible script for setting up Test Env for Coffeemaker - [coffeemaker_test](coffeemaker_test.yml)

Link for Screencast - [here](https://youtu.be/I24dgWeVqCU)
