---
title: PSBLAS-EXT
subtitle: Parallel Sparse BLAS GPU Plugin
product_code: PSBLAS
layout: product
image: /img/psblaslibraryext.png
features:
    - label: Add NVIDIA-GPU capabilities to your code
      icon: fa-microchip
    - label: Tested on thousands of GPUs
      icon: fa-fighter-jet
rating: 5
order: 2
---

PSBLAS-EXT
===========================

This is the extenstions plugin for PSBLAS

This package contains:
1. Extended matrix formats: ELLPACK, Hacked ELLPACK, DIAgonals, Hacked
   DIAgonals. Note: DIA and HDIA have limited support.      
2. A GPU plugin: gpu-enabled versions of the above, with the CUDA code
   from http://spgpu.googlecode.com,  plus interfaces to
   CSR and HYB formats available in the NVIDIA CuSPARSE lib.
   Note: DIAG and HDIAG have limited support.
3. RSB: an interface to http://sourceforge.net/projects/librsb


PREREQUISITES
-------------

To build this code you need to have PSBLAS 3.3.0 or later, together
with its prerequisites.

To make use of the NVIDIA GPU you'll need:
1. An installation of the CUDA toolkit (version 4.1 or later);
2. The SPGPU code from http://spgpu.googlecode.com



INSTALLING
----------

./configure --prefix=/path/to/install \
            --with-psblas=/path/to/PSBLAS/install \
	    --with-cuda=/CUDA/install \
	    --with-spgpu=/SPGPU/install \
	    --with-librsb=/LIBRSB/install

make;
make install

Note: we have only tested with GNU Fortran compiler.
Note: CUDA nvcc typically lags behind the latest  versions of GCC/GNU
      Fortran; currently nvcc supports GCC 4.8 so this is the preferred choice.
      Mixing SPGPU CUDA code  compiled with an older version and the rest with
      e.g. 4.9 has  worked fine so far: YMMV.  


TODO
----
Improve MPI support.


WHAT IS NOT HERE
----------------
Good preconditioners for the GPU. Performance of  triangular system
solves on the GPU is very bad: we enable it in CSRG and HYBG, we do
not even bother to implement it in ELG and HLG.  
So if you use the GPU, you are limited to no preconditioning, or
diagonal scaling. We are working on an independent plugin for mld2p4
(www.mld2p4.it) that will deliver better alternatives based on
approximate inverses.  


Report bugs to:
 https://github.com/sfilippone/psblas3-ext/issues

Contributors
------------
 Salvatore Filippone     
 Alessandro Fanfarillo   