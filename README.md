# Ansible LAMP (Fedora target)

Provision a LAMP stack (Apache + PHP + MariaDB) on **Fedora** using Ansible.

Features:
- `firewalld` configured (SSH/HTTP/HTTPS)
- Apache (`httpd`) installed and enabled
- PHP + MySQL extension
- MariaDB installed and started, with smart handling of root auth (socket/password) and app DB/user creation
- SELinux boolean to allow Apache → DB connections

> Control node: Ubuntu (your laptop).  
> Target node: Fedora (e.g., `192.168.178.131`).

---

## Requirements

- Ansible 2.14+ on the control node
- SSH access to the Fedora server (user `liveuser`, SSH key)
- Collections:
  ```bash
  ansible-galaxy collection install community.mysql ansible.posix
