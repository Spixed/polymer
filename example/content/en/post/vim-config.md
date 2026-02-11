---
title: "Vim Configuration for Minimalists"
date: 2024-01-10
author: sarah
featured: false
categories:
  - Tools
tags:
  - Vim
  - Editor
---

Vim doesn't need hundreds of plugins. Here's my minimal setup.

## Base Configuration

My entire `~/.vimrc`:

```vim
" Essential settings
set nocompatible
set number relativenumber
set expandtab tabstop=4 shiftwidth=4
set autoindent smartindent
set hlsearch incsearch ignorecase smartcase

" Appearance
syntax on
set background=dark
colorscheme desert
set cursorline

" Keybindings
let mapleader = " "
nnoremap <leader>w :w<CR>
nnoremap <leader>q :q<CR>
nnoremap <C-h> <C-w>h
nnoremap <C-l> <C-w>l
```

That's it. **48 lines**.

## Navigation Essentials

| Key | Action |
|-----|--------|
| `gg` | Go to start |
| `G` | Go to end |
| `0` | Line start |
| `$` | Line end |
| `w` | Next word |
| `b` | Previous word |
| `%` | Matching bracket |

### Text Objects

The real power:

- `ciw` - Change inner word
- `ci"` - Change inside quotes
- `da(` - Delete around parentheses
- `yi{` - Yank inside braces

## Philosophy

1. Learn the defaults first
2. Add plugins only when needed
3. Muscle memory beats mouse

> The best config is the one you understand completely.

---

*Less is more. Especially in Vim.*
