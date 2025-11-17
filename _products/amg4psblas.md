---
title: AMG4PSBLAS
subtitle: Preconditioners for PSBLAS
description: Parallel Algebraic Multigrid and Domain Decomposition Preconditioners
product_code: AMG4PSBLAS
layout: product
image: /img/amg4psblaslibrary.png
features:
    - label: Parallel AMG Preconditioners
      icon: fa-user-clock
    - label: Highly Parallel Smoothers
      icon: fa-puzzle-piece
    - label: Tested on tens of thousands of cores
      icon: fa-network-wired
    - label: Excellent innovation in the EU Innovation Radar
      icon: fa-star
order: 2
---

Algebraic Multigrid Package  based on [PSBLAS](https://github.com/sfilippone/psblas3) (Parallel Sparse BLAS version 3.9)

AMG4PSBLAS is a package of parallel algebraic multilevel preconditioners included in the PSCToolkit (Parallel Sparse Computation Toolkit) software framework.

It is a progress of a software development project started in 2007, named MLD2P4, which originally implemented a multilevel version of some domain decomposition preconditioners of additive-Schwarz type and was based on a parallel decoupled version of the well known smoothed aggregation method to generate the multilevel hierarchy of coarser matrices.

In the last years the package was extended for including new algorithms and functionalities for the setup and application new AMG preconditioners with the final aims of improving efficiency and scalability when tens of thousands cores are used and of boosting reliability in dealing with general symmetric positive definite linear systems.

It is an evolution of MLD2P4 (see [LICENSE.MLD2P4](LICENSE.MLD2P4)), but due to the significant number of changes and the increase in scope, we decided to rename the package as AMG4PSBLAS.

AMG4PSBLAS has been designed to provide scalable and easy-to-use preconditioners in the context of the PSBLAS (Parallel Sparse Basic Linear Algebra Subprograms) computational framework and can be used in conjuction with the Krylov solvers available in this framework. Our package is based on a completely algebraic approach; therefore users level interfaces assume that the system matrix and preconditioners are represented as PSBLAS distributed sparse matrices.

AMG4PSBLAS enables the user to easily specify different features of an algebraic multilevel preconditioner, thus allowing to experiment with different preconditioners for the problem and parallel computers at hand.

The package employs object-oriented design techniques in Fortran 2008, with interfaces to additional third party libraries such as MUMPS, UMFPACK, SuperLU, and SuperLU_Dist, which can be exploited in building multilevel preconditioners. The parallel implementation is based on a Single Program Multiple Data (SPMD) paradigm; the inter-process communication is based on MPI and is managed mainly through PSBLAS.

RELEASE
-------
Library releases for AGM4PSBLAS.

|Release | Date | Sources                        | Documentation             | Works with |
|--------|------|--------------------------------|---------------------------| -----------|
| Version 1.2-rc3 | July 23, 2025 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/v1.2.0-rc3.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/v1.2.0-rc3.tar.gz)  | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/amg4psblasguide/amg4psblas_1.2-guide-rc3.pdf){:target="_blank"} | PSBLAS 3.9-rc3 |


## Main Refrerences:

The main reference for this project is
> D'Ambra, P., Durastante, F., & Filippone, S. (2021). AMG preconditioners for linear solvers towards extreme scale. SIAM Journal on Scientific Computing, 43(5), S679-S703.

AMG4PSBLAS is the suite of preconditioners for the Parallel Sparse Computation Toolkit ([PSCToolkit](https://psctoolkit.github.io/)) suite of libraries. See the paper:
> D’Ambra, P., Durastante, F., & Filippone, S. (2023). Parallel Sparse Computation Toolkit. Software Impacts, 15, 100463.

The main reference for features inherited from MLD2P4 is
> P. D'Ambra, D. di Serafino, S. Filippone,
> MLD2P4: a Package of Parallel Algebraic Multilevel Domain Decomposition
> Preconditioners in Fortran 95,
> ACM Transactions on Mathematical Software, 37 (3), 2010, art. 30,
> doi: 10.1145/1824801.1824808.

## Installing

Installation requires having a working version of the [PSBLAS](https://github.com/sfilippone/psblas3) library installed.
AMG4PSBLAS has several interfaces to third-party libraries that can be used in the construction and application phases of preconditioners. 
In particular, it is possible to link AMG4PSBLAS with the libraries: MUMPS, SuperLU, SuperLU_Dist, UMFPACK. This is _not mandatory_ and the library can run 
in isolation and without these features.

0. Unpack the tar file in a directory of your choice (preferrably
   outside the main PSBLAS directory).
1. run configure `--with-psblas=<ABSOLUTE path of the PSBLAS install directory>`
   adding the options for MUMPS, SuperLU, SuperLU_Dist, UMFPACK as desired.
   See [AMG4PSBLAS User's and Reference Guide](docs/amg4psblas_1.0-guide.pdf) (Section 3) for details.
2. Tweak `Make.inc` if you are not satisfied.
3. run `make`; 
4. Go into the test subdirectory and build the examples of your choice.
5. (if desired): `make install` 

>The single precision version is supported only by MUMPS and SuperLU;
>thus, even if you specify at configure time to use UMFPACK or SuperLU_Dist,
>the corresponding preconditioner options will be available only from
>the double precision version.

### CUDA, OpeMP, OpenACC

CUDA, OpenMP and OpenACC features are transparently inherited by PSBLAS installation. If PSBLAS has been configured (and installed) with these supports then AMG4PSBLAS will transparently inherit them. It will then be possible to move the computation to GPU accelerator simply by selecting the appropriate variable types. If these have not been activated or installed for PSBLAS then they will not be available for AMG4PSBLAS either and the operation will be purely on CPU/MPI. See also the samples/cuda folder.

### EoCoE - Software as service portal

In the European project “Energy oriented Center of Excellence: toward exascale for energy” we made available a software as service portal: [https://eocoe.psnc.pl/](https://eocoe.psnc.pl/). This permits to test several cutting-edge computational methods for accelerating the transition to the production, storage and management of clean, decarbonized energy. Among them you have the possibility of running PSBLAS+AMG4PSBLAS on some test problems to become familiar with using the software.

## TODO and bugs
 
- [X] Fix all reamining bugs. Bugs? We dont' have any ! 🤓

> [!NOTE]
> To report bugs 🐛 or issues ❓ please use the [GitHub issue system](https://github.com/sfilippone/amg4psblas/issues).

## The AMG4PSBLAS team. 

- Pasqua D'Ambra         (IAC-CNR, Naples, IT)
- Fabio Durastante       (University of Pisa and IAC-CNR, IT)
- Salvatore Filippone    (University of Rome Tor Vergata and IAC-CNR, IT)

**Contributors** (_roughly reverse cronological order_):

- Luca       Pepè Sciarria
- Andea      Di Iorio
- Ambra	     Abdullahi Hassan
- Alfredo    Buttari

License
-------

AMG4PSBLAS is distributed under the BSD 3-Clause license.

```
 AMG4PSBLAS version 1.1
  Algebraic Multigrid Package based on PSBLAS (Parallel Sparse BLAS version 3.8)
  
  (C) Copyright 2022

      Salvatore Filippone  
      Pasqua D'Ambra   
      Fabio Durastante        
  
  Redistribution and use in source and binary forms, with or without
  modification, are permitted provided that the following conditions
  are met:
    1. Redistributions of source code must retain the above copyright
        notice, this list of conditions and the following disclaimer.
    2. Redistributions in binary form must reproduce the above copyright
        notice, this list of conditions, and the following disclaimer in the
        documentation and/or other materials provided with the distribution.
    3. The name of the AMG4PSBLAS group or the names of its contributors may
        not be used to endorse or promote products derived from this
        software without specific written permission.
  
  THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
  ``AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED
  TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
  PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE AMG4PSBLAS GROUP OR ITS CONTRIBUTORS
  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
  CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
  SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
  INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
  CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
  ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
  POSSIBILITY OF SUCH DAMAGE.
```

The code inherited from MLD2P4 is again available under the BSD 3-Clause license.
```
MLD2P4  version 2.2
  MultiLevel Domain Decomposition Parallel Preconditioners Package
             based on PSBLAS (Parallel Sparse BLAS version 3.5)
  
  (C) Copyright 2008-2018

      Salvatore Filippone  
      Pasqua D'Ambra   
      Daniela di Serafino   

 
  Redistribution and use in source and binary forms, with or without
  modification, are permitted provided that the following conditions
  are met:
    1. Redistributions of source code must retain the above copyright
       notice, this list of conditions and the following disclaimer.
    2. Redistributions in binary form must reproduce the above copyright
       notice, this list of conditions, and the following disclaimer in the
       documentation and/or other materials provided with the distribution.
    3. The name of the MLD2P4 group or the names of its contributors may
       not be used to endorse or promote products derived from this
       software without specific written permission.
 
  THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
  ``AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED
  TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
  PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE MLD2P4 GROUP OR ITS CONTRIBUTORS
  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
  CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
  SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
  INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
  CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
  ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
  POSSIBILITY OF SUCH DAMAGE.
```

# For versions prior to 1.2

The versions below (1.0–1.1.x) remain available and are validated against PSBLAS 3.7–3.8 and PSBLAS-EXT 1.3.x. They are in maintenance mode (critical fixes only), and the user/reference manual is frozen at the 1.0 guide. Expect minor differences in configure flags, preconditioner/solver keywords, and Make.inc variables versus 1.2; prefer a clean rebuild when upgrading and consult the guide’s build/configuration sections for migration notes. New development and full GPU/OpenMP improvements are tracked on the 1.2+ line.

|Release | Date | Sources                        | Documentation             | Works with |
|--------|------|--------------------------------|---------------------------| -----------|
| Version 1.1.2 | November 26, 2023 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/v1.1.2.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/v1.1.2.tar.gz)  | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/amg4psblasguide/amg4psblas_1.0-guide.pdf){:target="_blank"} [![HTML](/img/htmlicon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/amg4psblasguide/index.html){:target="_blank"}  | PSBLAS 3.8.1-2, PSBLAS-EXT  Version 1.3.2 |
| Version 1.1.1 | September 29, 2023 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/v1.1.1.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/v1.1.1.tar.gz)  | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/amg4psblasguide/amg4psblas_1.0-guide.pdf){:target="_blank"} [![HTML](/img/htmlicon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/amg4psblasguide/index.html){:target="_blank"}  | PSBLAS 3.8.1, PSBLAS-EXT  Version 1.3.2 |
| Version 1.1.0 | May 24, 2022 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/v1.1.0.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/v1.1.0.tar.gz)  | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/amg4psblasguide/amg4psblas_1.0-guide.pdf){:target="_blank"} [![HTML](/img/htmlicon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/amg4psblasguide/index.html){:target="_blank"}  | PSBLAS 3.8.0, PSBLAS-EXT 1.3.0-rc1 |
| Version 1.0 | May 11, 2021 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/V1.0.0.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/V1.0.0.tar.gz)  | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/amg4psblasguide/amg4psblas_1.0-guide.pdf){:target="_blank"} [![HTML](/img/htmlicon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/amg4psblasguide/index.html){:target="_blank"}  | PSBLAS 3.7.0.1, PSBLAS-EXT 1.3.0-rc1 |
| Version 1.0-rc2 | April 12, 2021 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/v1.0-rc2.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/amg4psblas/archive/refs/tags/v1.0-rc2.tar.gz)  | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/amg4psblasguide/amg4psblas_1.0-rc-guide.pdf){:target="_blank"} [![HTML](/img/htmlicon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/amg4psblasguide/index.html){:target="_blank"}  | PSBLAS 3.7.0, PSBLAS-EXT 1.3.0-rc1 |

Library releases for MLD2P4 can be downloaded from: [mld2p4/releases](https://github.com/sfilippone/mld2p4-2/releases)

|Release | Date       | Sources                               |
|--------|------------|---------------------------------------|
| Version 2.2.2  | 6 May 2020 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/mld2p4-2/archive/refs/tags/v2.2.2.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/mld2p4-2/archive/refs/tags/v2.2.2.tar.gz) |