---
layout: default
title: Pytorch Basics
parent: Pytorch
nav_order: 2
---

# Pytorch Basics
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## In pytorch we deal with tensors

```python
x = torch.empty(3) # 1D tensor
x = torch.empty(3,2) # 2D tensor
```

## To create tensor with random values

```python
x = torch.rand(3,2) # random elements of size 3,2
x = torch.zeros(3,2) # for zeros
x = torch.ones(3,2) # for ones.
```

## We can check the datatype and set datatype
 
```python
print(x.dtype) # by default it is float32.

x = torch.ones(3,2,dtype = torch.int) # --> int32.
x = torch.ones(3,2,dtype = torch.double) # --> double
x = torch.ones(3,2,dtype = torch.float16) # --> float 16 bits
```

## To check the size

```python
print(x.size())
```

## To add values

```python
x = torch.tensor([2.5, 0.1]) 
y = torch.tensor([4.5, 3.1]) 
z = x + y
# or
z = torch.add(x,y)
```

## Inplace addtion

```python
y.add_(x) # every function that has trailing _ (underscore) will do inplace operation.
similarly mul,sub,div
```

## Slicing operation

```python
print(x[:, 1]) # all rows, column 1st (indexing from zero)
```

## Reshaping the tensor

```python
x = torch.rand(4,4)
y = x.view(16) # converts it into 1D tensor. 1x16
y = x.view(-1,8) # converts it into 1D tensor. 2x8 ; pytorch automatically determines the size of -1 index.
```

## Changing types from tensor to numpy and vice versa

```python
a = torch.ones(5)
b = a.numpy() # both a and b are pointing to the same location.

a.add_(1) # this also changes b.

c = torch.from_numpy(b) # from numpy to tensor
```

## GPU if available

```python
# Here addition takes place on GPU but result is moved back to CPU
if torch.cuda.is_available("cuda"):
    device = torch.device("cuda")
    x = torch.ones(5, device = device)
    y = y.to(device)
    z = x + y
    z = z.to("cpu")
```

## Requires_grad - requires gradient to be calculated (default is false)

```python
x = torch.ones(5, requires_grad = True)
```
