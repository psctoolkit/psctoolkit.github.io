---
title: PSBLAS-EXT
subtitle: Parallel Sparse BLAS GPU Plugin
description: Parallel Sparse BLAS for an hybrid MPI-NVIDIA code
product_code: PSBLAS-EXT
layout: product
image: /img/psblaslibraryext.png
features:
    - label: Add NVIDIA-GPU capabilities to your code
      icon: fa-microchip
    - label: Tested on thousands of GPUs
      icon: fa-fighter-jet
order: 2
---

This is the **extenstions plugin for PSBLAS**

This package contains:
1. Extended matrix formats: ELLPACK, Hacked ELLPACK, DIAgonals, Hacked
   DIAgonals. Note: DIA and HDIA have limited support.      
2. A GPU plugin: gpu-enabled versions of the above, with the CUDA code
   from [davidebarbieri/spgpu](https://github.com/davidebarbieri/spgpu), plus interfaces to
   CSR and HYB formats available in the NVIDIA CuSPARSE lib.
   Note: DIAG and HDIAG have limited support.
3. RSB: an interface to [librsb](http://sourceforge.net/projects/librsb)


PREREQUISITES
-------------

To build this code you need to have PSBLAS 3.7.0 or later, together
with its prerequisites.

To make use of the NVIDIA GPU you'll need:
1. An installation of the CUDA toolkit (version 10);
2. The SPGPU code from [davidebarbieri/spgpu](https://github.com/davidebarbieri/spgpu)

:point_right: Need to update code for CUDA 11 (where the HYB format has been dropped).

RELEASE
-------

Library releases for PSBLAS-EXT.

|Release | Date | Sources                        | Documentation             | Works with |
|--------|------|--------------------------------|---------------------------| -----------|
| Version 1.3.0-rc1 | April 12, 2021 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3-ext/archive/refs/tags/V1.3.0-rc1.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3-ext/archive/refs/tags/V1.3.0-rc1.tar.gz)  | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/psblasextguide/psblas-ext-1.0.pdf){:target="_blank"} | PSBLAS 3.7.0 |

Library releases can be downloaded from: [psblas3-ext/releases](https://github.com/sfilippone/psblas3-ext/releases)

INSTALLING
----------
```
./configure --prefix=/path/to/install \
            --with-psblas=/path/to/PSBLAS/install \
	    --with-cuda=/CUDA/install \
	    --with-spgpu=/SPGPU/install \
	    --with-librsb=/LIBRSB/install

make;
make install
```

*Note:* we have only tested with GNU Fortran compiler.

*Note:* CUDA nvcc typically lags behind the latest  versions of GCC/GNU
      Fortran; currently nvcc supports GCC 8 so this is the preferred choice.
      Mixing SPGPU CUDA code  compiled with an older version and the rest with
      e.g. 4.9 has  worked fine so far: YMMV.
			See the [docs at NVIDIA](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#system-requirements) for further information on the compatibility between GCC and nvcc.  


TODO
----
Improve MPI support.

WHAT IS NOT HERE
----------------
Good preconditioners for the GPU. Performance of  triangular system
solves on the GPU is very bad: we enable it in CSRG and HYBG, we do
not even bother to implement it in ELG and HLG.  
So if you use the GPU, you are limited to no preconditioning, or
diagonal scaling. We are working on an independent plugin that will deliver
better alternatives based on approximate inverses.  


Report bugs to:
 https://github.com/sfilippone/psblas3-ext/issues

Contributors
------------
- Salvatore Filippone     
- Alessandro Fanfarillo   
