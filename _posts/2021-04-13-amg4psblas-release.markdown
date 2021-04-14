---
layout: post
title:  "AMG4PSBLAS Version 1.0 - RC1"
date:   2021-04-13 12:00:00
categories: news
description: "The AMG4PSBLAS development team gladly announce the release of version 1.0 (release candidate 1 - rc1) of the package."
image: https://psctoolkit.github.io/img/news.png
published: true
author: F. Durastante
hero_image: https://psctoolkit.github.io/img/news.png
hero_height: is-large
hero_darken: true
canonical_url: https://psctoolkit.github.io/news/2021/04/13/amg4psblasrelease1.html
---

The AMG4PSBLAS development team gladly announce the release of version 1.0 (release candidate 1 --- rc1) of the package.

AMG4PSBLAS (Algebraic MultiGrid Preconditioners Package based on
PSBLAS) is a package of parallel algebraic multilevel preconditioners included in the PSCToolkit (Parallel Sparse Computation Toolkit) software framework ([https://psctoolkit.github.io/](https://psctoolkit.github.io/)); its development is supported by
the EU-H2020 EoCoE (Energy Oriented Center of Excellence) project, and the package has been selected by EU Innovation Radar as recent excellent innovation.

AMG4PSBLAS is  designed to provide scalable and easy-to-use preconditioners in the context of the  PSBLAS (Parallel Sparse Basic Linear Algebra Subprograms) parallel computing framework, to  be used in conjunction with the PSBLAS Krylov solvers.
The library uses a fully algebraic approach to generate a hierarchy of coarse-level matrices and operators; it includes a new parallel coupled aggregation algorithm exploiting maximum edge-weighted matchings.
The preconditioners in AMG4PSBLAS can combine different types of AMG cycles with many smoothers and coarsest-level solvers. AMG4PSBLAS runs on most parallel computers, requiring only PSBLAS, the BLAS and MPI.  

A GPU plugin for PSBLAS (available separately from [https://psctoolkit.github.io/](https://psctoolkit.github.io/)) enables the execution of AMG4PSBLAS
applications on clusters with hybrid CPU/GPU nodes.
