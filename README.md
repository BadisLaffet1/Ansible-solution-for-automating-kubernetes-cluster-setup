
# Ansible Solution for Automating Kubernetes Cluster Setup

This Ansible project automates the setup of a Kubernetes cluster using Ansible playbooks. It simplifies the process of configuring the Kubernetes master and joining worker nodes to the cluster.

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


