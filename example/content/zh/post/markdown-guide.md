---
title: "Markdown 语法指南"
date: 2024-02-15T12:00:00+08:00
draft: false
author: "alex"
featured: true
categories: ["指南"]
tags: ["Markdown", "文档"]
description: "Polymer 主题支持的 Markdown 语法完整指南。"
---

本文提供了可以在 Hugo 内容文件中使用的基本 Markdown 语法示例，展示了各种 HTML 元素在 Polymer 主题中的样式表现。

## 标题

以下 HTML `<h1>`—`<h6>` 元素代表六个级别的章节标题。`<h1>` 是最高级别，而 `<h6>` 是最低级别。

# H1 一级标题
## H2 二级标题
### H3 三级标题
#### H4 四级标题
##### H5 五级标题
###### H6 六级标题

## 段落

这是一个标准段落。Xerum, quo qui autunt expliquam qui dolut labo. Aque venitatiusda cum, voluptionse latur sitiae dolessi aut parist aut dollo enim qui voluptate ma dolestendit peritin re plis aut quas inctum laceat est volestemque commosa as cus endigna tectur.

## 引用块

引用块元素代表引自其他来源的内容。

> "我梦见画，然后画下了梦。"
>
> — 文森特·梵高

## 表格

表格不是核心 Markdown 规范的一部分，但 Hugo 原生支持它们。

| 姓名 | 年龄 |
| :--- | :-- |
| 张三 | 27  |
| 李四 | 23  |

## 代码块

### 使用反引号的代码块

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <title>HTML5 示例文档</title>
</head>
<body>
  <p>测试</p>
</body>
</html>
```

## 列表类型

### 有序列表

1. 第一项
2. 第二项
3. 第三项

### 无序列表

* 列表项
* 另一项
* 再一项

### 嵌套列表

* 项目
  1. 第一子项
  2. 第二子项

## 其他元素

abbr
: 缩写

sub
: H<sub>2</sub>O

sup
: X<sup>2</sup>
