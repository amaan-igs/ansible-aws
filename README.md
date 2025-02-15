# Ansible Automation

## Overview

This Ansible project automates the installation and configuration of a web server (Apache) on Ubuntu instances. It includes playbooks, inventory, and templates to manage infrastructure efficiently.

## Prerequisites

- Ansible installed on your control machine.
- SSH access to target servers.
- A valid inventory file (`inventory.ini`).
- Public key authentication set up between the control node and target servers.

## Directory Structure

```plaintext
ansible/
├── inventory.ini
├── playbooks/
│   ├── playbook_web.yaml
│   ├── playbook_update.yaml
├── templates/
│   ├── index.html.j2
├── roles/
│   ├── apache/
│   │   ├── tasks/
│   │   │   ├── main.yaml
│   │   ├── templates/
│   │   │   ├── index.html.j2
│   │   ├── handlers/
│   │   │   ├── main.yaml
└── README.md
```

## Setup Instructions

1. **Install Ansible (if not installed):**

   ```ini
   sudo apt update && sudo apt install -y ansible
   ```

2. **Configure Inventory (inventory.ini):**

    ```bash
    [myhosts]
    node1.inotech-pk.com ansible_user=ubuntu ansible_ssh_private_key_file=~/keys/ansible
    ```

3. **Run Linter:**

    ```sudo
    sudo apt install -y ansible-lint
    ```

    ```bash
    ansible-lint playbooks/playbook.yaml 
    ```

4. **Run Playbooks:**

    ```bash
    ansible-playbook -i inventory.ini playbooks/playbook_web.yaml
    ```