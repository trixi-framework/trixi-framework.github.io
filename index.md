@def title = "Trixi Framework"
@def maxtoclevel=2

# Trixi Framework

The Trixi framework is a collaborative scientific effort to provide
open source tools for adaptive high-order numerical simulations of
hyperbolic PDEs in Julia. Besides the core algorithms, the framework
also includes mesh and visualization tools. Moreover, it includes
utilities such as Julia wrappers of mature libraries written in
other programming languages.

This page gives an overview of the different activities that, together,
constitute the Trixi framework on [GitHub](https://github.com/orgs/trixi-framework).

\toc

## Adaptive high-order numerical simulations of hyperbolic PDEs
* [**Trixi.jl**](https://github.com/trixi-framework/Trixi.jl)

  Adaptive high-order numerical simulations of hyperbolic PDEs in Julia

* [**Trixi2Vtk.jl**](https://github.com/trixi-framework/Trixi2Vtk.jl)

  Convert output files generated with Trixi.jl to VTK

* [**libtrixi**](https://github.com/trixi-framework/libtrixi)

  Use [Trixi.jl](https://github.com/trixi-framework/Trixi.jl) from C/C++/Fortran

* [**SmartShockFinder.jl**](https://github.com/trixi-framework/SmartShockFinder.jl)

  Create troubled cell indicators for Trixi.jl using artificial neural networks

## Mesh generation
* [**HOHQMesh.jl**](https://github.com/trixi-framework/HOHQMesh.jl)

  HOHQMesh.jl is a Julia wrapper for the HOHQMesh mesh generator, which allows to
  produce curved quadrilateral and hexahedral meshes for high-order numerical
  simulations.

* [**HOHQMesh**](https://github.com/trixi-framework/HOHQMesh)

  High Order Hex-Quad Mesh (HOHQMesh) package to automatically generate
  all-quadrilateral meshes with high order boundary information.

* [**Smesh.jl**](https://github.com/trixi-framework/Smesh.jl)

  Smesh.jl is a Julia wrapper packagae for smesh, a simple Fortran package for generating
  and handling unstructured triangular and polygonal meshes.

* [**smesh**](https://github.com/trixi-framework/smesh)

  A simple Fortran package for generating and handling unstructured triangular and polygonal
  meshes.

## Particle-based multiphysics simulations

* [**TrixiParticles.jl**](https://github.com/trixi-framework/TrixiParticles.jl)

  Particle-based multiphysics simulations in Julia

* [**PointNeighbors.jl**](https://github.com/trixi-framework/PointNeighbors.jl)

  Efficient neighborhood search in point clouds with fixed search radius

## Additional packages
* [**P4est.jl**](https://github.com/trixi-framework/P4est.jl)

  P4est.jl is lightweight Julia wrapper for the p4est C library.

* [**KROME.jl**](https://github.com/trixi-framework/KROME.jl)

  KROME.jl is a lightweight Julia wrapper for KROME, a Fortran library for including
  chemistry and microphysics in astrophysics simulations.

* [**JuliaVTK/ReadVTK.jl**](https://github.com/JuliaVTK/ReadVTK.jl)

  Julia package for reading VTK XML files (maintained by the Trixi framework
  authors).

## Publications
The following publications make use of Trixi.jl or one of the other packages
listed above. Author names of Trixi.jl's main developers are in *italics*.

### 2025

* Babbar, Chandrashekar,
  **Lax-Wendroff Flux Reconstruction on adaptive curvilinear meshes with error based time stepping for hyperbolic conservation laws**,
  Journal of Computational Physics (522), 113622, 2025.\\
  [![arXiv:2402.11926](https://img.shields.io/badge/arXiv-2402.11926-yellow)](https://arxiv.org/abs/2402.11926)
  [![doi:10.1016/j.jcp.2024.113622](https://zenodo.org/badge/doi/10.1016/j.jcp.2024.113622.svg)](https://doi.org/10.1016/j.jcp.2024.113622)

* *Ranocha*, *Winters*, *Schlottke-Lakemper*, Öffner, Glaubitz, *Gassner*,
  **On the robustness of high-order upwind summation-by-parts methods for nonlinear conservation laws**, 2025.\\
  [![arXiv:2311.13888](https://img.shields.io/badge/arXiv-2311.13888-yellow)](https://arxiv.org/abs/2311.13888)
  [![doi:10.1016/j.jcp.2024.113471](https://zenodo.org/badge/doi/10.1016/j.jcp.2024.113471.svg)](https://doi.org/10.1016/j.jcp.2024.113471)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2023-upwind)

### 2024
* Oblapenko, Tarnovskiy, Ertl, Torrilhon,,
  **Entropy-stable fluxes for high-order Discontinuous Galerkin simulations of high-enthalpy flows**, 2024.\\
  [![arXiv:2410.14502](https://img.shields.io/badge/arXiv-2411.13168-yellow)](https://arxiv.org/abs/2411.13168)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/knstmrd/paper_ec_trixi_chem)

* Bach, *Rueda-Ramírez*, Kopriva, *Gassner*,
  **Mimetic Metrics for the DGSEM**, 2024.\\
  [![arXiv:2410.14502](https://img.shields.io/badge/arXiv-2410.14502-yellow)](https://arxiv.org/abs/2410.14502)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/amrueda/paper_2024_mimetic_metrics)

* *Doehring*, *Christmann*, *Schlottke-Lakemper*, *Gassner*, Torrilhon,
  **Fourth-Order Paired-Explicit Runge-Kutta Methods**, 2024.\\
  [![arXiv:2408.05470](https://img.shields.io/badge/arXiv-2408.05470-yellow)](https://arxiv.org/abs/2408.05470)

* *Ersing*, Goldberg, *Winters*,
  **Entropy stable hydrostatic reconstruction schemes for shallow water systems**, 2024.\\
  [![arXiv:2406.14119](https://img.shields.io/badge/arXiv-2406.14119-yellow)](https://arxiv.org/abs/2406.14119)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/patrickersing/paper-2024-es_hydrostatic_reconstruction)

* Glaubitz, *Ranocha*, *Winters*, *Schlottke-Lakemper*, Öffner, *Gassner*,
  **Generalized upwind summation-by-parts operators and their application to nodal discontinuous Galerkin methods**, 2024.\\
  [![arXiv:2406.14557](https://img.shields.io/badge/arXiv-2406.14557-yellow)](https://arxiv.org/abs/2406.14557)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2024-generalized-upwind-sbp)

* Bender, Öffner,
  **Entropy-Conservative Discontinuous Galerkin Methods for the Shallow Water Equations with Uncertainty**, 2024.\\
  [![doi:10.1007/s42967-024-00369-y](https://zenodo.org/badge/doi/10.1007/s42967-024-00369-y.svg)](https://doi.org/10.1007/s42967-024-00369-y)

* Oblapenko, Torrilhon,
  **Entropy-conservative high-order methods for high-enthalpy flows**, 2024.\\
  [![arXiv:2403.16882](https://img.shields.io/badge/arXiv-2403.16882-yellow)](https://arxiv.org/abs/2403.16882)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/knstmrd/paper-ec_trixi_inte)

* *Doehring*, *Schlottke-Lakemper*, *Gassner*, Torrilhon,
  **Multirate Time-Integration based on Dynamic ODE Partitioning through Adaptively Refined Meshes for Compressible Fluid Dynamics**, 2024.\\
  [![arXiv:2403.05144](https://img.shields.io/badge/arXiv-2403.05144-yellow)](https://arxiv.org/abs/2403.05144)
  [![doi:10.1016/j.jcp.2024.113223](https://zenodo.org/badge/doi/10.1016/j.jcp.2024.113223.svg)](https://doi.org/10.1016/j.jcp.2024.113223)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2024-amr-paired-rk)

* Babbar, Kenettinkara, Chandrashekar,
  **Admissibility preserving subcell limiter for Lax-Wendroff flux reconstruction**,
  Journal of Scientific Computing, Vol. 99, Issue 2, May 2024.\\
  [![arXiv:2305.10781](https://img.shields.io/badge/arXiv-2305.10781-yellow)](https://arxiv.org/abs/2305.10781)
  [![doi:10.1007/s10915-024-02482-9](https://zenodo.org/badge/doi/10.1007/s10915-024-02482-9.svg)](https://doi.org/10.1007/s10915-024-02482-9)

* Babbar, Chandrashekar,
  **Multi-Derivative Runge-Kutta Flux Reconstruction for Hyperbolic Conservation Laws**, 2024.\\
  [![arXiv:2403.02141](https://img.shields.io/badge/arXiv-2403.02141-yellow)](https://arxiv.org/abs/2403.02141)

* *Lampert*, *Ranocha*,
  **Structure-Preserving Numerical Methods for Two Nonlinear Systems of Dispersive Wave Equations**, 2024.\\
  [![arXiv:2402.16669](https://img.shields.io/badge/arXiv-2402.16669-yellow)](https://arxiv.org/abs/2402.16669)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/JoshuaLampert/2024_dispersive_shallow_water)

* Rueda-Ramírez, Sikstel, *Gassner*,
  **An Entropy-Stable Discontinuous Galerkin Discretization of the Ideal Multi-Ion Magnetohydrodynamics System**, 2024.\\
  [![arXiv:2402.14615](https://img.shields.io/badge/arXiv-2402.14615-yellow)](https://arxiv.org/abs/2402.14615)

* *Doehring*, *Gassner*, Torrilhon,
  **Many-Stage Optimal Stabilized Runge-Kutta Methods for Hyperbolic Partial Differential Equations**, 2024.\\
  [![arXiv:2402.12140](https://img.shields.io/badge/arXiv-2402.12140-yellow)](https://arxiv.org/abs/2402.12140)

* Babbar, Chandrashekar,
  **Lax-Wendroff Flux Reconstruction for advection-diffusion equations with error-based time stepping**, 2024.\\
  [![arXiv:2402.12669](https://img.shields.io/badge/arXiv-2402.12669-yellow)](https://arxiv.org/abs/2402.12669)

### 2023

* Ovadia, Oommen, Kahana, Peyvan, Turkel, Karniadakis,
  **Real-time Inference and Extrapolation via a Diffusion-inspired Temporal Transformer Operator (DiTTO)**, 2023.\\
  [![arXiv:2307.09072](https://img.shields.io/badge/arXiv-2307.09072-yellow)](https://arxiv.org/abs/2307.09072)

* *Ranocha*, Schütz,
  **Multiderivative time integration methods preserving nonlinear functionals via relaxation**, 2023.\\
  [![arXiv:2311.03883](https://img.shields.io/badge/arXiv-2311.03883-yellow)](https://arxiv.org/abs/2311.03883)
  [![doi:10.2140/camcos.2024.19.27](https://zenodo.org/badge/doi/10.2140/camcos.2024.19.27.svg)](https://doi.org/10.2140/camcos.2024.19.27)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/ranocha/2023_multiderivative_relaxation)

* *Ranocha*, Giesselmann,
  **Stability of step size control based on a posteriori error estimates**, 2023.\\
  [![arXiv:2307.12677](https://img.shields.io/badge/arXiv-2307.12677-yellow)](https://arxiv.org/abs/2307.12677)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/ranocha/2023_RK_error_estimate)

* *Chan*, Shukla, Wu, Liu, Nalluri,
  **High order entropy stable schemes for the quasi-one-dimensional shallow
  water and compressible Euler equations**, 2023.\\
  [![arXiv:2307.12089](https://img.shields.io/badge/arXiv-2307.12089-yellow)](https://arxiv.org/abs/2307.12089)

* Ersing, *Winters*,
  **An entropy stable discontinuous Galerkin method for the two-layer
  shallow water equations on curvilinear meshes**, 2023.\\
  [![arXiv:2306.12699](https://img.shields.io/badge/arXiv-2306.12699-yellow)](https://arxiv.org/abs/2306.12699)
  [![doi:10.1007/s10915-024-02451-2](https://zenodo.org/badge/doi/10.1007/s10915-024-02451-2.svg)](https://doi.org/10.1007/s10915-024-02451-2)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2023-es_two_layer)

* Rueda-Ramírez, Bolm, Kuzmin, *Gassner*,
  **Monolithic Convex Limiting for Legendre–Gauss–Lobatto Discontinuous Galerkin
  Spectral Element Methods**, 2023.\\
  [![arXiv:2303.00374](https://img.shields.io/badge/arXiv-2303.00374-yellow)](https://arxiv.org/abs/2303.00374)
  [![doi:10.1007/s42967-023-00321-6](https://zenodo.org/badge/doi/10.1007/s42967-023-00321-6.svg)](https://doi.org/10.1007/s42967-023-00321-6)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/amrueda/paper_2023_MCL_LGL-DGSEM)

* *Ranocha*,
  **A discontinuous Galerkin discretization of elliptic problems with improved
  convergence properties using summation by parts operators**, 2023.\\
  [![arXiv:2302.12488](https://img.shields.io/badge/arXiv-2302.12488-yellow)](https://arxiv.org/abs/2302.12488)
  [![doi:10.1016/j.jcp.2023.112367](https://zenodo.org/badge/doi/10.1016/j.jcp.2023.112367.svg)](https://doi.org/10.1016/j.jcp.2023.112367)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/ranocha/2023_elliptic)

* *Ranocha*, *Winters*, Castro, Dalcin, *Schlottke-Lakemper*, *Gassner*, Parsani,
  **On error-based step size control for discontinuous Galerkin methods for
  compressible fluid dynamics**, 2023.\\
  [![arXiv:2209.07037](https://img.shields.io/badge/arXiv-2209.07037-yellow)](https://arxiv.org/abs/2209.07037)
  [![doi:10.1007/s42967-023-00264-y](https://zenodo.org/badge/doi/10.1007/s42967-023-00264-y.svg)](https://doi.org/10.1007/s42967-023-00264-y)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2022-stepsize_control)

* *Ranocha*, *Schlottke-Lakemper*, *Chan*, Rueda-Ramírez, *Winters*, Hindenlang, *Gassner*,
  **Efficient implementation of modern entropy stable and kinetic energy
  preserving discontinuous Galerkin methods for conservation laws**, ACM Transactions on Mathematical Software, 2023.\\
  [![arXiv:2112.10517](https://img.shields.io/badge/arXiv-2112.10517-yellow)](https://arxiv.org/abs/2112.10517)
  [![doi:10.1145/3625559](https://zenodo.org/badge/doi/10.1145/3625559.svg)](https://doi.org/10.1145/3625559)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2021-EC_performance)

### 2022

* *Chan*, *Ranocha*, Rueda-Ramírez, *Gassner*, Warburton,
  **On the entropy projection and the robustness of high order entropy stable
  discontinuous Galerkin schemes for under-resolved flows**, 2022.\\
  [![arXiv:2203.10238](https://img.shields.io/badge/arXiv-2203.10238-yellow)](https://arxiv.org/abs/2203.10238)
  [![doi:10.3389/fphy.2022.898028](https://zenodo.org/badge/doi/10.3389/fphy.2022.898028.svg)](https://doi.org/10.3389/fphy.2022.898028)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2022-robustness-entropy-projection)

* Rueda-Ramírez, Pazner, *Gassner*,
  **Subcell limiting strategies for discontinuous Galerkin spectral element methods**, 2022.\\
  [![arXiv:2202.00576](https://img.shields.io/badge/arXiv-2202.00576-yellow)](https://arxiv.org/abs/2202.00576)
  [![doi:10.1016/j.compfluid.2022.105627](https://zenodo.org/badge/doi/10.1016/j.compfluid.2022.105627.svg)](https://doi.org/10.1016/j.compfluid.2022.105627)

* Lukáčová-Medvid’ová, Öffner,
  **Convergence of Discontinuous Galerkin Schemes for the Euler Equations
  via Dissipative Weak Solutions**, 2022.\\
  [![arXiv:2202.10043](https://img.shields.io/badge/arXiv-2202.10043-yellow)](https://arxiv.org/abs/2202.10043)
  [![doi:10.1016/j.amc.2022.127508](https://zenodo.org/badge/doi/10.1016/j.amc.2022.127508.svg)](https://doi.org/10.1016/j.amc.2022.127508)

* *Ranocha*,
  **A Note on Numerical Fluxes Conserving Harten's Entropies for the
  Compressible Euler Equations**, 2022.\\
  [![arXiv:2201.03946](https://img.shields.io/badge/arXiv-2201.03946-yellow)](https://arxiv.org/abs/2201.03946)
  [![doi:10.1016/j.jcp.2022.111236](https://zenodo.org/badge/doi/10.1016/j.jcp.2022.111236.svg)](https://doi.org/10.1016/j.jcp.2022.111236)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/ranocha/paper-2022-Euler_Harten_EC)

* *Ranocha*, *Schlottke-Lakemper*, *Winters*, *Faulhaber*, *Chan*, *Gassner*,
  **Adaptive numerical simulations with Trixi.jl: A case study of Julia for
  scientific computing**, JuliaCon Proceedings, 77, 2022.\\
  [![arXiv:2108.06476](https://img.shields.io/badge/arXiv-2108.06476-yellow)](https://arxiv.org/abs/2108.06476)
  [![doi:10.21105/jcon.00077](https://zenodo.org/badge/doi/10.21105/jcon.00077.svg)](https://doi.org/10.21105/jcon.00077)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2021-juliacon)

* *Gassner*, Svärd, Hindenlang,
  **Stability Issues of Entropy-Stable and/or Split-form High-order Schemes**, 2022.\\
  [![arXiv:2007.09026](https://img.shields.io/badge/arXiv-2007.09026-yellow)](https://arxiv.org/abs/2007.09026)
  [![doi:10.1007/s10915-021-01720-8](https://zenodo.org/badge/doi/10.1007/s10915-021-01720-8.svg)](https://doi.org/10.1007/s10915-021-01720-8)

### 2021

* Singh, Chandrashekar, **On a linear stability issue of split form schemes for
  compressible flows**, 2021.\\
  [![arXiv:2104.14941](https://img.shields.io/badge/arXiv-2104.14941-yellow)](https://arxiv.org/abs/2104.14941)

* *Ranocha*, *Gassner*, **Preventing pressure oscillations does not fix local
  linear stability issues of entropy-based split-form high-order schemes**,
  Communications on Applied Mathematics and Computation, 2021.\\
  [![arXiv:2009.13139](https://img.shields.io/badge/arXiv-2009.13139-yellow)](https://arxiv.org/abs/2009.13139)
  [![doi:10.1007/s42967-021-00148-z](https://zenodo.org/badge/doi/10.1007/s42967-021-00148-z.svg)](https://doi.org/10.1007/s42967-021-00148-z)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-EC-KEP-PEP)

* *Schlottke-Lakemper*, *Winters*, *Ranocha*, *Gassner*,
  **A purely hyperbolic discontinuous Galerkin approach for self-gravitating
  gas dynamics**, Journal of Computational Physics (442), 110467, 2021.\\
  [![arXiv:2008.10593](https://img.shields.io/badge/arXiv-2008.10593-yellow)](https://arxiv.org/abs/2008.10593)
  [![doi:10.1016/j.jcp.2021.110467](https://zenodo.org/badge/doi/10.1016/j.jcp.2021.110467.svg)](https://doi.org/10.1016/j.jcp.2021.110467)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-self-gravitating-gas-dynamics)


## Talks

### 2024
* **Non-intrusive Multirate Time-Integration for High-Order accurate Compressible Fluid Dynamics with Trixi.jl**\\
  *Doehring*\\
  2nd July 2024, PDESoft 2024, Cambridge, UK

### 2023

* **Challenges of sustainable research software engineering in Trixi.jl**\\
  *Schlottke-Lakemper*\\
  27th October 2023, MBD Colloquium, Aachen, Germany

* **Julia for scientific high-performance computing: opportunities and challenges**\\
  *Schlottke-Lakemper*\\
  6th October 2023, Ferrite.jl User & Developer Conference, Bochum, Germany

* **Scaling Trixi.jl to more than 10,000 cores using MPI**\\
  *Schlottke-Lakemper*, *Ranocha*\\
  27th July 2023, JuliaCon 2023, Cambridge, US

* **Massively Parallel Computational Fluid Dynamics with Julia and Trixi.jl**\\
  *Schlottke-Lakemper*\\
  28th June 2023, PASC Conference, Davos, Switzerland

* **Research Software Engineering for Sustainable Scientific Computing**\\
  *Schlottke-Lakemper*\\
  30th January 2023, SSD Seminar Series, Aachen, Germany

* **Trixi.jl: High-Order Numerical Simulations of Conservation Laws in Julia**\\
  *Schlottke-Lakemper*\\
  19th January 2023, SNuBIC Seminar\\
  [tutorials & notebooks](https://github.com/trixi-framework/tutorial-2023-snubic)

### 2022

* **Robust and efficient high-performance computational fluid dynamics enabled by modern numerical methods and technologies**\\
  *Ranocha*\\
  3rd November 2022,  MUSEN Colloquium, TU Braunschweig, Germany

* **Reproducibility as a service: collaborative scientific computing with Julia**\\
  *Schlottke-Lakemper*, *Ranocha*\\
  27th October 2022,  MaRDI Workshop for Scientific Computing, Münster, Germany

* **From Mesh Generation to Adaptive Simulation: A Journey in Julia**\\
  *Winters*\\
  27th July 2022, JuliaCon 2022\\
  [recorded talk on YouTube](https://youtu.be/_N4ozHr-t9E) | [presentation & code](https://github.com/trixi-framework/talk-2022-juliacon_toolchain)

* **Running Julia code in parallel with MPI: Lessons learned**\\
  *Christmann*, Neher, *Schlottke-Lakemper*\\
  26th July 2022, Julia for HPC Minisymposium, JuliaCon 2022\\
  [recorded talk on YouTube](https://youtu.be/fog1x9rs71Q?t=5172) | [presentation](https://github.com/JuliaParallel/juliacon-2022-julia-for-hpc-minisymposium)

* **Extensible Computational Fluid Dynamics in Julia with Trixi.jl**\\
  *Schlottke-Lakemper*, *Ranocha*, *Gassner*\\
  25th February 2022, SIAM Conference on Parallel Processing for Scientific Computing, Seattle, US

### 2021

* **Research software development with Julia**\\
  *Schlottke-Lakemper*, *Ranocha*\\
  27th September 2021, NFDI4Ing Conference 2021

* **Adaptive high-order numerical simulations with Trixi.jl**\\
  *Schlottke-Lakemper*, *Ranocha*\\
  9th September 2021, CliMA Seminar, California Institute of Technology

* **Adaptive and extendable numerical simulations with Trixi.jl**\\
  *Schlottke-Lakemper*, *Ranocha*\\
  30th July 2021, JuliaCon 2021\\
  [presentation & notebooks](https://github.com/trixi-framework/talk-2021-juliacon) |
  [recorded talk on YouTube](https://www.youtube.com/watch?v=hoViWRAhCBE)

* **Trixi.jl: High-Order Numerical Simulations of Hyperbolic PDEs in Julia**\\
  *Ranocha*, *Schlottke-Lakemper*, *Winters*\\
  14th July 2021, ICOSAHOM 2021\\
  [tutorials & notebooks](https://github.com/trixi-framework/tutorial-2021-icosahom)

* **Introduction to Julia and Trixi, a numerical simulation framework for hyperbolic PDEs**\\
  *Ranocha*\\
  27th April 2021, Applied Mathematics Seminar, University of Münster\\
  [presentation](https://github.com/trixi-framework/talk-2021-Introduction_to_Julia_and_Trixi)

* **Purely hyperbolic self-gravitating flow simulations in Julia**\\
  *Schlottke-Lakemper*, *Winters*, *Ranocha*, *Gassner*\\
  15th March 2021, GAMM Annual Meeting 2021

* **Julia for adaptive high-order multi-physics simulations**\\
  *Schlottke-Lakemper*\\
  27th January 2021, Numerical Analysis Seminar, Lund University\\
  [presentation & notebooks](https://github.com/trixi-framework/talk-2021-julia-adaptive-multi-physics-simulations)


## Outreach
### Google Summer of Code 2023
Trixi.jl participated in the Google Summer of Code 2023, marking its initial steps towards running on GPUs. This project was mentored by [Hendrik Ranocha](https://ranocha.de/) and [Michael Schlottke-Lakemper](https://www.uni-augsburg.de/fakultaet/mntf/math/prof/hpsc). [Here](outreach/gsoc/2023/gpu-acceleration-in-trixi-jl-using-cuda-jl) you can find the report from our contributor [Huiyu Xie](https://github.com/huiyuxie).


## Authors
[Michael Schlottke-Lakemper](https://www.uni-augsburg.de/fakultaet/mntf/math/prof/hpsc)
(University of Augsburg, Germany),
[Gregor Gassner](https://www.mi.uni-koeln.de/NumSim/gregor-gassner) (University of Cologne,
Germany),
[Hendrik Ranocha](https://ranocha.de/) (University of Hamburg, Germany),
[Andrew Winters](https://liu.se/en/employee/andwi94) (Linköping University, Sweden), and
[Jesse Chan](https://jlchan.github.io/) (Rice University, US) are the
principal developers of
[Trixi.jl](https://github.com/trixi-framework/Trixi.jl).
[David A. Kopriva](https://www.math.fsu.edu/~kopriva/) (Florida State University,
US) is the principal developer of [HOHQMesh](https://github.com/trixi-framework/HOHQMesh)
and [HOHQMesh.jl](https://github.com/trixi-framework/HOHQMesh.jl).
For a full list of authors, please check out the respective packages.


## Get in touch!

There are a number of ways to reach out to us:
* Meet us on [Slack](https://join.slack.com/t/trixi-framework/shared_invite/zt-sgkc6ppw-6OXJqZAD5SPjBYqLd8MU~g)
* Create an issue in one of the repositories listed on this page
* Get in touch with one of the [Trixi Authors](https://github.com/trixi-framework/Trixi.jl/blob/main/AUTHORS.md)

## Acknowledgments
~~~
<div style="width: 100%; text-align: center; font-size: 0;">
  <div><!--
    BMBF     --><img src="https://github.com/trixi-framework/Trixi.jl/assets/3637659/f59af636-3098-4be6-bf80-c6be3f17cbc6" style="height: 120px; width: auto"><!--
    DFG      --><img src="https://github.com/trixi-framework/Trixi.jl/assets/3637659/e67b9ed3-7699-466a-bdaf-2ba070a29a8e" style="height: 120px; width: auto"><!--
    -->
  </div>
  <div><!--
    SRC      --><img src="https://github.com/trixi-framework/Trixi.jl/assets/3637659/48f9da06-6f7a-4586-b23e-739bee3901c0" style="height: 120px; width: auto"><!--
    ERC      --><img src="https://github.com/trixi-framework/Trixi.jl/assets/3637659/9371e7e4-3491-4433-ac5f-b3bfb215f5ca" style="height: 120px; width: auto"><!--
    -->
  </div>
  <div><!--
    NSF      --><img src="https://github.com/trixi-framework/Trixi.jl/assets/3637659/5325103c-ae81-4747-b87c-c6e4a1b1d7a8" style="height: 120px; width: auto"><!--
    DUBS     --><img src="https://github.com/trixi-framework/Trixi.jl/assets/3637659/bb021e6e-42e6-4fe1-a414-c847402e1937" style="height: 120px; width: auto"><!--
    -->
  </div>
  <div><!--
    NumFOCUS --><img src="https://github.com/trixi-framework/Trixi.jl/assets/3637659/8496ac9e-b586-475f-adb7-69bcfc415185" style="height: 120px; width: auto"><!--
    -->
  </div>
</div>
~~~

This project has benefited from funding by the [Deutsche
Forschungsgemeinschaft](https://www.dfg.de/) (DFG, German Research Foundation)
through the following grants:
* Excellence Strategy EXC 2044-390685587, Mathematics Münster: Dynamics-Geometry-Structure.
* Research unit FOR 5409 "Structure-Preserving Numerical Methods for Bulk- and
  Interface Coupling of Heterogeneous Models (SNuBIC)" (project number 463312734).
* Individual grant no. 528753982.

This project has benefited from funding from the [European Research Council](https://erc.europa.eu)
through the
ERC Starting Grant "An Exascale aware and Un-crashable Space-Time-Adaptive
Discontinuous Spectral Element Solver for Non-Linear Conservation Laws" (Extreme),
ERC grant agreement no. 714487.

This project has benefited from funding from [Vetenskapsrådet](https://www.vr.se)
(VR, Swedish Research Council), Sweden
through the VR Starting Grant "Shallow water flows including sediment transport and morphodynamics",
VR grant agreement 2020-03642 VR.

This project has benefited from funding from the United States
[National Science Foundation](https://www.nsf.gov/) (NSF) under awards
DMS-1719818 and DMS-1943186.

This project has benefited from funding from the German
[Federal Ministry of Education and Research](https://www.bmbf.de) (BMBF)
through the project grant "Adaptive earth system modeling
with significantly reduced computation time for exascale supercomputers
(ADAPTEX)" (funding id: 16ME0668K).

This project has benefited from funding by the
[Daimler und Benz Stiftung](https://www.daimler-benz-stiftung.de) (Daimler and Benz Foundation)
through grant no. 32-10/22.

Trixi.jl is supported by [NumFOCUS](https://numfocus.org/) as an Affiliated Project.
