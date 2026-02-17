# Polymer - 一个充满活力与律动的 Hugo 主题

Polymer 是一个受波普艺术和“新粗野主义”启发的现代高对比度 Hugo 主题。它具有鲜艳的色彩、动态的“墨滴”变形效果以及高度交互的响应式网格系统。

## ✨ 特性

- **动态网格布局**：首页文章在每次加载时随机调整大小和颜色。
- **Hero 轮播图**：精选文章在变形的 Hero 区域中美观展示。
- **Qmoji 支持**：通过短代码内置支持 QQ 风格表情（静态、APNG、Lottie）。
- **作者资料**：交互式作者筛选和包含多语言简介的资料卡片。
- **分类筛选**：支持即时 AJAX 风格筛选的分类和标签页面。
- **自适应首字下沉**：根据文本密度自动缩放的首字样式。
- **现代排版**：包含 Space Grotesk 和 Maple Mono 等高冲击力字体。
- **暗黑模式**：无缝切换明暗主题。
- **数学公式支持**：内置 MathJax 支持。
- **Waline 评论**：集成 Waline 评论系统。

## 🚀 安装

### 1. 环境要求
确保您已安装 Hugo（建议使用 Extended 版本以支持 SCSS/Minification）。

### 2. 添加主题
```bash
git submodule add https://github.com/spixed/polymer themes/polymer
```

### 3. 配置
更新您的 `hugo.toml` 配置文件。此主题需要特定的语言和参数设置。

```toml
baseURL = "https://your-site.com/"
title = "我的博客"
theme = "polymer"
defaultContentLanguage = "zh"
hasCJKLanguage = true
enableEmoji = true

[params]
  description = "一个数字粗野主义主题"
  math = true
  mathEngine = "mathjax"
  favicon = "/logo.png"

  [params.waline]
    enable = true
    serverURL = "https://your-waline-server.vercel.app/"

[taxonomies]
  category = "categories"
  tag = "tags"

[languages]
  [languages.zh]
    languageName = '简体中文'
    contentDir = 'content/zh'
    weight = 1
    languageCode = "zh-CN"
  
  [languages.en]
    languageName = 'English'
    contentDir = 'content/en'
    weight = 2
    languageCode = "en-US"

[markup]
  [markup.goldmark]
    [markup.goldmark.renderer]
      unsafe = true
    [markup.goldmark.extensions]
      [markup.goldmark.extensions.passthrough]
        enable = true
        [markup.goldmark.extensions.passthrough.delimiters]
          block = [['$$', '$$'], ['\\[', '\\]']]
          inline = [['$', '$'], ['\\(', '\\)']]
```

## 📝 内容管理

### 目录结构
Polymer 使用多语言目录结构：

```text
content/
├── en/
│   ├── post/
│   │   └── my-first-post.md
│   ├── about.md
│   └── archives.md
└── zh/
    ├── post/
    │   └── my-first-post.md
    ├── about.md
    └── archives.md
```

### Front Matter (文章头信息)
以下是文章 Front Matter 的完整示例：

```yaml
---
title: "粗野主义的艺术"
date: 2024-02-15T12:00:00+08:00
draft: false
author: "alex"        # 必须与 data/authors.toml 中的 ID 匹配
featured: true        # 设置为 true 以在 Hero 轮播图中展示
categories: ["设计"]
tags: ["艺术", "Web"]
description: "探索原始的数字美学。"
---
```

### 作者配置
创建或编辑 `data/authors.toml` 来定义作者。Front Matter 中的 `author` 字段对应此处的 TOML 键（例如 `[alex]`）。

```toml
[alex]
    name = "Alex Bold"
    nickname = "Alex"
    avatar = "/images/alex.jpg"
    bio = { en = "A digital explorer.", zh = "数字探索者。" }
    github = "https://github.com/alex"
    website = "https://alex.com"
    email = "alex@example.com"
    weight = 1
```

## 😄 Qmoji 支持

Polymer 内置了独特的 Qmoji 系统（QQ 风格表情），由 [QFace](https://koishi.js.org/QFace/#/qqnt) 和 [Spixed/Qmoji](https://github.com/Spixed/Qmoji) 提供支持。

### 用法
在 Markdown 中使用短代码：

```markdown
{{< qq-emoji "微笑" >}}
{{< qq-emoji "大哭" "block">}}
```

### 支持的名称
您可以使用中文名称（如 "微笑"）或斜杠命令风格（如 "/微笑"）。
获取完整的支持名称和 ID 列表，请参考 [Koishi QFace 文档](https://koishi.js.org/QFace/#/qqnt)。

## 📄 许可证
MIT
