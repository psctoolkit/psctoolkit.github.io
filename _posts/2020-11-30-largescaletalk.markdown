---
layout: post
title:  "(Sparse) Linear Algebra at the Extreme Scales"
date:   2020-11-30 10:00:00
categories: seminar
description: "Tutorial for the Learn@EoCoE Initiative"
image: https://psctoolkit.github.io/img/seminar.png
published: true
author: F. Durastante
hero_image: https://psctoolkit.github.io/img/seminar.png
hero_height: is-large
hero_darken: true
canonical_url: https://psctoolkit.github.io/seminar/2020/11/30/largescaletalkpisa.html
---

NumPI seminars 2020-2021 - Numerical Analysis Seminars - Pisa - Tuesday, 01/12/2020, 16:00 CET
by F. Durastante - IAC-CNR

Sparse linear algebra is essential for a wide variety of scientific applications.
The availability of highly parallel sparse solvers and preconditioners lies at the
core of pretty much all multi-physics and multi-scale simulations. Technology
is nowadays expanding to target exascale platforms. I am going to present
some work on Algebraic Multigrid Preconditioners in which we try to face these
challenges to make Exascale Computing possible.
The talk will focus on one side on the theoretical aspects pertaining to the
construction of the multigrid hierarchy for which the main novelty is the design
and implementation of new parallel smoothers and a coarsening algorithm
based on aggregation of unknowns employing weighted graph matching techniques.
On the other, the talk also focuses on the libraries developed to cover
the needs of having parallel BLAS feature for sparse matrices that are capable
of running on machines with thousands of high-performance cores; and to discuss
the advancements made by the new smoothers and coarsening algorithm
as an improvement in terms of numerical scalability at low operator complexity
over the algorithms available in previous releases of the package. I will present
weak scalability results on two of the most powerful supercomputers in Europe,
for linear systems with sizes up to $O(10^{10})$ unknowns for a benchmark Poisson
problem, and strong scaling result for a wind-simulation benchmark problem.

This is a joint work with P. D’Ambra, and S. Filippone. This work is supported by the
EU under the Horizon 2020 Project Energy oriented Centre of
Excellence: toward exascale for energy (EoCoE-II), Project ID: 824158

Meeting link: [BigBlueButton](https://hausdorff.dm.unipi.it/b/leo-xik-xu4)
