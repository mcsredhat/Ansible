
## 📘 Ansible Cisco Configuration

This repository provides an Ansible playbook for automating the configuration of Cisco network devices using CLI commands.

### 📂 Contents

- **`ansible-cisco.txt`** *(recommended to rename to `cisco-playbook.yml`)*:  
  Ansible playbook containing tasks to configure Cisco IOS devices.

### 🧰 Requirements

- **Python 3**
- **Ansible** (recommended version: 2.9+)
- Cisco device(s) with SSH access
- Ansible collections for network automation (e.g., `cisco.ios`)

Install Ansible dependencies:
```
ansible-galaxy collection install cisco.ios
```

### 🚀 Usage

1. Rename the playbook:
   ```
   mv ansible-cisco.txt cisco-playbook.yml
   ```

2. Update the `hosts` file or inventory with your Cisco device details.

3. Run the playbook:
   ```
   ansible-playbook -i inventory.ini cisco-playbook.yml
   ```

> Make sure your device credentials and IP addresses are correctly set up in your inventory.

### 🛠 Example Tasks in the Playbook

This playbook can automate a variety of Cisco IOS configurations, including:

- 🔧 **Hostname Configuration**
- 🌐 **Interface Setup (IP addresses, descriptions, enabling interfaces)**
- 🧱 **VLAN Creation and Assignment**
- 🔁 **Routing Configuration (Static and Dynamic)**
- 🔒 **Enable Password and User Account Setup**
- 📡 **SNMP Configuration**
- 📜 **Logging and Syslog Setup**
- 🔁 **Spanning Tree Protocol (STP) Settings**
- 🌍 **NTP and Timezone Configuration**
- 🧮 **Access Control Lists (ACLs)**

### 🔒 Security Note

Avoid hardcoding passwords or sensitive information in your playbook. Use Ansible Vault for encryption:
```bash
ansible-vault encrypt group_vars/all.yml
```
