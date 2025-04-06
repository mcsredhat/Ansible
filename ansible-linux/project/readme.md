
# Infrastructure Automation Project using Ansible

This project outlines a complete setup of a web application infrastructure using Ansible. It includes a **database server**, **application server**, and a **load balancer**, all configured and deployed through Ansible playbooks.

---

## 🗃️ Components Overview

1. **Database Server (Host 1)** – MySQL setup and configuration.
2. **Application Server (Host 2)** – Apache, PHP, and web app deployment.
3. **Load Balancer (Host 3)** – HAProxy setup to distribute traffic.

---

## 📦 1. Database Server Setup (Host 1)

### ✅ Objective
- Install MySQL.
- Configure a user and database.
- Ensure the MySQL service is running.

### 🛠️ Steps
- Use an Ansible playbook to install MySQL, create a database and user.
- Connect to the MySQL server using CLI to verify setup.

### ▶️ Ansible Command
```
ansible-playbook -i inventory.ini setup_database.yml
```

---

## 🖥️ 2. Application Server Setup (Host 2)

### ✅ Objective
- Install Apache and PHP.
- Deploy a PHP-based web application.
- Configure the app to connect to the MySQL database.

### 🛠️ Features
- PHP app with a user registration form.
- Stores user data in MySQL.
- Displays registered users.
- Uses Ansible’s `template` module to inject DB credentials securely.

### ▶️ Ansible Command
```
ansible-playbook -i inventory.ini setup_app_server.yml
```

---

## 🌐 3. Load Balancer Setup (Host 3)

### ✅ Objective
- Install and configure HAProxy.
- Balance traffic between multiple application servers.

### 🛠️ Steps
- Use Ansible to install and configure HAProxy.
- Set up frontend and backend configurations to point to the application server.

### ▶️ Ansible Commands
```
ansible-playbook -i inventory.ini haproxy_setup.yml
ansible-playbook -i inventory.ini haproxy_configure.yml
```

---

## 🧪 Testing & Validation

- **Access Test**: Run `curl http://<load_balancer_ip>` to verify access.
- **Traffic Distribution**: Check `/var/log/haproxy.log` on the load balancer.
- **DB Connectivity**: SSH into Host 2 and confirm it can reach the MySQL database on Host 1.

---

## ✅ Tools Used

- Ansible
- Apache
- PHP
- MySQL
- HAProxy
- CentOS (assumed for `yum` usage)

---

## 📎 Notes

- Ensure proper IP addresses and hostnames in the Ansible inventory file.
- Secure credentials using Ansible Vault in production environments.
- Use `.gitignore` to avoid committing sensitive files or large binaries.

---
