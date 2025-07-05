#  Apache Tomcat Installation using Ansible

This repository contains an Ansible playbook and role for automating the installation and configuration of **Apache Tomcat 10** on remote Linux servers (Debian/Ubuntu-based).

---

## 📁 Project Structure
```txt
.
├── inventory
│   └── hosts
├── roles
│   └── tomcat
│       ├── defaults
│       │   └── main.yml
│       ├── files
│       ├── handlers
│       │   └── main.yml
│       ├── meta
│       │   └── main.yml
│       ├── tasks
│       │   └── main.yml
│       ├── templates
│       │   ├── context.xml-host-manager.j2
│       │   ├── context.xml-manager.j2
│       │   ├── tomcat-users.xml.j2
│       │   └── tomcat.service.j2
│       └── vars
│           └── main.yml
└── tomcat.yml
```


## 📦 Features

- Installs Java (OpenJDK)  
- Downloads and extracts Apache Tomcat 10  
- Configures a dedicated `tomcat` system user and group  
- Deploys secure `tomcat-users.xml` with admin and manager roles  
- Configures access for `/manager` and `/host-manager` apps  
- Creates a `systemd` service for managing Tomcat  
- Starts and enables the Tomcat service on boot

## 📋 Inventory Example

Edit the `inventory/hosts` file and define your target servers:

```ini
[servers]
10.10.10.18
10.10.10.19
```

.

## 🚀 Usage
1. Clone the repository
```bash
git clone https://github.com/mehdi-khaksari/install-apache-tomcat-ansible.git
cd install-apache-tomcat-ansible
```
2. Run the playbook
```bash
ansible-playbook -i inventory/hosts tomcat.yml
```

## 🌐 Access After Deployment
Once the playbook is complete:

- Tomcat is available at: http://<your-server-ip>:8080

- Manager App: http://<your-server-ip>:8080/manager/html

- Host Manager: http://<your-server-ip>:8080/host-manager/html


# 📬 Contact
Feel free to fork, improve, and contribute!

Author: mehdi khaksari 

Email: mahdikhaksari36@gmail.com
