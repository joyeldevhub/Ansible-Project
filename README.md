# Ansible Infrastructure Automation Project

## Overview
This project automates the provisioning of infrastructure and deployment of services using Ansible. It includes playbooks and roles for setting up VPCs, security groups, EC2 instances, and service deployment.

## Directory Structure
```
ansible_project/
├── inventory/
│   └── hosts.ini
├── roles/
│   ├── common/
│   ├── vpc_setup/
│   ├── security_groups/
│   ├── jump_host/
│   ├── ami_creation/
│   ├── instance_provisioning/
│   └── service_deployment/
├── vars/
│   └── all.yml
├── playbooks/
│   ├── vpc_setup.yml
│   ├── security_groups.yml
│   ├── jump_host.yml
│   ├── ami_creation.yml
│   ├── instance_provisioning.yml
│   └── service_deployment.yml
├── group_vars/
│   ├── dev.yml
│   ├── staging.yml
│   └── production.yml
├── configs/
│   └── services.yml
├── .gitignore
└── README.md
```

## Setup and Running

### Prerequisites
- Ansible installed on your local machine.
- AWS account with appropriate permissions.
- SSH keys for accessing EC2 instances.

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/ansible_project.git
   cd ansible_project
   ```

2. Install Ansible if you haven't already:
   ```bash
   sudo apt-get update
   sudo apt-get install ansible
   ```

3. Configure your AWS credentials:
   ```bash
   aws configure
   ```

### Running Playbooks
1. **VPC Setup**:
   ```bash
   ansible-playbook playbooks/vpc_setup.yml -i inventory/hosts.ini --tags "vpc"
   ```

2. **Security Groups Setup**:
   ```bash
   ansible-playbook playbooks/security_groups.yml -i inventory/hosts.ini --tags "security_groups"
   ```

3. **Jump Host Setup**:
   ```bash
   ansible-playbook playbooks/jump_host.yml -i inventory/hosts.ini --tags "jump_host"
   ```

4. **AMI Creation**:
   ```bash
   ansible-playbook playbooks/ami_creation.yml -i inventory/hosts.ini --tags "ami"
   ```

5. **Instance Provisioning**:
   ```bash
   ansible-playbook playbooks/instance_provisioning.yml -i inventory/hosts.ini --tags "instances"
   ```

6. **Service Deployment**:
   ```bash
   ansible-playbook playbooks/service_deployment.yml -i inventory/hosts.ini --tags "deploy"
   ```

### Environment-Specific Configuration
Use the `group_vars` directory to manage environment-specific variables. For example, `group_vars/dev.yml` contains variables for the development environment.


This `README.md` file provides a comprehensive guide for anyone who wants to set up and run your Ansible project. Feel free to customize it further based on your project's specific needs.
