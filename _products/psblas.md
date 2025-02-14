---
title: PSBLAS
subtitle: Parallel Sparse BLAS
description: Parallel Sparse Basic Linear Algebra Subroutines
product_code: PSBLAS
layout: product
image: /img/psblaslibrary.png
features:
    - label: Great addition to any scientific project
      icon: fa-plus-square
    - label: Comes with a range of interfaces
      icon: fa-handshake
    - label: Tested on tens of thousands of cores
      icon: fa-network-wired
ratings: 0
order: 1
---

The **PSBLAS library**, developed with the aim to facilitate the
parallelization of computationally intensive scientific applications,
is designed to address parallel implementation of iterative solvers
for sparse linear systems through the distributed memory paradigm.  It
includes routines for multiplying sparse matrices by dense matrices,
solving block diagonal systems with triangular diagonal entries,
preprocessing sparse matrices, and contains additional routines for
dense matrix operations.  The current implementation of PSBLAS
addresses a distributed memory execution model operating with message
passing.

The PSBLAS library version 3 is  implemented in the Fortran 2003 programming
language, with reuse and/or adaptation of  existing Fortran 77 and Fortran 95
software, plus a handful of C  routines.

## UTILITIES

The `test/util` directory contains some utilities to convert to/from
Harwell-Boeing and MatrixMarket file formats.


## DOCUMENTATION
-------------
See `docs/psblas-3.7.pdf`; an HTML version of the same document is
available in `docs/html`, and on this website.

Please consult the sample programs, especially
`test/pargen/psb_[sd]_pde[23]d.f90`


## OTHER SOFTWARE CREDITS

We originally included a modified implementation of some of the Sparker
(serial sparse BLAS)  material; this has been completely rewritten, way
beyond the intention(s) and responsibilities of the original developers.
The main reference for the serial sparse BLAS is:
>Duff, I., Marrone, M., Radicati, G., and Vittoli, C. Level 3 basic
>linear algebra subprograms for sparse matrices: a user level interface,
>ACM Trans. Math. Softw., 23(3), 379-401, 1997.


## RELEASE


Library releases for PSBLAS.

|Release | Date | Sources                        | Documentation             |
|--------|------|--------------------------------|---------------------------|
| Version 3.8.1-2 | November 13, 2023 |  [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/v3.8.1-2.zip) [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/v3.8.1-2.tar.gz) |  [![PDF](/img/pdficon.png){:height="24px" width="24px"}](/psblasguide/psblas-3.8.pdf){:target="_blank"} [![HTML](/img/htmlicon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/psblasguide/index.html){:target="_blank"}  |
| Version 3.8.1 | September 29, 2023 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/v3.8.1.zip) [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/v3.8.1.tar.gz) |  [![PDF](/img/pdficon.png){:height="24px" width="24px"}](/psblasguide/psblas-3.8.pdf){:target="_blank"} [![HTML](/img/htmlicon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/psblasguide/index.html){:target="_blank"}  |
| Version  3.8.0-2 | August 5, 2022 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/v3.8.0-2.zip) [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/v3.8.0-2.tar.gz) | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](/psblasguide/psblas-3.8.pdf){:target="_blank"} [![HTML](/img/htmlicon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/psblasguide/index.html){:target="_blank"}  |
| Version 3.8.0 | May 24, 2022 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/v3.8.0.zip) [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/v3.8.0.tar.gz) | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](/psblasguide/psblas-3.8.pdf){:target="_blank"} [![HTML](/img/htmlicon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/psblasguide/index.html){:target="_blank"}  |
| Version 3.7.0.2 | September 24, 2021 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/v3.7.0.2.zip) [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/v3.7.0.2.tar.gz) | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](/psblasguide/psblas-3.7.0.1.pdf){:target="_blank"} [![HTML](/img/htmlicon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/psblasguide/index.html){:target="_blank"}  |
| Version 3.7.0.1 | May 11, 2021 | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/V3.7.0.1.zip) [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/V3.7.0.1.tar.gz) | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](/psblasguide/psblas-3.7.0.1.pdf){:target="_blank"} [![HTML](/img/htmlicon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/psblasguide/index.html){:target="_blank"}  |
| Version 3.7.0-1 | April 13, 2021  | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/V3.7.0-1.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/V3.7.0-1.tar.gz) | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](/psblasguide/psblas-3.7.pdf){:target="_blank"} [![HTML](/img/htmlicon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/psblasguide/index.html){:target="_blank"}  |    
| Version 3.7.0 | April 12, 2021  | [![ZIP](/img/zipicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/v3.7.0.zip)  [![Archive](/img/archiveicon.png){:height="24px" width="24px"}](https://github.com/sfilippone/psblas3/archive/refs/tags/v3.7.0.tar.gz) | [![PDF](/img/pdficon.png){:height="24px" width="24px"}](/psblasguide/psblas-3.7.pdf){:target="_blank"} [![HTML](/img/htmlicon.png){:height="24px" width="24px"}](https://psctoolkit.github.io/psblasguide/index.html){:target="_blank"}  |    

Library releases can be downloaded from: [psblas3/releases](https://github.com/sfilippone/psblas3/releases)

## INSTALLING

To compile and run our software you will need the following
prerequisites (see also SERIAL below):

1. A working version of MPI

2. A version of the BLAS; if you don't have a specific version for your
   platform you may try ATLAS available from
   [http://math-atlas.sourceforge.net/](http://math-atlas.sourceforge.net/)

3. We have had good results with  the METIS library, from
   [http://www-users.cs.umn.edu/~karypis/metis/metis/main.html](http://www-users.cs.umn.edu/~karypis/metis/metis/main.html).
   This is optional; it is  used in the util and test/fileread
   directories but only if you specify `--with-metis`.

4. If you have the AMD package of Davis, Duff and Amestoy, you can
   specify `--with-amd` (see `./configure --help` for more details).

The configure script will generate a Make.inc file suitable for building
the library. The script is capable of recognizing the needed libraries
with their default names; if they are in unusual places consider adding
the paths with `--with-libs`, or explicitly specifying the names in
`--with-blas`, etc. Please note that a common way for the configure script
to fail is to specify inconsistent MPI vs. plain compilers, either
directly or indirectly via environment variables; e.g. specifying the
Intel compiler with `FC=ifort` while at the same time having an
`MPIFC=mpif90` which points to GNU Fortran. The best way to avoid this
situation is (in our opinion) to use the environment modules package
(see http://modules.sourceforge.net/), and load the relevant
variables with (e.g.)
``` bash
module load gnu46 openmpi
```
This will delegate to the modules setup to make sure that the version of
openmpi in use is the one compiled with the gnu46 compilers. After the
configure script has completed you can always tweak the Make.inc file
yourself.

After you have Make.inc fixed,  run
``` bash
make
```
to  compile the library; go to the test directory and its subdirectories
to get test programs done. If you specify `--prefix=/path` you can do make
install and the libraries will be installed under `/path/lib`, while the
module files will be installed under `/path/modules`. The regular and
experimental C interface header files are under `/path/include`.

### PACKAGE DISTRIBUTION


The PSBLAS library is also distributed as a package for the following Linux distributions.

| Distro  | PSBLAS Version | Reference | Maintainer | To install |
|---------|----------------|-----------|------------|------------|
|Fedora | 3.8.0-2            | [psblas3](https://src.fedoraproject.org/rpms/psblas3) | [sagitter](https://fedoraproject.org/wiki/User:Sagitter) | `dnf install psblas3-serial`  <br> `dnf install psblas3-openmpi` <br> `dnf install psblas3-mpich `<br> `dnf install psblas3-debugsource` <br> `dnf install psblas3-debuginfo` <br> **Note:** For the *mpich* and *openmpi* versions also the `-debuginfo` and `-devel` are available.|

## SERIAL

Configuring with `--enable-serial` will provide a fake MPI stub library
that enables running in pure serial mode; no MPI installation is needed
in this case (but note that the fake MPI stubs are only guaranteed to
cover what we use internally, it's not a complete replacement).

## LONG INTEGERS

From version 3.7.0 of PSBLAS, we handle 8-bytes integer data for the global indices
of distributed matrices, allowing an index space larger than 2G. The default setting
in the configure uses 4 bytes for **local indices**, and 8 bytes for **global indices**.
This can be tuned using the following configure flags.

| Configure flag     |                                                                |
|--------------------|----------------------------------------------------------------|
|`--with-ipk=<bytes>` | Specify the size in bytes for **local indices** and data, default 4 bytes.|
|`--with-lpk=<bytes>`| Specify the size in bytes for **global indices** and data, default 8 bytes.|

**Note:** If you wish to compile PSBLAS with the Metis interfaces then you need
to configure and compile it in a consistent way with the choice made for `--with-lpk`.
This can be achieved by setting the defines in the `metis.h` library, e.g, to use
8 bytes integers and 4 bytes floats
```c
#define IDXTYPEWIDTH 64
#define REALTYPEWIDTH 32
```

## TODO

Fix all reamining bugs. Bugs? We dont' have any ! ;-)


## The PSBLAS team.

Project lead:
Salvatore Filippone

Contributors (roughly reverse cronological order):

- [Fabio Durastante](https://fdurastante.github.io)
- Soren 	   Rasmussen
- Zaak       Beekman
- Ambra	   Abdullahi Hassan
- [Pasqua	   D'Ambra](https://www.iac.cnr.it/~dambra/)
- Alfredo    Buttari
- Daniela    di Serafino
- Michele    Martone
- Michele    Colajanni
- Fabio      Cerioni
- Stefano    Maiolatesi
- Dario      Pascucci

## License

PSBLAS is distributed under the BSD 3-Clause license.

```
              Parallel Sparse BLAS  version 3.8
    (C) Copyright 2006-2022
        Salvatore Filippone
        Alfredo Buttari      
 
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
