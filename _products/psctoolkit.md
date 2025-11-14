---
title: PSCToolkit
subtitle: Parallel Sparse Computation Toolkit
description:
product_code: PSCTOOLKIT
layout: product
image: /img/psctoolkit.png
features:
    - label: PSBLAS Parallel Sparse BLAS
      icon: fa-code
    - label: AMG4PSBLAS Preconditioners for PSBLAS
      icon: fa-tachometer-alt
    - label: Excellent innovation in the EU Innovation Radar
      icon: fa-star
order: 3
---

# PSCToolkit

PSCToolkit is a suite of libraries for high‑performance sparse linear algebra on distributed memory systems, with optional GPU acceleration. It includes:

- PSBLAS — Parallel Sparse BLAS (distributed sparse matrices and vectors)
- AMG4PSBLAS — Algebraic Multigrid preconditioners and solvers for PSBLAS
- SUNDIALS (integration) — ODE/DAE solvers interfaced with PSBLAS

Project home: https://psctoolkit.github.io/
GitHub: https://github.com/psctoolkit/psctoolkit
Docker Hub: https://hub.docker.com/r/psctoolkit/psctoolkit

## Get the Code

### Stable (master)

```bash
git clone --recurse-submodules https://github.com/psctoolkit/psctoolkit.git
```

### Development (bleeding edge)

```bash
git clone --recurse-submodules https://github.com/psctoolkit/psctoolkit.git
cd psctoolkit
git checkout development
git submodule update --init --recursive
```

To update submodules to their tracked branches:

```bash
git submodule update --recursive --remote
```

> The submodules are pinned to mutually compatible versions. Switching branches or pulling arbitrarily inside submodules may break compatibility.

## Docker Images

Prebuilt images are published on Docker Hub via GitHub Actions:

- `psctoolkit/psctoolkit:latest` — built from the `master` branch (stable)
- `psctoolkit/psctoolkit:development` — built from the `development` branch

### Pull

```bash
# Stable
docker pull psctoolkit/psctoolkit:latest

# Development
docker pull psctoolkit/psctoolkit:development
```

### Run

```bash
# CPU-only container
docker run -it psctoolkit/psctoolkit:development /bin/bash

# GPU-enabled (requires NVIDIA Container Toolkit)
docker run --gpus all -it psctoolkit/psctoolkit:development /bin/bash
```

Inside the container, libraries are installed under:

- `/usr/local/psctoolkit/include` — headers and Fortran modules
- `/usr/local/psctoolkit/lib` — libraries

### What’s Inside the Image

Base: `nvidia/cuda:13.0.2-devel-ubuntu24.04` (Ubuntu 24.04 + CUDA 13).

Installed components:
- Build tools: gcc/g++, gfortran, cmake, git, OpenMPI
- Math: OpenBLAS, SuiteSparse (incl. UMFPACK, AMD), METIS
- Direct solvers: SuperLU, SuperLU_DIST, MUMPS
- PSCToolkit libraries compiled with:
  - PSBLAS: OpenMP enabled; CUDA enabled for compute capabilities 60, 70, 80, 89, 90
  - AMG4PSBLAS: support for SuperLU, SuperLU_DIST, MUMPS, UMFPACK

Source code is available at `/home/work/psctoolkit/` inside the container.

### Compile and Run Examples

```bash
# Fortran + PSBLAS
mpif90 -I/usr/local/psctoolkit/modules your_code.f90 \
  -L/usr/local/psctoolkit/lib -lpsb_linsolve -lpsb_prec -lpsb_util -lpsb_base -o your_program

# With AMG4PSBLAS
mpif90 -I/usr/local/psctoolkit/modules your_code.f90 \
  -L/usr/local/psctoolkit/lib -lamg_prec -lpsb_prec -lpsb_linsolve -lpsb_util -lpsb_base -o your_program

# With CUDA support
mpif90 -I/usr/local/psctoolkit/modules your_code.f90 \
  -L/usr/local/psctoolkit/lib -lpsb_ext -lpsb_cuda -lspgpu -lpsb_linsolve -lpsb_prec -lpsb_util -lpsb_base \
  -L/usr/local/cuda/lib64 -lcudart -lcublas -lcusparse -o your_program

# Run with MPI (example)
mpirun -np 4 ./your_program
```

### C Language Bindings

The C interfaces (Fortran/C interoperability via ISO_C_BINDING) are located in the cbind subdirectories:
- psblas3/cbind (PSBLAS)
- amg4psblas/cbind (AMG4PSBLAS)

They are built automatically with the normal build; no separate configure step is required.

After installation, the binding headers are placed under the main include prefix (e.g. /usr/local/psctoolkit/include). Header filenames follow the library naming used in the cbind directories (inspect that directory for the exact names; typical patterns group PSBLAS and AMG4PSBLAS symbols separately).

### GPU Runtime Prerequisites

- NVIDIA GPU (compute capability ≥ 6.0: Pascal, Volta, Turing, Ampere, Hopper)
- NVIDIA Container Toolkit installed on the host

Quick install (Ubuntu/Debian):

```bash
# Install NVIDIA Container Toolkit (see NVIDIA docs for details)
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
curl -fsSL https://nvidia.github.io/nvidia-docker/gpgkey | sudo gpg --dearmor -o /usr/share/keyrings/nvidia-container-toolkit-keyring.gpg
curl -fsSL https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | \
  sudo tee /etc/apt/sources.list.d/nvidia-docker.list
sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
sudo systemctl restart docker
```

Verify:

```bash
docker run --gpus all psctoolkit/psctoolkit:development nvidia-smi
```

## Build From Source (Development)

Requirements:
- C/C++ (gcc/g++), Fortran (gfortran)
- MPI (OpenMPI or MPICH)
- BLAS/LAPACK (OpenBLAS, MKL, etc.)
- Optional: CUDA Toolkit; SuiteSparse; METIS; SuperLU; SuperLU_DIST; MUMPS

### PSBLAS

```bash
cd psblas3
./configure --prefix=/usr/local/psctoolkit \
  --with-amdlibdir=/usr/lib/x86_64-linux-gnu/ \
  --with-amdincdir=/usr/include/suitesparse/ \
  --with-metislibdir=/usr/lib/x86_64-linux-gnu/ \
  --with-ipk=4 --with-lpk=4 \
  --enable-openmp

# CUDA (optional)
# add: --enable-cuda \
#      --with-cudadir=/usr/local/cuda \
#      --with-cudacc=60,70,80,89,90

make -j$(nproc)
make install
```

### AMG4PSBLAS

```bash
cd amg4psblas
./configure --prefix=/usr/local/psctoolkit \
  --with-psblas=/usr/local/psctoolkit \
  --with-superlulibdir=/usr/lib/x86_64-linux-gnu \
  --with-superluincdir=/usr/include/superlu/ \
  --with-superludistlibdir=/usr/lib/x86_64-linux-gnu \
  --with-superludistincdir=/usr/include/superlu-dist/ \
  --with-mumpslibdir=/usr/lib/x86_64-linux-gnu \
  --with-mumpsincdir=/usr/include \
  --with-umfpacklibdir=/usr/lib/x86_64-linux-gnu \
  --with-umfpackincdir=/usr/include/suitesparse/

make -j$(nproc)
make install
```

### SUNDIALS (optional)

See instructions inside the `sundials/` submodule.

## Continuous Integration

Images are built and pushed automatically by GitHub Actions:
- `latest` on pushes to `master` → Docker tag `psctoolkit/psctoolkit:latest`
- `development` on pushes to `development` → Docker tag `psctoolkit/psctoolkit:development`

## Links and Support

- Website: https://psctoolkit.github.io/
- GitHub: https://github.com/psctoolkit/psctoolkit
- Docker Hub: https://hub.docker.com/r/psctoolkit/psctoolkit
- Documentation: https://psctoolkit.github.io/libraries/
- Publications: https://psctoolkit.github.io/publication/
- Email: psctoolkit@na.iac.cnr.it

## Citation

If PSCToolkit helped your research, please cite the relevant libraries. See the [Publications page](https://psctoolkit.github.io/publication/).

## License

Each component retains its original license (generally BSD 3‑Clause). Refer to the respective repositories for details.
