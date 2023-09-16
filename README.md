
# Ansible Solution for Automating Kubernetes Cluster Setup

This Ansible project automates the setup of a Kubernetes cluster using Ansible playbooks. It simplifies the process of configuring the Kubernetes master and joining worker nodes to the cluster.

This Ansible project was inspired by Chad Crouch workings in opensourcegeeks.

Char Crouch is a GoLang Fanatic & FullStack Geek experienced in multiple enterprise environments. he has a huge passion for the open-source world specifically Linux and Opensource Software.



## Table of Contents

- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
  - [Inventory](#inventory)
  - [Creating Kubernetes Cluster](#creating-kubernetes-cluster)
- [Ansible Playbooks](#ansible-playbooks)
- [Contributing](#contributing)
- [License](#license)

## Prerequisites

Before using this Ansible project, make sure you have the following prerequisites installed and configured on your control machine:

- Ansible: [Installation Guide](https://docs.ansible.com/ansible/latest/installation_guide/index.html)
- SSH access to target machines (controller and worker nodes)
- Basic knowledge of Kubernetes concepts

## Getting Started

### Inventory

Before running the Ansible playbooks, ensure that you have configured your inventory. The `inventory.ini` file should contain details of the controller and worker nodes where you want to set up the Kubernetes cluster. Update the inventory file with your machine details.

Example `inventory.ini`:

```ini
[controller]
controller ip=192.168.187.133 
[workers]
worker ip==192.168.187.135 
```



Replace 192.168.187.133, 192.168.187.135, etc., with the actual IP addresses of your machines.

Creating Kubernetes Cluster
To set up the Kubernetes cluster, follow these steps:

Configure your inventory as mentioned above.

Run the users.yml playbook to create a kube user on all nodes. This user will be used for managing Kubernetes.

```bash
ansible-playbook -i inventory.ini users.yml
```

Run the k8s-install.yml playbook to install Kubernetes on both the controller and worker nodes.


```bash
ansible-playbook -i inventory.ini k8s-install.yml
```

Use the master.yml playbook to create the Kubernetes master node.

```bash
ansible-playbook -i inventory.ini master.yml
```

Finally, run the workers.yml playbook to join the worker nodes to the Kubernetes cluster.


Your Kubernetes cluster should now be set up and ready to use.


```bash
ansible-playbook -i inventory.ini workers.yml
```

Ansible Playbooks
This project includes several Ansible playbooks to automate the Kubernetes setup process:

-users.yml: Creates a kube user on all nodes.
-k8s-install.yml: Installs Kubernetes on the controller and worker nodes.
-master.yml: Sets up the Kubernetes master node.
-workers.yml: Joins the worker nodes to the Kubernetes cluster.


Feel free to customize these playbooks to suit your specific requirements.




