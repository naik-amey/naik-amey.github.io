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

# Steps to install pytorch on mac M1 silicon

```bash
  curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh\nsh Miniconda3-latest-MacOSX-arm64.sh
  sh Miniconda3-latest-MacOSX-arm64.sh -u
  conda create --name pytorch_m1 python=3.8
  conda activate pytorch_m1 
```

## Follow these steps to avoid numpy error whule importing torch in python

```bash
  conda clean --all
  conda install openblas
  conda uninstall numpy
  conda install numpy
  conda install pytorch torchvision -c pytorch
```
