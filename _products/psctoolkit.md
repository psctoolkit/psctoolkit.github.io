---
title: PSCToolkit
subtitle: Parallel Sparse Computation Toolkit
description:
product_code: PSCTOOLKIT
layout: product
image: /img/psctoolkit.png
features:
    - label: PSBLAS: Parallel Sparse BLAS
      icon: fa-code
    - label: PSBLAS-EXT: GPU Plugin for Parallel Sparse BLAS
      icon: fa-puzzle-piece
    - label: AMG4PSBLAS: Preconditioners for PSBLAS
      icon: fa-tachometer-alt
    - label: Excellent innovation in the EU Innovation Radar
      icon: fa-star
order: 4
---

This is the complete set of libraries that goes under the name PSCToolkit. To have the latest aligned version you can use the [psctoolkit repository](https://github.com/psctoolkit/psctoolkit).
It contains the various libraries that make up the Parallel Sparse Computation Toolkit (PSCToolkit) as submodules.

- PSBLAS
- PSBLAS-EXT
- AMG4PSBLAS

Moreover, it contains a version of the SUNDIALS library interfacing the PSCToolkit routines for linear algebra (distributed matrices and vectors), linear solvers and preconditioners.

## How to get

To clone the **latest version** do
```bash
git clone https://github.com/psctoolkit/psctoolkit.git
```
or if you want to use ssh:
```bash
git clone git@github.com:psctoolkit/psctoolkit.git
```
To keep it updated with the changes in the individual repositories, use the command:
```bash
git submodule update --init --recursive
```
or to execute ```git pull``` inside each of the folders to synchronize to the latest version.

**Warning:** the various submodules point to mutually compatible versions of the library. Branch switching and pull operations could damage compatibility, especially moving into development branches. The easiest way is to download the latest **stable release**. This contains all versions of the packages that can be compiled together.

## How to install

The possible installation order are:

1) PSBLAS -> PSBLAS-EXT -> AMG4PSBLAS -> SUNDIALS
2) PSBLAS -> AMG4PSBLAS

Each of the libraries contains its own installation instructions. See information on [https://psctoolkit.github.io/libraries/](https://psctoolkit.github.io/libraries/) for each of them.
