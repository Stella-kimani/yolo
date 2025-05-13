# Configuration Management IP

This project automates the deployment of an e-commerce application using Ansible (Stage 1) and Ansible+Terraform (Stage 2).

## Requirements
- VirtualBox
- Vagrant
- Ansible
- (Optional) Terraform

## Stage 1: Ansible
1. Clone this repository
2. Run `vagrant up`

## Stage 2: Ansible + Terraform
1. Checkout to Stage_two branch
2. Run `./deploy.sh`

## Project Structure
- `Vagrantfile` - Vagrant configuration
- `ansible/` - Ansible playbooks and roles
- `terraform/` - Terraform configuration (Stage 2)