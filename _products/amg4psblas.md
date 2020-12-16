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

AMG4PSBLAS library
===========================

This package provides parallel Algebraic MultiGrid (AMG), to be used in the
iterative solution of linear systems.

The package is an evolution of the MLD2P4 package  
containing multilevel additive and hybrid Schwarz preconditioners,
as well as one-level additive Schwarz preconditioners. The current
version extends the original plan by including multilevel cycles
and smoothers widely used in multigrid methods. In AMG4PSBLAS a purely algebraic
approach is applied to generate coarse-level corrections, so that
no geometric background is needed concerning the matrix to be
preconditioned.

AMG4PSBLAS has been designed to provide scalable and easy-to-use preconditioners
in the context of the PSBLAS (Parallel Sparse Basic
Linear Algebra Subprograms) computational framework and is used
in conjuction with the Krylov solvers available from PSBLAS. The
package employs object-oriented design techniques in Fortran 2003,
with interfaces to additional third party libraries such as MUMPS,
UMFPACK, SuperLU, and SuperLU_Dist, which can be exploited in building
multilevel preconditioners. The parallel implementation is based on
a Single Program Multiple Data (SPMD) paradigm; the inter-process
communication is based on MPI and is managed mainly through PSBLAS.

RELEASE
-------
Library releases for AGM4PSBLAS are coming...

Library releases for MLD2P4 can be downloaded from: [mld2p4/releases](https://github.com/sfilippone/mld2p4-2/releases)

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
- Fabio Durastante
- Salvatore Filippone

Contributors to MLD2P4:
- Daniela di Serafino
- Ambra Abdullahi Hassan
- Alfredo Buttari
