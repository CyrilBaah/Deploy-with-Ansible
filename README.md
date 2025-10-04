# Deploy with Ansible

Automated deployment of a static website to Ubuntu EC2 instances using Ansible.

## Project Structure

```
Deploy-with-Ansible/
├── inventory.ini          # Ansible inventory with EC2 instances
├── install_nginx.yml      # Ansible playbook for NGINX deployment
├── index.html            # Static HTML template
└── README.md             # This file
```

## Prerequisites

- Ansible installed on your local machine
- SSH access to EC2 instances
- Private key file (`webserver.pem`) in `~/.ssh/`

## Quick Start

1. **Test connectivity**
   ```bash
   ansible -i inventory.ini instances -m ping
   ```

2. **Deploy the website**
   ```bash
   ansible-playbook -i inventory.ini install_nginx.yml
   ```

## What it does

- Installs and configures NGINX on Ubuntu EC2 instances
- Deploys a static HTML page showing the instance's public IP
- Ensures NGINX is running and enabled

## Configuration

Update `inventory.ini` with your EC2 instance details:
- Replace IP addresses with your instances
- Ensure the SSH key path is correct
