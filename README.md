# EC2 Instance Management with Ansible

This repository contains Ansible playbooks for managing AWS EC2 instances, including provisioning a new EC2 instance and resizing the EBS volume.

## Prerequisites

- Ansible installed on your local machine.
- An AWS account with necessary permissions to create EC2 instances and manage EBS volumes.
- Ansible Vault (for securely storing AWS credentials).
- SSH key pair (`my_aws.pem`) for accessing the EC2 instance.

## Setup

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/ec2-instance-management.git
   cd ec2-instance-management

2. **Create a Vault file to store AWS credentials:**

   ```bash
   ansible-vault create vault.yml

3. **Create an SSH key pair (if you don't have one already):**
    
    ```bash
    ssh-keygen -t rsa -b 4096 -f ~/.ssh/my_aws 
This will create a public and private key pair (my_aws and my_aws.pub).

## Tasks

### 1. Provision EC2 Instance

This playbook provisions a new EC2 instance in AWS, including the creation of a security group and a key pair for SSH access.

- **Playbook:** `ec2_provision.yml`

- **Usage:**

   ```bash
   ansible-playbook ec2_provision.yml --tags create_ec2 --vault-password-file vault.pass

