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
order: 3
---

AMG4PSBLAS (*Algebraic MultiGrid Preconditioners Package based on PSBLAS*) is a
package of parallel algebraic multilevel preconditioners included in the PSCToolkit
(Parallel Sparse Computation Toolkit) software framework.

It is a progress of a software development project started in 2007, named MLD2P4,
which originally implemented a multilevel version of some domain decomposition
preconditioners of additive-Schwarz type and was based on a parallel decoupled
version of the well known smoothed aggregation method to generate the multilevel
hierarchy of coarser matrices.

In the last years, within the context of the EU-H2020 EoCoE project (Energy
Oriented Center of Excellence), the package was extended for including new
algorithms and functionalities for the  setup and application new AMG
preconditioners with the final aims of improving efficiency and scalability when
tens of thousands cores are used and of boosting reliability in dealing with
general symmetric positive definite linear systems.

Due to the significant number of changes and the increase in scope, we decided
to rename the package as AMG4PSBLAS.

AMG4PSBLAS has been designed to provide scalable and easy-to-use preconditioners
in the context of the PSBLAS (Parallel Sparse Basic Linear Algebra Subprograms)
computational framework and can be used in conjuction with the Krylov solvers
available in this framework.
Our package is based on a completely algebraic approach; therefore users level
interfaces assume that the system matrix and preconditioners are represented
as PSBLAS distributed sparse matrices.

AMG4PSBLAS enables the user to easily specify different
features of an algebraic multilevel preconditioner, thus allowing to experiment
with different preconditioners for the problem and parallel computers at hand.

The package employs object-oriented design techniques in
Fortran 2003, with interfaces to additional third party libraries
such as *MUMPS*, *UMFPACK*, *SuperLU*, and *SuperLU_Dist*, which
can be exploited in building multilevel preconditioners. The parallel
implementation is based on a Single Program Multiple Data (SPMD)
paradigm; the inter-process communication is based on MPI and
is managed mainly through PSBLAS.

RELEASE
-------
Library releases for AGM4PSBLAS.

|Release | Date | Archive                        | Documentation             |
|--------|------|--------------------------------|---------------------------|
| 1.0-RC1|      | ![PDF](../img/archiveicon.png)  | ![PDF](../img/pdficon.png) |      

Library releases for MLD2P4 can be downloaded from: [mld2p4/releases](https://github.com/sfilippone/mld2p4-2/releases)

|Release | Date       | Archive                               |
|--------|------------|---------------------------------------|
| 2.2.2  |6 May 2020  | [![Archive](../img/archiveicon.png)](https://github.com/sfilippone/mld2p4-2/archive/refs/tags/v2.2.2.tar.gz) |


DOCUMENTATION
-------------

An HTML version of the library documentation can be found on the page [AMG4PSBLAS documentation](https://psctoolkit.github.io/amg4psblasguide/index.html). In any case, the software releases contain a copy of the documentation and a pdf version of it.

TO COMPILE
----------
0. Unpack the tar file in a directory of your choice (preferrably
   outside the main PSBLAS directory).
1. run configure `--with-psblas=<ABSOLUTE path of the PSBLAS install directory>`
   adding the options for MUMPS, SuperLU, SuperLU_Dist, UMFPACK as desired.
   See MLD2P4 User's and Reference Guide (Section 3) for details.
2. Tweak Make.inc if you are not satisfied.
3. `make`
4. Go into the test subdirectory and build the examples of your choice.
5. (if desired): `make install`


NOTES
-----
- The single precision version is supported only by MUMPS and SuperLU;
  thus, even if you specify at configure time to use UMFPACK or SuperLU_Dist,
  the corresponding preconditioner options will be available only from
  the double precision version.
- The preconditioners in AMG4PSBLAS extend those of PSBLAS and are meant
  to be used with the PSBLAS Krylov solvers; so in an existing program
  you need to modify the type of the preconditioner object and its
  settings, but the rest of the application needs not be changed.

The AMG4PSBLAS team.
----------------
Contributors:
- [Pasqua D'Ambra](https://www.iac.cnr.it/~dambra/)
- [Fabio Durastante](https://fdurastante.github.io)
- Salvatore Filippone

Contributors to MLD2P4:
- Daniela di Serafino
- Ambra Abdullahi Hassan
- Alfredo Buttari
