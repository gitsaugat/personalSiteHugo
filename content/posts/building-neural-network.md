---
title: How to build and train a simple Neural Network using pytorch
description: A beginner's guide to creating neural networks with PyTorch
date: 2025-11-16T02:15:00.000-05:00
draft: false
---

# PyTorch

PyTorch is a famous tool to build neural networks which can be used with Python
.


## Installation 

First, install PyTorch using pip:

```bash
pip install torch torchvision
```

## Building a Simple Neural Network

### Step 1: Import Required Libraries

```python
import torch
import torch.nn as nn
import torch.optim as optim
```

### Step 2: Define the Network Architecture

```python
class SimpleNN(nn.Module):
    def __init__(self, input_size, hidden_size, output_size):
        super(SimpleNN, self).__init__()
        self.layer1 = nn.Linear(input_size, hidden_size)
        self.relu = nn.ReLU()
        self.layer2 = nn.Linear(hidden_size, output_size)
    
    def forward(self, x):
        x = self.layer1(x)
        x = self.relu(x)
        x = self.layer2(x)
        return x
```

### Step 3: Initialize the Model

```python
# Define dimensions
input_size = 10
hidden_size = 20
output_size = 2

# Create model instance
model = SimpleNN(input_size, hidden_size, output_size)
```

### Step 4: Define Loss Function and Optimizer

```python
criterion = nn.CrossEntropyLoss()
optimizer = optim.Adam(model.parameters(), lr=0.001)
```

### Step 5: Training Loop

```python
# Example training loop
for epoch in range(100):
    # Forward pass
    outputs = model(train_data)
    loss = criterion(outputs, train_labels)
    
    # Backward pass and optimization
    optimizer.zero_grad()
    loss.backward()
    optimizer.step()
    
    if (epoch + 1) % 10 == 0:
        print(f'Epoch [{epoch+1}/100], Loss: {loss.item():.4f}')
```

## Key Concepts

- **nn.Module**: Base class for all neural network modules
- **Forward pass**: Defines how data flows through the network
- **Loss function**: Measures how well the model performs
- **Optimizer**: Updates the model weights to minimize loss
- **Backpropagation**: Automatic gradient computation using `.backward()`

## Conclusion

PyTorch makes it easy to build and train neural networks with its intuitive API and automatic differentiation capabilities. This simple example demonstrates the core workflow that can be extended to more complex architectures.

.....