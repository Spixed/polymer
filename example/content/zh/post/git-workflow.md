---
title: Git 工作流最佳实践
date: 2024-01-15
draft: false
author: alex
featured: false
categories: [开发]
tags: [Git, 工作流]
description: ''
---


Git 功能强大，但如果没有好的实践，它可能会变得混乱。这是我的方法。

## 分支策略

我使用简化版的 Git Flow：

```
main ←── develop ←── feature/xyz
                 ←── fix/abc
```

### 命名约定

- `feature/*` - 新功能
- `fix/*` - Bug 修复
- `chore/*` - 维护任务
- `docs/*` - 文档更新

## 提交信息

遵循 **Conventional Commits** 规范：

```
<type>(<scope>): <subject>

<body>

<footer>
```

示例：

```
feat(auth): 添加 OAuth2 登录支持

实现了 Google 和 GitHub OAuth 提供商。
使用 passport.js 进行策略管理。

Closes #123
```

### 类型参考

| 类型 | 描述 |
|------|-----|
| `feat` | 新功能 |
| `fix` | Bug 修复 |
| `docs` | 文档 |
| `style` | 格式化 |
| `refactor` | 代码重构 |
| `test` | 添加测试 |
| `chore` | 维护 |

## Pre-commit Hooks

提交前始终运行检查：

```bash
# .pre-commit-config.yaml
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
```

> 清晰的 git 历史讲述一个故事。让你的可读。

---

*你未来的自己会感谢好的提交信息。*
