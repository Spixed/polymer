---
title: "My Terminal Setup Guide"
date: 2024-01-20
author: alex
featured: false
categories:
  - Tools
tags:
  - Terminal
  - Productivity
---

A well-configured terminal is a developer's best friend. Here's my setup.

## Shell: Zsh + Oh My Zsh

First, install zsh:

```bash
brew install zsh
chsh -s $(which zsh)
```

Then install Oh My Zsh:

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Essential Plugins

My must-have plugins:

- **zsh-autosuggestions** - Fish-like suggestions
- **zsh-syntax-highlighting** - Command highlighting
- **fzf** - Fuzzy finder integration

## Theme: Starship

[Starship](https://starship.rs/) is a minimal, blazing-fast prompt.

```toml
# ~/.config/starship.toml
[character]
success_symbol = "[➜](bold green)"
error_symbol = "[✗](bold red)"

[directory]
truncation_length = 3
```

### Keybindings Cheatsheet

| Shortcut | Action |
|----------|--------|
| `Ctrl+R` | Fuzzy history search |
| `Ctrl+T` | Fuzzy file finder |
| `Alt+C` | Fuzzy cd |

> A good terminal setup should feel like an extension of your thoughts.

---

*Invest in your tools—you'll use them every day.*
