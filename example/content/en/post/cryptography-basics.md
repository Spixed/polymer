---
title: "Cryptography Fundamentals"
date: 2024-02-03
author: sarah
featured: true
categories:
  - Security
tags:
  - Cryptography
  - Math
math: true
---

In a world of digital communication, cryptography is essential. Let's explore the basics.

## Symmetric Encryption

Both parties share a {{< hl blue >}}secret key{{< /hl >}}:

```
plaintext → [encrypt with key] → ciphertext → [decrypt with key] → plaintext
```

### AES Example

```python
from Crypto.Cipher import AES
from Crypto.Random import get_random_bytes

key = get_random_bytes(16)  # 128-bit key
cipher = AES.new(key, AES.MODE_GCM)

ciphertext, tag = cipher.encrypt_and_digest(b"Secret message")
```

## Asymmetric Encryption

Uses a **key pair**: public and private.

$$
\text{Encrypt}(m, K_{pub}) = c
$$

$$
\text{Decrypt}(c, K_{priv}) = m
$$

### RSA Key Generation

The security relies on the difficulty of factoring:

$$
n = p \times q
$$

Where $p$ and $q$ are large primes.

| Key Length | Security Level |
|------------|----------------|
| 1024-bit | Legacy (weak) |
| 2048-bit | Standard |
| 4096-bit | High security |

## Hash Functions

Properties of cryptographic hashes:

1. **Deterministic**: Same input → same output
2. **One-way**: Cannot reverse
3. **Collision-resistant**: Hard to find duplicates

```bash
echo "hello" | sha256sum
# 5891b5b522d5df086d0ff0b110fbd9d21bb4fc7163af34d08286a2e846f6be03
```

> Never roll your own crypto. Use established libraries.

---

*Security is only as strong as its weakest link.*
