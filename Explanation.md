# Execution Order Explanation

## Stage 1: Ansible Playbook
1. **Common Role**: Sets up base system requirements (Docker, dependencies)
2. **Database Role**: Configures and starts the database container
3. **Backend Role**: Sets up the backend API service
4. **Frontend Role**: Configures the user interface
5. **Proxy Role**: Sets up Nginx as a reverse proxy

## Stage 2: Terraform + Ansible
1. Terraform provisions the EC2 instance
2. Remote-exec provisions Python (required for Ansible)
3. Local-exec triggers the Ansible playbook
4. Ansible configures the application as in Stage 1

## Key Modules Used
- `docker_container`: Manages Docker containers
- `git`: Clones the application repository
- `apt`: Installs system packages
- `service`: Manages system services