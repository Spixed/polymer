---
title: "Neural Networks From Scratch"
date: 2024-02-05
author: sarah
featured: true
categories:
  - AI
tags:
  - Machine Learning
  - Python
math: true
---

Understanding neural networks requires building one from the ground up. Let's dive in.

## The Perceptron

The simplest neural network is a single perceptron:

$$
y = \sigma\left(\sum_{i=1}^{n} w_i x_i + b\right)
$$

Where $\sigma$ is the activation function (often sigmoid or ReLU).

### Python Implementation

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

## Multi-Layer Networks

A full network stacks multiple layers:

1. **Input Layer**: Raw data
2. **Hidden Layers**: Feature extraction
3. **Output Layer**: Predictions

### Backpropagation

The chain rule enables gradient computation:

$$
\frac{\partial L}{\partial w} = \frac{\partial L}{\partial a} \cdot \frac{\partial a}{\partial z} \cdot \frac{\partial z}{\partial w}
$$

This is the {{< hl green >}}heart of deep learning{{< /hl >}}.

## Training Checklist

- [x] Initialize weights
- [x] Forward pass
- [x] Compute loss
- [ ] Backward pass
- [ ] Update weights

> The only way to truly understand neural networks is to implement them yourself.

---

*Start simple. Complexity comes naturally.*
