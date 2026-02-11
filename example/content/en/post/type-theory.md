---
title: "Introduction to Type Theory"
date: 2024-01-28
author: alex
featured: true
categories:
  - Programming
tags:
  - Types
  - Theory
math: true
---

Type systems are more than just error catching—they're a form of documentation that the compiler can verify.

## Why Types Matter

Consider this simple function:

```javascript
function add(a, b) {
    return a + b;
}
```

Without types, `add("hello", "world")` is perfectly valid. With types:

```typescript
function add(a: number, b: number): number {
    return a + b;
}
```

Now the compiler catches mistakes {{< hl blue >}}before runtime{{< /hl >}}.

### The Curry-Howard Correspondence

There's a deep connection between types and logic:

| Type Theory | Logic |
|-------------|-------|
| Type | Proposition |
| Value | Proof |
| Function | Implication |
| Product Type | Conjunction (AND) |
| Sum Type | Disjunction (OR) |

This connection is expressed as:

$$
\Gamma \vdash e : \tau \iff \Gamma \vdash \mathcal{P}
$$

Where $e$ is a term of type $\tau$, and $\mathcal{P}$ is the corresponding proposition.

## Practical Applications

1. **Validation**: Types as contracts
2. **Refactoring**: Safe code changes
3. **Documentation**: Self-documenting APIs

> Types are not restrictions—they are **guardrails** that keep you on the road.

---

*The goal is not to make the type system happy, but to express your intent clearly.*
