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

To build this code you need to have PSBLAS 3.8.0-2 or later, together
with its prerequisites.

To make use of the NVIDIA GPU you'll need:
1. An installation of the CUDA toolkit (version $ \geq 10$);
2. The SPGPU code from [davidebarbieri/spgpu](https://github.com/davidebarbieri/spgpu)

RELEASE
-------

Library releases for PSBLAS-EXT.

|Release | Date | Sources                        | Documentation             | Works with |
|--------|------|--------------------------------|---------------------------| -----------|
| Version 1.3.1 | September 29, 2023 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3-ext/archive/refs/tags/v1.3.2.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3-ext/archive/refs/tags/v1.3.2.tar.gz)  | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/psblasextguide/psblas-ext-1.3.pdf){:target="_blank"} | PSBLAS 3.8.1 |
| Version 1.3.1 | Novembre 24, 2022 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3-ext/archive/refs/tags/v1.3.1.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3-ext/archive/refs/tags/v1.3.1.tar.gz)  | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/psblasextguide/psblas-ext-1.3.pdf){:target="_blank"} | PSBLAS 3.8.0-2 |
| Version 1.3.0 | May 12, 2021 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3-ext/archive/refs/tags/V1.3.0.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3-ext/archive/refs/tags/V1.3.0.tar.gz)  | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3-ext/raw/maint-1.3.0/docs/psblas-ext-1.0.pdf){:target="_blank"} | PSBLAS 3.7.0.1 |
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

License
-------

PSBLAS-EXT is distributed under the BSD 3-Clause license.

```
              Parallel Sparse BLAS  Extensions plugin 
    (C) Copyright 2014

                       Salvatore Filippone
                       Alessandro Fanfarillo
 
  Redistribution and use in source and binary forms, with or without
  modification, are permitted provided that the following conditions
  are met:
    1. Redistributions of source code must retain the above copyright
       notice, this list of conditions and the following disclaimer.
    2. Redistributions in binary form must reproduce the above copyright
       notice, this list of conditions, and the following disclaimer in the
       documentation and/or other materials provided with the distribution.
    3. The name of the PSBLAS group or the names of its contributors may
       not be used to endorse or promote products derived from this
       software without specific written permission.
 
  THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
  ``AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED
  TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
  PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE PSBLAS GROUP OR ITS CONTRIBUTORS
  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
  CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
  SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
  INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
  CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
  ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
  POSSIBILITY OF SUCH DAMAGE.
 ```