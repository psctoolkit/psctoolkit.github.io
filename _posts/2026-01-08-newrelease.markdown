---
layout: post
title:  "PSCTOOLKIT - a sparse linear algebra library for HPC - New Releases of PSBLAS 3.9.0 and AMG4PSBLAS 1.2.0"
date:   2026-01-08 06:00:00
categories: news
description: "New Releases of PSBLAS 3.9.0 and AMG4PSBLAS 1.2.0"
image: https://psctoolkit.github.io/img/news.png
published: true
author: F. Durastante
hero_image: https://psctoolkit.github.io/img/news.png
hero_height: is-large
hero_darken: true
canonical_url: https://psctoolkit.github.io/news/2026/01/08/newreleases.html
---

We are pleased to announce the **release of the newest versions** of the two core components in the **PSCToolkit** suite:

### 🔹 PSBLAS 3.9.0

**PSBLAS** (Parallel Sparse Basic Linear Algebra Subprograms) is the distributed sparse linear algebra library at the heart of the PSCToolkit. It provides scalable and efficient support for parallel sparse matrix operations, iterative solvers, distributed memory execution, and interfaces to high-performance computing environments. 

**Highlights in 3.9.0:**
- Direct support for GPU acceleration, no longer needing PSBLAS-EXT for GPU offloading. 
- Now supports installation via CMake, in addition to the traditional configure/make system.
- Improvement of the C interface for easier integration with C/C++ applications.

This release is recommended for all current and new developments relying on PSBLAS. 

👉 Full details and downloads: [https://psctoolkit.github.io/products/psblas/](https://psctoolkit.github.io/products/psblas/)

---

### 🔹 AMG4PSBLAS 1.2.0

**AMG4PSBLAS** is the algebraic multigrid preconditioner package designed to work seamlessly with PSBLAS. It implements highly parallel multilevel preconditioners optimized for use with large-scale iterative solvers. 

**Key features in 1.2.0:**
- New polynomial smoothers optimized for GPU architectures, enhancing convergence rates on modern hardware.
- Now supports CMake for easier building and integration.
- Improvement of the C interface for better usability in C/C++ projects. 

AMG4PSBLAS works in tandem with PSBLAS 3.9.0 to enable efficient preconditioning for large sparse linear systems. 

👉 Full details and downloads: [https://psctoolkit.github.io/products/amg4psblas/](https://psctoolkit.github.io/products/amg4psblas/)

---

## 🚀 Getting Started

Both libraries come with source code, documentation, and examples — and can be built using standard tools like `configure`/`make` or CMake. They are designed to support HPC environments with MPI and optional GPU support. 

We encourage users to upgrade to these latest releases to take advantage of improved performance, scalability, and ease of integration in scientific computing workflows.

For support, documentation, and issue reporting, visit the PSCToolkit GitHub organization or the project websites.


