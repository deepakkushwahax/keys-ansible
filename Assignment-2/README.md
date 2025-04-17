# Ansible Assignment-2

This project involves configuring a web environment using Ansible. It includes installing Nginx and Apache, setting up log rotation, rotating websites every 2 hours, and configuring Nginx as a reverse proxy.

---

## Steps to Execute

### STEP 1: Install Nginx + Configure Log Rotation

Install Nginx on target servers and configure log rotation to manage log file size and retention.

```bash
ANSIBLE_STRATEGY=linear ansible-playbook install_nginx.yml -l servers --forks 1
```

### STEP 2: Create Websites + 2-Hour Auto Switch

```basg
ANSIBLE_STRATEGY=free ansible-playbook website_rotation.yml -l servers --forks 1
```

### Configure Nginx as Reverse Proxy
```bash
ANSIBLE_STRATEGY=linear ansible-playbook configure_reverse_proxy.yml
```