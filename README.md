# Human Gov Infrastructure

Infrastructure automation project using **Terraform** and **Ansible**.  
This repository demonstrates a practical approach to provisioning infrastructure and configuring servers using Infrastructure as Code (IaC).

Terraform is responsible for creating the infrastructure, while Ansible is used to configure and manage the servers after provisioning.

---

## Overview

This project is built to follow real-world DevOps practices:

- Infrastructure provisioning using Terraform
- Server configuration using Ansible
- Clear separation between infrastructure and configuration
- Repeatable and predictable deployments

---

## Repository Structure

<pre>
human-gov-infrastructure-with-terrafrom-and-ansible/
│
├── terraform/
│   ├── main.tf
│   ├── provider.tf
│   ├── variables.tf
│   └── outputs.tf
│
├── ansible/
│   ├── ansible.cfg
│   ├── hosts
│   ├── deploy-humangov.yml
│   ├── install-webserver-conditionals.yml
│   ├── create-folders-with-loop.yml
│   └── example-vars.yml
│
├── .gitignore
└── README.md
</pre>
---

## Tools Used

- **Terraform** – Infrastructure provisioning  
- **Ansible** – Configuration management  
- **Linux** – Target operating system  
- **SSH** – Remote server access  

---

## Prerequisites

Make sure the following are available before running the project:

- Terraform installed
- Ansible installed
- SSH key configured for remote access
- Cloud credentials configured for your environment

---

## Usage

### 1. Clone the Repository

```bash
git clone <repository-url>
cd human-gov-infrastructure-with-terrafrom-and-ansible
2. Provision Infrastructure with Terraform
bash
Copy code
cd terraform
terraform init
terraform plan
terraform apply
Terraform will create the required infrastructure resources.

3. Configure Ansible Inventory
Edit the Ansible inventory file:

bash
Copy code
ansible/hosts
Example:

ini
Copy code
[web]
<server-ip> ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/id_rsa
4. Run Ansible Playbooks
Install and configure the web server:

bash
Copy code
cd ansible
ansible-playbook -i hosts install-webserver-conditionals.yml
Deploy application files:

bash
Copy code
ansible-playbook -i hosts deploy-humangov.yml
Create directories using loops:

bash
Copy code
ansible-playbook -i hosts create-folders-with-loop.yml
What This Project Demonstrates
Infrastructure creation using Terraform

Ansible playbooks with conditions and loops

Inventory and variable management

Common automation patterns used in DevOps environments

Notes
Terraform is used only for infrastructure provisioning

Ansible handles configuration and application setup

Playbooks are written to be idempotent and reusable

