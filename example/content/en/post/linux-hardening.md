---
title: Linux Server Hardening Guide
date: 2024-01-25
draft: false
author: sarah
featured: false
categories: [Security]
tags: [Linux, Sysadmin]
description: ''
---


A fresh Linux server is vulnerable. Here's how to lock it down.

## SSH Configuration

Edit `/etc/ssh/sshd_config`:

```bash
# Disable password auth
PasswordAuthentication no
PubkeyAuthentication yes

# Disable root login
PermitRootLogin no

# Change default port
Port 2222
```

After changes:

```bash
sudo systemctl restart sshd
```

### SSH Keys Setup

Generate a strong key:

```bash
ssh-keygen -t ed25519 -C "your@email.com"
```

## Firewall with UFW

```bash
# Install and enable
sudo apt install ufw
sudo ufw enable

# Default policies
sudo ufw default deny incoming
sudo ufw default allow outgoing

# Allow SSH
sudo ufw allow 2222/tcp
```

### Quick Reference

| Service | Port | Action |
|---------|------|--------|
| SSH | 2222 | Allow |
| HTTP | 80 | Allow |
| HTTPS | 443 | Allow |

## Automatic Updates

Install unattended-upgrades:

```bash
sudo apt install unattended-upgrades
sudo dpkg-reconfigure unattended-upgrades
```

> Security is a process, not a product.

---

*A hardened server is a happy server.*
