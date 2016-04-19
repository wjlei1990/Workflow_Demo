### Intro

Specfem3d globe is used for forward solver and adjoint solver.

Tutorial: I put a tutorial on [google drive](https://drive.google.com/file/d/0B7lccGZgvREBdUlXdnZReDV5SlU/view). You 
may download and view it.

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
##### Useful links:
 1. [Specfem workshop at Indiana University, 2015](https://github.com/wjlei1990/USArray2015_SPECFEM)
 2. [Specfem workshop at Princeton University, 2016](https://github.com/wjlei1990/ComputationalGeophysicsWorkshop)

