---
title: "Linux 服务器加固指南"
date: 2024-01-25
author: sarah
featured: false
categories:
  - 安全
tags:
  - Linux
  - 运维
---

一个全新的 Linux 服务器是脆弱的。这是如何加固它。

## SSH 配置

编辑 `/etc/ssh/sshd_config`：

```bash
# 禁用密码认证
PasswordAuthentication no
PubkeyAuthentication yes

# 禁用 root 登录
PermitRootLogin no

# 更改默认端口
Port 2222
```

更改后：

```bash
sudo systemctl restart sshd
```

### SSH 密钥设置

生成强密钥：

```bash
ssh-keygen -t ed25519 -C "your@email.com"
```

## 使用 UFW 防火墙

```bash
# 安装并启用
sudo apt install ufw
sudo ufw enable

# 默认策略
sudo ufw default deny incoming
sudo ufw default allow outgoing

# 允许 SSH
sudo ufw allow 2222/tcp
```

### 快速参考

| 服务 | 端口 | 操作 |
|-----|------|-----|
| SSH | 2222 | 允许 |
| HTTP | 80 | 允许 |
| HTTPS | 443 | 允许 |

## 自动更新

安装 unattended-upgrades：

```bash
sudo apt install unattended-upgrades
sudo dpkg-reconfigure unattended-upgrades
```

> 安全是一个过程，不是一个产品。

---

*加固的服务器是快乐的服务器。*
