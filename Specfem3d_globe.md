### Intro

Specfem3d globe is used for forward solver and adjoint solver.

Tutorial: I put a tutorial on [google drive](https://drive.google.com/file/d/0B7lccGZgvREBdUlXdnZReDV5SlU/view). You 
may download and view it.

---
##### Forward solver
Use specfem to simulate forward wavefield and generate synthetic data.

1. Input:
  * source(`DATA/CMTSOLUTION`), which specifies the location and moment tensor the source.
  * station file(`DATA/STATIONS`), which specifies the location of receivers.
  * parameter file(`DATA/Par_file`), which specifies a lot of configuration stuff inside. If you want to generate sac output,
  please set `OUTPUT_SEISMOS_SAC_BINARY = .true.`. Then you would get sac files(*.sac) we used to use.

2. Launch the job:
  I have a simple doc [here](https://github.com/wjlei1990/ComputationalGeophysicsWorkshop/blob/master/How_to_run_specfem3d_globe.md).
So basically, you need to run the mesher to generate mesh and run the solver to generate synthetic waveforms. 

3. Output
You should be able to genrate the sac files after forward simulation. 

##### Adjoint solver
Use specfem to calculcate the kernels.

---
##### More powerful specfem
1. **ADIOS** as the model file format: we used to use binary file to save model file. Now we transferred it to ADIOS. To use this capalibity, you need:
  * load the adios module on Titan.
  * configure the Makefile by adding `--with-adios` flag.

2. **CUDA** support that boost the performance of the code. You need:
  * load the cuda library on Titan.
  * configure the Makefile by adding `--with-cuda=5`.

3. **ASDF** as thye output synthetic waveform file format: we used to use sac binary as the waveform file format. Now for faster processsing speed, we transfer to ASDF. It is a external library which is not on Titan yet, so you need to install the library in your home dir first. Check out the library [here](https://github.com/SeismicData/asdf-library)
  * configure the Makefile by adding `--with-asdf ASDF_LIBS="/path/to/asdf-library/libasdf.a"`

A example configure to use all the above features would be:
```
./configure --with-asdf ASDF_LIBS="/ccs/home/lei/bin/asdf-library/build/lib/libasdf.a" --with-adios --with-cuda=cuda5 --host=x86_64-unknown-linux-gnu MPIF90=$mpif90 F90=$f90 CC=$cc FLAGS_CHECK="$flags" FCFLAGS="" CFLAGS="$cflags" CUDA_INC="$CUDATOOLKIT_HOME/include" CUDA_LIB="$CUDATOOLKIT_HOME/lib64" MPI_INC="$CRAY_MPICH2_DIR/include"
```
---
##### Useful links:
 1. [Specfem workshop at Indiana University, 2015](https://github.com/wjlei1990/USArray2015_SPECFEM)
 2. [Specfem workshop at Princeton University, 2016](https://github.com/wjlei1990/ComputationalGeophysicsWorkshop)

