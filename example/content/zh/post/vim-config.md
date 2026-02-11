---
title: "极简主义者的 Vim 配置"
date: 2024-01-10
author: sarah
featured: false
categories:
  - 工具
tags:
  - Vim
  - 编辑器
---

Vim 不需要数百个插件。这是我的极简设置。

## 基础配置

我的整个 `~/.vimrc`：

```vim
" 基本设置
set nocompatible
set number relativenumber
set expandtab tabstop=4 shiftwidth=4
set autoindent smartindent
set hlsearch incsearch ignorecase smartcase

" 外观
syntax on
set background=dark
colorscheme desert
set cursorline

" 快捷键
let mapleader = " "
nnoremap <leader>w :w<CR>
nnoremap <leader>q :q<CR>
nnoremap <C-h> <C-w>h
nnoremap <C-l> <C-w>l
```

就这些。**48 行**。

## 导航要点

| 按键 | 操作 |
|-----|------|
| `gg` | 到开头 |
| `G` | 到结尾 |
| `0` | 行首 |
| `$` | 行尾 |
| `w` | 下一个词 |
| `b` | 上一个词 |
| `%` | 匹配括号 |

### 文本对象

真正的力量：

- `ciw` - 改变内部词
- `ci"` - 改变引号内
- `da(` - 删除包括括号
- `yi{` - 复制大括号内

## 哲学

1. 先学默认
2. 只在需要时添加插件
3. 肌肉记忆胜过鼠标

> 最好的配置是你完全理解的配置。

---

*少即是多。尤其是在 Vim 中。*
