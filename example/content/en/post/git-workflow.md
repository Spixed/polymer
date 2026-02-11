---
title: Git Workflow Best Practices
date: 2024-01-15
draft: false
author: alex
featured: false
categories: [Development]
tags: [Git, Workflow]
description: ''
---


Git is powerful, but without good practices, it can become chaotic. Here's my approach.

## Branching Strategy

I use a simplified Git Flow:

```
main ←── develop ←── feature/xyz
                 ←── fix/abc
```

### Naming Conventions

- `feature/*` - New features
- `fix/*` - Bug fixes
- `chore/*` - Maintenance tasks
- `docs/*` - Documentation updates

## Commit Messages

Follow the **Conventional Commits** specification:

```
<type>(<scope>): <subject>

<body>

<footer>
```

Example:

```
feat(auth): add OAuth2 login support

Implemented Google and GitHub OAuth providers.
Uses passport.js for strategy management.

Closes #123
```

### Types Reference

| Type | Description |
|------|-------------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation |
| `style` | Formatting |
| `refactor` | Code restructuring |
| `test` | Adding tests |
| `chore` | Maintenance |

## Pre-commit Hooks

Always run checks before committing:

```bash
# .pre-commit-config.yaml
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
```

> A clean git history tells a story. Make yours readable.

---

*Your future self will thank you for good commit messages.*
