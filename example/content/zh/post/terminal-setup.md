---
title: 我的终端配置指南
date: 2024-01-20
draft: false
author: alex
featured: false
categories: [工具]
tags: [终端, 效率]
description: ''
---


一个配置良好的终端是开发者的好伙伴。这是我的设置。

## Shell: Zsh + Oh My Zsh

首先，安装 zsh：

```bash
brew install zsh
chsh -s $(which zsh)
```

然后安装 Oh My Zsh：

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### 必备插件

我的必备插件：

- **zsh-autosuggestions** - 类 Fish 的建议
- **zsh-syntax-highlighting** - 命令高亮
- **fzf** - 模糊搜索集成

## 主题: Starship

[Starship](https://starship.rs/) 是一个极简、超快的提示符。

```toml
# ~/.config/starship.toml
[character]
success_symbol = "[➜](bold green)"
error_symbol = "[✗](bold red)"

[directory]
truncation_length = 3
```

### 快捷键速查

| 快捷键 | 操作 |
|-------|------|
| `Ctrl+R` | 模糊历史搜索 |
| `Ctrl+T` | 模糊文件查找 |
| `Alt+C` | 模糊 cd |

> 好的终端配置应该像是你思维的延伸。

---

*投资你的工具——你每天都会用到它们。*
