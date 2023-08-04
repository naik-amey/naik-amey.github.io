---
layout: default
title: Pytorch
nav_order: 1
has_children: true
permalink: docs/pytorch
---

# Pytorch Installation

{: .no_toc }

My pytorch notes.
{: .fs-6 .fw-300 }

## Steps to install pytorch on mac M1 silicon

```bash
  curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh\nsh Miniconda3-latest-MacOSX-arm64.sh
  sh Miniconda3-latest-MacOSX-arm64.sh -u
  conda create --name pytorch_m1 python=3.8
  conda activate pytorch_m1 
```

## Follow these steps to avoid numpy error while importing torch

```bash
  conda clean --all
  conda install openblas
  conda uninstall numpy
  conda install numpy
  conda install pytorch torchvision -c pytorch
```

## Calc gradients we need to set requires_grad

```
x = torch.randn(3, requires_grad =True)
```

## To calc gradient for x. It creates a computational graph.

For, `y = x + 2.`

1. The graph looks like this,
```
x ---\
      |+| ---> y
2 ---/
```

2. In the forward pass we calculate output y.

dy/dx in backward prop (add backward function)
y output looks like

tensor([1.1,2.3,5.0],  grad_fn = <AddBackward0>)

similarly we will have grad_fn = <MulBackward0>)

So now to calculate gradient
y.backward() # dy/dz
print(x.grad) # print gradients.

# more - https://youtu.be/c36lUUr864M?t=1876

backprop:

x --->a(x) --> y ---> b(y) --> z

dz/dx = dz/dy * dy/dx

Computational graph:

1. Forward Pass - Compute loss
2. Compute local gradients
3. Backward Pass: compute dLoss/dWeights using the chain rule.

Copy images from here :
    https://youtu.be/c36lUUr864M?t=2942
Example:
    https://youtu.be/c36lUUr864M?t=3291
