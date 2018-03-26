## Description
Here we use Ansible to setup and install our 4 node Kubernetes cluster. I forked the majority of these playbooks from [jeremievallee](https://github.com/jeremievallee/kubernetes-vagrant-ansible) who did a fantastic job sorting this out.

## Usage
Use Ansible to install and setup Kubernetes on the nodes
```
ansible-playbook playbook.yml -i inventory -e @vars.yml
```
