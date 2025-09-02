# 🚀 Ansible Web Server Automation (Role-based)

This project demonstrates how to use **Ansible Roles** to automate the deployment and configuration of an **Nginx web server**.  
It covers installing Nginx, deploying a custom HTML page, and configuring the firewall (UFW) to allow HTTP traffic.

---

## 📌 Overview

- 📂 Uses **roles** for modular, production-style automation  
- 📝 Installs and configures **Nginx** web server  
- 🔄 Uses **handlers** to restart services only when needed  
- 🧩 Deploys a **Jinja2 template** as a custom `index.html`  
- 🔐 Configures **UFW firewall** to allow HTTP traffic (port 80)  
- ⚡ Fully **idempotent** – running it multiple times won’t cause issues  

---

## 📂 Project Structure

---

## ⚙️ Requirements

- **Control Node:**  
  - Ansible installed  
    - macOS: `brew install ansible`  
    - Linux: `sudo apt install ansible -y` or `pip install ansible`  

- **Target Host(s):**  
  - Ubuntu/Debian server  
  - SSH access with key authentication  
  - UFW firewall enabled (remove firewall task if not needed)  

---

## ▶️ Usage

1. **Clone the repository:**
   ```bash
   git clone https://github.com/<your-username>/ansible-webserver.git
   cd ansible-webserver
## Update the inventory file (inventory/hosts.ini):
  ```bash
[webservers]
192.168.56.10 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/id_rsa
```

## Run the playbook:
  ```bash
ansible-playbook -i inventory/hosts.ini playbooks/deploy-nginx.yml
```

Verify deployment:
  ```bash
curl http://192.168.56.10


Or open http://192.168.56.10 in your browser.
```
## 🔑 Key Features

✅ Role-based modular structure

✅ Idempotent automation (safe to run multiple times)

✅ Dynamic content using Jinja2 templates

✅ Handlers for efficient service management

✅ Firewall automation with UFW

## 🎯 Learning Outcomes

By working with this project, you will learn how to:

Write role-based playbooks in Ansible

Use handlers and templates effectively

Manage firewall rules with Ansible modules

Build scalable and reusable automation for infrastructure

## 🌟 Next Steps

Add SSL (using Let’s Encrypt / Certbot role)

Add a PostgreSQL or Docker role for multi-service automation

Use Ansible Vault to secure sensitive data

Extend with GitHub Actions CI/CD for automation pipelines
