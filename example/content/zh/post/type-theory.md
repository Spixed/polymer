---
title: 类型理论入门
date: 2024-01-28
draft: false
author: alex
featured: true
categories: [编程]
tags: [类型, 理论]
description: ''
---


类型系统不仅仅是捕获错误——它们是编译器可以验证的文档形式。

## 为什么类型很重要

考虑这个简单的函数：

```javascript
function add(a, b) {
    return a + b;
}
```

没有类型，`add("hello", "world")` 完全有效。有了类型：

```typescript
function add(a: number, b: number): number {
    return a + b;
}
```

现在编译器在{{< hl blue >}}运行前{{< /hl >}}就能捕获错误。

### Curry-Howard 对应

类型和逻辑之间有深刻的联系：

| 类型理论 | 逻辑 |
|---------|------|
| 类型 | 命题 |
| 值 | 证明 |
| 函数 | 蕴涵 |
| 积类型 | 合取 (AND) |
| 和类型 | 析取 (OR) |

这种联系表示为：

$$
\Gamma \vdash e : \tau \iff \Gamma \vdash \mathcal{P}
$$

其中 $e$ 是类型 $\tau$ 的项，$\mathcal{P}$ 是对应的命题。

## 实际应用

1. **验证**：类型作为契约
2. **重构**：安全的代码更改
3. **文档**：自文档化的 API

> 类型不是限制——它们是让你保持在正轨上的**护栏**。

---

*目标不是让类型系统满意，而是清晰地表达你的意图。*
