---
title: "密码学基础"
date: 2024-02-03
author: sarah
featured: true
categories:
  - 安全
tags:
  - 密码学
  - 数学
math: true
---

在数字通信的世界里，密码学是必不可少的。让我们探索基础知识。

## 对称加密

双方共享一个{{< hl blue >}}密钥{{< /hl >}}：

```
明文 → [用密钥加密] → 密文 → [用密钥解密] → 明文
```

### AES 示例

```python
from Crypto.Cipher import AES
from Crypto.Random import get_random_bytes

key = get_random_bytes(16)  # 128位密钥
cipher = AES.new(key, AES.MODE_GCM)

ciphertext, tag = cipher.encrypt_and_digest(b"秘密消息")
```

## 非对称加密

使用**密钥对**：公钥和私钥。

$$
\text{加密}(m, K_{pub}) = c
$$

$$
\text{解密}(c, K_{priv}) = m
$$

### RSA 密钥生成

安全性依赖于因式分解的困难性：

$$
n = p \times q
$$

其中 $p$ 和 $q$ 是大素数。

| 密钥长度 | 安全级别 |
|---------|---------|
| 1024位 | 遗留（弱） |
| 2048位 | 标准 |
| 4096位 | 高安全性 |

## 哈希函数

密码学哈希的特性：

1. **确定性**：相同输入 → 相同输出
2. **单向性**：无法逆向
3. **抗碰撞**：难以找到重复

```bash
echo "hello" | sha256sum
# 5891b5b522d5df086d0ff0b110fbd9d21bb4fc7163af34d08286a2e846f6be03
```

> 永远不要自己造密码学轮子。使用成熟的库。

---

*安全性只有最薄弱环节那么强。*
