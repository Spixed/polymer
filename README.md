# Polymer - A Vibrant, Funky Hugo Theme

Polymer is a modern, high-contrast Hugo theme inspired by pop art and "Neo-Brutalism". It features vibrant colors, dynamic "ink-blob" morphing effects, and a highly interactive, responsive grid system.

## ✨ Features

- **Dynamic Grid Layout**: Homepage articles are randomized in size and color on every load.
- **Hero Carousel**: Featured articles are beautifully showcased in a morphing hero section.
- **Qmoji Support**: Built-in support for QQ-style emojis (static, APNG, Lottie) via shortcodes.
- **Author Profiles**: Interactive author filtering and profile cards with multi-language bios.
- **Taxonomy Filtering**: Category and Tag pages with instant AJAX-like filtering.
- **Adaptive Drop Caps**: First-letter styling that automatically scales based on text density.
- **Modern Typography**: High-impact fonts including Space Grotesk and Maple Mono.
- **Dark Mode**: Seamless transition between light and dark themes.
- **Math Support**: Built-in MathJax support for equations.
- **Waline Comments**: Integrated Waline comment system.

## 🚀 Installation

### 1. Requirements
Ensure you have Hugo installed (Extended version recommended for SCSS/Minification).

### 2. Add Theme
```bash
git submodule add https://github.com/spixed/polymer themes/polymer
```

### 3. Configuration
Update your `hugo.toml` with the following configuration. This theme requires specific language and parameter settings.

```toml
baseURL = "https://your-site.com/"
title = "My Blog"
theme = "polymer"
defaultContentLanguage = "en"
hasCJKLanguage = true
enableEmoji = true

[params]
  description = "A Digital Brutalism Theme"
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
  [languages.en]
    languageName = 'English'
    contentDir = 'content/en'
    weight = 1
    languageCode = "en-US"
  
  [languages.zh]
    languageName = '简体中文'
    contentDir = 'content/zh'
    weight = 2
    languageCode = "zh-CN"

[menu]
  [[menu.main]]
    identifier = "home"
    name = "Home"
    url = "/"
    weight = 1
  [[menu.main]]
    identifier = "archives"
    name = "Archives"
    url = "/archives/"
    weight = 10
  [[menu.main]]
    identifier = "links"
    name = "Links"
    url = "/links/"
    weight = 20

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

## 📝 Content Management

### Directory Structure
Polymer uses a multilingual directory structure:

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

### Front Matter
Here is a complete example of the Front Matter for a post:

```yaml
---
title: "The Art of Brutalism"
date: 2024-02-15T12:00:00+08:00
draft: false
author: "alex"        # Must match ID in data/authors.toml
featured: true        # Set to true to show in the Hero Carousel
categories: ["Design"]
tags: ["Art", "Web"]
description: "An exploration of raw digital aesthetics."
---
```

### Authors Configuration
Create or edit `data/authors.toml` to define your authors. The `author` field in Front Matter corresponds to the TOML key here (e.g., `[alex]`).

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

## 😄 Qmoji Support

Polymer includes a unique Qmoji system (QQ-style emojis) powered by [QFace](https://koishi.js.org/QFace/#/qqnt) and [Spixed/Qmoji](https://github.com/Spixed/Qmoji).

### Usage
Use the shortcode in your Markdown:

```markdown
{{< qq-emoji "微笑" >}}
{{< qq-emoji "大哭" "block">}}
```

(Note: The "block" parameter is optional(default is inline). It will display the emoji as a block element if set to "block". And the Qmoji name must be in Chinese or slash command style.)

### Supported Names
You can use the Chinese name (e.g., "微笑") or the slash command style (e.g., "/微笑").
For a full list of supported names and IDs, please refer to the [Koishi QFace Documentation](https://koishi.js.org/QFace/#/qqnt).

## 📄 License
MIT
