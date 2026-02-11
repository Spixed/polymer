---
title: 从零开始理解神经网络
date: 2024-02-05
draft: false
author: sarah
featured: true
categories: [AI]
tags: [机器学习, Python]
description: ''
---


理解神经网络需要从头构建一个。让我们深入探索。

## 感知机

最简单的神经网络是单个感知机：

$$
y = \sigma\left(\sum_{i=1}^{n} w_i x_i + b\right)
$$

其中 $\sigma$ 是激活函数（通常是 sigmoid 或 ReLU）。

### Python 实现

```python
import numpy as np

class Perceptron:
    def __init__(self, n_inputs):
        self.weights = np.random.randn(n_inputs)
        self.bias = 0.0
    
    def forward(self, x):
        z = np.dot(self.weights, x) + self.bias
        return self.sigmoid(z)
    
    def sigmoid(self, z):
        return 1 / (1 + np.exp(-z))
```

## 多层网络

完整的网络堆叠多个层：

1. **输入层**：原始数据
2. **隐藏层**：特征提取
3. **输出层**：预测

### 反向传播

链式法则使梯度计算成为可能：

$$
\frac{\partial L}{\partial w} = \frac{\partial L}{\partial a} \cdot \frac{\partial a}{\partial z} \cdot \frac{\partial z}{\partial w}
$$

这是{{< hl green >}}深度学习的核心{{< /hl >}}。

## 训练清单

- [x] 初始化权重
- [x] 前向传播
- [x] 计算损失
- [ ] 反向传播
- [ ] 更新权重

> 真正理解神经网络的唯一方法是亲自实现它们。

---

*从简单开始。复杂性自然会产生。*
