---
title: License
layout: page
show_sidebar: false
---

The **Parallel Sparse Computation Toolkit (PSCToolkit)** library suite is distributed under the **BSD-3 Clause License**, a permissive open-source license that provides flexibility for both academic and commercial use.  

### What is the BSD-3 Clause License?  
The **BSD-3 Clause License** (Berkeley Software Distribution 3-Clause License) is a widely used, permissive open-source license that allows for broad use and redistribution of the software, with minimal restrictions. It is an evolution of the original BSD license, with an additional clause preventing the use of the project's name for endorsement without permission.  

### What Users Can Do  
Under the BSD-3 Clause License, users are granted the following permissions:  

- **Use, modify, and distribute** the software freely.  
- **Incorporate it into proprietary or open-source projects**, including commercial applications.  
- **Distribute modified or unmodified versions**, as long as the original copyright notice and disclaimers are maintained.
- **Use it for personal, academic, research, or commercial purposes** without the need to release derivative works under the same license.  

### What Users Cannot Do  
While the BSD-3 Clause License is permissive, there are a few restrictions:  

- **No liability or warranty**: The software is provided "as is," without any warranty, and the authors are not responsible for any damages resulting from its use.  
- **No endorsement**: Users cannot use the name of the original project, contributors, or organization to promote their own derived software without prior permission.  
- **Must retain copyright notices**: Any redistribution, be it in source code form or object code form, must include the original copyright statement and disclaimer.  

### Philosophy Behind the BSD-3 Clause License  
The BSD-3 Clause License aligns with the **open-source philosophy** by promoting innovation, collaboration, and widespread adoption of software. Unlike restrictive licenses such as the GPL, BSD-3 allows developers to integrate the code into both open-source and proprietary projects without imposing copyleft obligations.  

This permissive approach encourages industry adoption while maintaining recognition for the original authors. It strikes a balance between _freedom_ and _credit_, making it a popular choice for academic, research, and enterprise software.  

By using the BSD-3 Clause License, the **PSCToolkit** ensures that its software remains **accessible, adaptable, and widely applicable** across different domains while respecting the contributions of its developers.  

## Third-party Libraries

The PSCToolkit library can be linked against several third-party auxiliary libraries, each distributed under its own license. It is important for users to review these licenses to ensure compliance when integrating these libraries into their projects. Below is a brief overview of the supported libraries along with links for more detailed information:

- **SuiteSparse (UMFPACK)**  
  SuiteSparse is a comprehensive suite of sparse matrix algorithms. It includes **UMFPACK**, which is specialized in solving unsymmetric sparse systems.  
  [Learn more about SuiteSparse (UMFPACK)](http://faculty.cse.tamu.edu/davis/suitesparse.html)

- **MUMPS**  
  MUMPS is a parallel sparse direct solver designed for solving large systems of linear equations. It is particularly well-suited for high-performance computing environments.  
  [Learn more about MUMPS](http://mumps.enseeiht.fr/)

- **SuperLU**  
  SuperLU is a library dedicated to solving large, sparse, nonsymmetric linear systems on high-performance machines.  
  [Learn more about SuperLU](http://crd-legacy.lbl.gov/~xiaoye/SuperLU/)

- **SuperLU_Dist**  
  SuperLU_Dist extends SuperLU's capabilities to distributed-memory architectures, allowing it to operate efficiently in parallel computing environments.  
  [Learn more about SuperLU_Dist](http://crd-legacy.lbl.gov/~xiaoye/SuperLU_DIST/)

- **METIS**  
  METIS provides algorithms for partitioning unstructured graphs, meshes, and for computing fill-reducing orderings of sparse matrices, which is crucial for efficient sparse matrix computations.  
  [Learn more about METIS](http://glaros.dtc.umn.edu/gkhome/metis/metis/overview)

Each of these libraries comes with its own set of license terms. Users are responsible for ensuring that the use of these libraries in their projects complies with the respective licenses.

### BLAS Implementation

PSCToolkit requires an implementation of the Basic Linear Algebra Subprograms (BLAS) to perform essential vector and matrix computations. Unlike the optional auxiliary libraries, a BLAS library is a necessary dependency for PSCToolkit to function properly. There are several open-source BLAS implementations available, each offering different performance benefits and coming under various licensing terms. Popular choices include [OpenBLAS](https://www.openblas.net/), renowned for its high-performance, multi-threaded routines; [ATLAS](http://math-atlas.sourceforge.net/), which automatically tunes its routines for optimal performance on specific hardware; and [BLIS](https://github.com/flame/blis), a flexible framework designed for rapid development of high-performance BLAS-like libraries. It is important to note that while these implementations are open source, some may have more restrictive licenses compared to the BSD-3 Clause license governing PSCToolkit. Users should review the specific licensing terms of the chosen BLAS library to ensure compliance with their project requirements.



