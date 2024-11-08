---
title: PSCToolkit
subtitle: Parallel Sparse Computation Toolkit
description:
product_code: PSCTOOLKIT
layout: product
image: /img/psctoolkit.png
features:
    - label: PSBLAS Parallel Sparse BLAS
      icon: fa-code
    - label: PSBLAS-EXT GPU Plugin for Parallel Sparse BLAS
      icon: fa-puzzle-piece
    - label: AMG4PSBLAS Preconditioners for PSBLAS
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

| PSCToolkit Stable Version | Libraries        |                    |
|---------------------------|------------------|--------------------|
| Version 1.0.0      | PSBLAS 3.7.0.1   | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/V3.7.0.1.zip) [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/V3.7.0.1.tar.gz)    |
|                    | AMG4PSBLAS 1.0.0 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/V1.0.0.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/V1.0.0.tar.gz)   |
|                    | PSBLAS-EXT 1.3.0 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3-ext/archive/refs/tags/V1.3.0.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3-ext/archive/refs/tags/V1.3.0.tar.gz)    |

## How to install

The possible installation order are:

1. PSBLAS -> PSBLAS-EXT -> AMG4PSBLAS -> SUNDIALS
2. PSBLAS -> AMG4PSBLAS -> PSBLAS-EXT -> SUNDIALS
3. PSBLAS -> AMG4PSBLAS


Each of the libraries contains its own installation instructions. See information on [https://psctoolkit.github.io/libraries/](https://psctoolkit.github.io/libraries/) for each of them.

### Docker container

We have also available an *experimental* Docker container containing the installation of the core libraries PSBLAS, PSBLAS-EXT, and AMG4PSBLAS (without GPU support). Such container is a unit of software packaging up the source code, the compiled version of the library, and all the relevant dependencies. The idea is to have a version of the PSCToolkit that can run quickly and reliably from one computing environment to another.

The container is available on [dockerhub](https://hub.docker.com/r/psctoolkit/psctoolkit). If you have a version of Docker installed on your
machine, you can use the image by doing
```bash
docker pull psctoolkit/psctoolkit
```
The library is installed under `/usr/local/psctoolkit`. The container is built upon the latest long term release of Ubuntu and uses the packaged versions of the software to fulfill the PSCToolkit prerequisites and
the auxiliary libraries.
