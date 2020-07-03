---
layout: post
title:  "MLD2P4: a Package of Parallel Algebraic MultiGrid Preconditioners for Scalable Linear Solvers"
date:   2020-01-20 10:00:00
categories: training
description: "Tutorial for the Learn@EoCoE Initiative"
image: https://psctoolkit.github.io/img/training.png
published: true
author: P. D'Ambra
hero_image: https://psctoolkit.github.io/img/training.png
hero_height: is-large
hero_darken: true
canonical_url: https://psctoolkit.github.io/training/2020/01/20/mld2p4tutorialeocoe.html
---

Current applications in Computational and Data Science often require the solution of large and sparse linear systems. The notion of "large" is qualitative and there is a clear tendency to increase it; currently, needing to solve systems with millions or even billions of unknowns is not unusual. To efficiently solve the above systems on high-end massively parallel computers, the methods of choice are the Krylov methods, whose convergence and scalability properties are related to the choice of suitable preconditioning techniques. During this webinar, Pasqua D'Ambra, Senior Research Scientist at the National Research Council of Italy, will present MLD2P4 (MultiLevel Domain Decomposition Parallel Preconditioners Package based on PSBLAS), which provides efficient and easy-to-use preconditioners in the context of the PSBLAS (Parallel Sparse Basic Linear Algebra Subprograms) computational framework. The package, whose features are constantly updated within the Energy-Oriented Center of Excellence (EoCoE) European project, includes multilevel cycles and smoothers widely used in multigrid methods. A purely algebraic approach is applied to generate coarse-level corrections so that no geometric background is needed concerning the matrix to be preconditioned. We will present the main features of the package, and example of usage of the main APIs needed to setup the preconditioner, together with its application within the Krylov solvers available from PSBLAS. Some results on test cases relative to the EoCoE application areas highlight how the PSBLAS/MLD2P4 software framework can be used to obtain highly scalable linear solvers.


This tutorial is part of the [Learn@EoCoE initiative](https://www.eocoe.eu/video_resource/mld2p4-a-package-of-parallel-algebraic-multigrid-preconditioners-for-scalable-linear-solvers/).

[![MLD2P4 - Click to Watch!](https://psctoolkit.github.io/img/eocoemld2p4tutorial.png)](https://youtu.be/Hp9LLeRuFm0 "MLD2P4 - Click to Watch!")
