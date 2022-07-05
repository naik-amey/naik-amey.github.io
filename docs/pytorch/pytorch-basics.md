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

## pytorch we deal with tensors

```python
x = torch.empty(3) # 1D tensor
x = torch.empty(3,2) # 2D tensor
```

## To create tensor with random values

```python
x = torch.rand(3,2)
x = torch.zeros(3,2) # for zeros
x = torch.ones(3,2) # for ones.
```

## We can check the datatype and set datatype
 
```python
print(x.dtype) # by default it is float32.

x = torch.ones(3,2,dtype = torch.int) # --> int32.
x = torch.ones(3,2,dtype = torch.double) # -->
x = torch.ones(3,2,dtype = torch.float16) # -->
```

## check the size

```python
print(x.size())
```

## add values

```python
x = torch.tensor([2.5, 0.1]) # we custom values.
y = torch.tensor([4.5, 3.1]) # we custom values.
z = x + y
or
z = torch.add(x,y)
```

## inplace addtion

```python
y.add_(x) # every function that has trailing _ (underscore) will do inplace operation.
similarly mul,sub,div
```

## slicing operation

```python
print(x[:, 1]) # all rows, column 1st (indexing from zero)
```

## reshaping the tensor

```python
x = torch.rand(4,4)
y = x.view(16) # converts it into 1D tensor. 1x16
y = x.view(-1,8) # converts it into 1D tensor. 2x8 ; pytorch automatically determines the size of -1 index.
```

## changing types from tensor to numpy and vice versa

```python
a = torch.ones(5)
b = a.numpy() # both a and b are pointing to the same location.

a.add_(1) # this also changes b.

c = torch.from_numpy(b) # from numpy to tensor
```

## to gpu if available

```python
if torch.cuda.is_available("cuda"):
    device = torch.device("cuda")
    x = torch.ones(5, device = device)
    y = y.to(device)
    z = x + y
    z = z.to("cpu")
```

## requires_grad - requires gradient to be calculated (default is false)

```python
x = torch.ones(5, requires_grad = True)
```

### Links that look like buttons

<div class="code-example" markdown="1">
[Link button](http://example.com/){: .btn }

[Link button](http://example.com/){: .btn .btn-purple }
[Link button](http://example.com/){: .btn .btn-blue }
[Link button](http://example.com/){: .btn .btn-green }

[Link button](http://example.com/){: .btn .btn-outline }
</div>
```markdown
[Link button](http://example.com/){: .btn }

[Link button](http://example.com/){: .btn .btn-purple }
[Link button](http://example.com/){: .btn .btn-blue }
[Link button](http://example.com/){: .btn .btn-green }

[Link button](http://example.com/){: .btn .btn-outline }
```

### Button element

GitHub Flavored Markdown does not support the `button` element, so you'll have to use inline HTML for this:

<div class="code-example">
<button type="button" name="button" class="btn">Button element</button>
</div>
```html
<button type="button" name="button" class="btn">Button element</button>
```

---

## Using utilities with buttons

### Button size

Wrap the button in a container that uses the [font-size utility classes]({{ site.baseurl }}{% link docs/utilities/typography.md %}) to scale buttons:

<div class="code-example" markdown="1">
<span class="fs-6">
[Big ass button](http://example.com/){: .btn }
</span>

<span class="fs-3">
[Tiny ass button](http://example.com/){: .btn }
</span>
</div>
```markdown
<span class="fs-8">
[Link button](http://example.com/){: .btn }
</span>

<span class="fs-3">
[Tiny ass button](http://example.com/){: .btn }
</span>
```

### Spacing between buttons

Use the [margin utility classes]({{ site.baseurl }}{% link docs/utilities/layout.md %}#spacing) to add spacing between two buttons in the same block.

<div class="code-example" markdown="1">
[Button with space](http://example.com/){: .btn .btn-purple .mr-2 }
[Button ](http://example.com/){: .btn .btn-blue .mr-2 }

[Button with more space](http://example.com/){: .btn .btn-green .mr-4 }
[Button ](http://example.com/){: .btn .btn-blue }
</div>
```markdown
[Button with space](http://example.com/){: .btn .btn-purple .mr-2 }
[Button ](http://example.com/){: .btn .btn-blue }

[Button with more space](http://example.com/){: .btn .btn-green .mr-4 }
[Button ](http://example.com/){: .btn .btn-blue }
```
