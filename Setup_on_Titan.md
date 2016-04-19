## Introduction

This file includes some setup on Titan@ORNL.

### System Modules

Here is the list of modules I loaded on Titan:
```
[lei@titan-ext7 specfem3d_globe]$ module list
Currently Loaded Modulefiles:
  1) modules/3.2.10.3                      18) xpmem/0.1-2.0502.64982.5.3.gem
  2) eswrap/1.1.0-1.020200.1231.0          19) dvs/2.5_0.9.0-1.0502.2188.1.113.gem
  3) craype-network-gemini                 20) alps/5.2.4-2.0502.9774.31.12.gem
  4) craype/2.4.2                          21) rca/1.0.0-2.0502.60530.1.63.gem
  5) cray-mpich/7.2.4                      22) atp/1.8.3
  6) craype-interlagos                     23) PrgEnv-gnu/5.2.82
  7) lustredu/1.4                          24) cudatoolkit/7.0.28-1.0502.10280.4.1
  8) DefApps                               25) cray-netcdf-hdf5parallel/4.3.1
  9) site-aprun/1.0                        26) cray-hdf5-parallel/1.8.12
 10) aprun-usage/1.0                       27) szip/2.1
 11) altd/1.0                              28) mxml/2.9
 12) cray-libsci/13.1.0                    29) adios/1.8.0
 13) udreg/2.3.2-1.0502.10518.2.17.gem     30) git/2.3.2
 14) ugni/6.0-1.0502.10863.8.28.gem        31) cmake/2.8.10.2
 15) pmi/5.0.9-1.0000.10911.175.4.gem      32) boost/1.57.0
 16) dmapp/7.0.1-1.0502.11080.8.74.gem     33) gcc/4.8.2
 17) gni-headers/4.0-1.0502.10859.7.8.gem
```
I used `gcc/4.8.2` here. To load the same module, put these lines in your `~/.bashrc` file:
```
  module unload PrgEnv-cray
  module unload PrgEnv-pgi
  module unload PrgEnv-ifort
  module load PrgEnv-gnu

  module load cudatoolkit

  module unload gcc
  module load gcc/4.8.2
  module swap cray-libsci cray-libsci/13.1.0
  module swap cray-mpich cray-mpich/7.2.4
  #module load gcc/4.7.2
  module load cray-netcdf-hdf5parallel/4.3.1
  #module load cray-netcdf-hdf5parallel
  module load cray-hdf5-parallel/1.8.12
  module load szip/2.1
  module load mxml/2.9
  module load adios/1.8.0
  module load rca
  module load git/2.3.2

  module load cmake
  module load boost
```
 
### Some useful files

There are located on ORNL machine. To access it, please to directory `/ccs/home/lei/scripts/example`. Copy them to your `specfem3d_globe` source code home dir.

  1. `configure.titan.bash`: run this file first to configure the Makefile.
  2. `compile.titan.bash`: run this file to compile the code.
  3. `job_mesh.bash`: submit this file to job queue to run the mesher.
  4. `job_solver.bash`: sumit this file to job queue to run the solver.

### Example code:
I put my example run code at `/lustre/atlas/proj-shared/geo111/Wenjie/bm_specfem/specfem3d_globe` on ORNL machine.

