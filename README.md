# 🔐 LDAP Authentication with Ansible (PAM)

![Ansible](https://img.shields.io/badge/Ansible-Automation-EE0000?logo=ansible&logoColor=white)
![LDAP](https://img.shields.io/badge/LDAP-Authentication-4B8BBE?logo=ldap&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-PAM-yellow?logo=linux&logoColor=black)
![Status](https://img.shields.io/badge/Status-Active-success)

---

## 📖 Overview

- This Ansible collection configures Linux servers to authenticate users against **LDAP** using **PAM** (Pluggable Authentication Modules).
- The collection enables centralized identity management by allowing system access via LDAP users and groups.
- Collection name:

---

## ✨ Features

- 🔐 LDAP authentication via PAM
- 👥 Centralized user access control
- 🧩 NSS + PAM integration
- 🔁 Idempotent Ansible roles
- 🛠 Works on systemd-based Linux distributions

---

## 🧠 How It Works

1. Installs required LDAP & PAM packages
2. Configures NSS to resolve LDAP users
3. Configures PAM for system authentication
4. Enables secure login via LDAP credentials
5. Grants access based on LDAP directory policies

---

## 🌐 DNS Requirement (Important)

⚠️ **DNS must be configured correctly before execution**<br>
All hosts **must resolve LDAP and domain records properly**.<br>

## Ensure the following DNS zone exists and is resolvable:
- Make sure records are added on
- Failure to configure DNS will result in authentication failures.

---

## ▶️ Execution
**`Enroll a server into LDAP authentication via PAM:`**

```bash
ansible-playbook -i inventory.ini main.yml -t install
````

```bash
[ldap_servers]
ldap01 ansible_host=192.168.8.10

[ldap_clients]
server01 ansible_host=192.168.8.50
server02 ansible_host=192.168.8.51
```


## 📦 Collection Information
| Key | Value |
|-----|-------|
| **Collection Name** | `lxhome.security.ldap` |
| **Purpose** | LDAP authentication via PAM |
| **Authentication Stack** | PAM + NSS |
| **Target OS** | Linux (systemd-based) |
| **Execution Method** | Ansible Playbook |
| **DNS Domain Required** | `lxhome.local` |


## 🔒 Security Notes
- Root access remains local
- LDAP is used for user authentication only
- SSH access is controlled via PAM policies
- TLS should be enabled for LDAP in production

## 📌 Requirements
- Ansible ≥ 2.14
- Working LDAP server
- Correct DNS configuration
- Network access to LDAP (TCP 389 / 636)

## 📜 License
- Licensed under the Apache License 2.0.
- See the **`LICENSE`** file for details.

## 🤝 Contributing
Issues and pull requests are welcome.

## ⭐ Acknowledgements
- OpenLDAP
- Linux PAM
- Red Hat