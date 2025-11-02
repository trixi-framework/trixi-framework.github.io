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

* [**TrixiShallowWater.jl**](https://github.com/trixi-framework/TrixiShallowWater.jl)

  High-order numerical simulations for shallow water applications

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

  Smesh.jl is a Julia wrapper package for smesh, a simple Fortran package for generating
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

* [**TrixiBottomTopography.jl**](https://github.com/trixi-framework/TrixiBottomTopography.jl)

  Approximating real world data for bottom topographies

## Downstream projects
There exist several downstream projects that build on the Trixi framework. Some of them are
listed below. If you have a project that you would like to see listed here, please
[open an issue](https://github.com/trixi-framework/trixi-framework.github.io/issues/new).

* [**BloodFlowTrixi.jl**](https://github.com/yolhan83/BloodFlowTrixi.jl)

  BloodFlowTrixi.jl implements one-dimensional (1D) and two-dimensional (2D) blood flow
  models for arterial circulation.

* [**TrixiCUDA.jl**](https://github.com/trixi-gpu/TrixiCUDA.jl)

  TrixiCUDA.jl offers CUDA acceleration for solving hyperbolic PDEs.

* [**TrixiLW.jl**](https://github.com/Arpit-Babbar/TrixiLW.jl)

  An implementation of the Lax-Wendroff flux reconstruction scheme for curvilinear meshes
  with adaptive mesh refinement and error based time stepping.

* [**TrixiShockTube.jl**](https://github.com/stillyslalom/TrixiShockTube.jl)

  A package for performing shock tube simulations with Trixi.jl.

## Publications
The following publications make use of Trixi.jl or one of the other packages
listed above. Author names of Trixi.jl's main developers are in *italics*.

### 2026
* Peyvan, Kumar, Karniadakis,
  **Fusion-DeepONet: A data-efficient neural operator for geometry-dependent hypersonic and supersonic flows**,
  Journal of Computational Physics (526) 114432, 2026.\\
  [![doi:10.1016/j.jcp.2025.114432](https://zenodo.org/badge/doi/10.1016/j.jcp.2025.114432.svg)](https://doi.org/10.1016/j.jcp.2025.114432)

* *Neher*, *Faulhaber*, *Berger*, Weißenfels, *Gassner*, *Schlottke-Lakemper*
  **Robust and efficient pre-processing techniques for particle-based methods including dynamic boundary generation**,
  Computer Physics Communications (318) 109898, 2026.\\
  [![arXiv:2506.21206](https://img.shields.io/badge/arXiv-2506.21206-yellow)](https://arxiv.org/abs/2506.21206)
  [![doi:10.1016/j.cpc.2025.109898](https://zenodo.org/badge/doi/10.1016/j.cpc.2025.109898.svg)](https://doi.org/10.1016/j.cpc.2025.109898)
  [![reproduce me!](https://zenodo.org/badge/DOI/10.5281/zenodo.15730554.svg)](https://doi.org/10.5281/zenodo.15730554)

### 2025
* Babbar, Chandrashekar,
  **Lax-Wendroff Flux Reconstruction for advection-diffusion equations with error-based time stepping**, 2025,\\
  Lecture Notes in Computational Science and Engineering (LNCSE,volume 142),
  Spectral and High-Order Methods for Partial Differential Equations ICOSAHOM 2023, 157–173.
  [![arXiv:2402.12669](https://img.shields.io/badge/arXiv-2402.12669-yellow)](https://arxiv.org/abs/2402.12669)
  [![doi:10.1007/978-3-031-76988-7_7](https://zenodo.org/badge/doi/10.1007/978-3-031-76988-7_7.svg)](https://doi.org/10.1007/978-3-031-76988-7_7)

* Sánchez-Ramírez, Giordano,
  **Extrae.jl: Julia bindings for the Extrae HPC Profiler**, 2025.\\
  [![arXiv:2509.10311](https://img.shields.io/badge/arXiv-2504.12087-yellow)](https://arxiv.org/pdf/2504.12087)

* Artiano, Knoth, Spichtinger, *Ranocha*,
  **Structure-preserving high-order methods for the compressible Euler equations in potential temperature formulation for atmospheric flows**, 2025.\\
  [![arXiv:2509.10311](https://img.shields.io/badge/arXiv-2509.10311-yellow)](https://arxiv.org/abs/2509.10311)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/MarcoArtiano/2025_structure_potential_temperature)

* Montoya, *Rueda-Ramírez*, *Gassner*,
  **Entropy-stable discontinuous spectral-element methods for the spherical shallow water equations in covariant form**, 2025.\\
  [![arXiv:2509.08790](https://img.shields.io/badge/arXiv-2509.08790-yellow)](https://arxiv.org/abs/2509.08790)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/tristanmontoya/paper-2025-spherical-shallow-water)

* Christner, *Chan*,
  **Entropy stable finite difference (ESFD) methods via entropy correction artificial viscosity (ECAV) and knapsack limiting (KL) techniques**, 2025.\\
  [![arXiv:2508.21226](https://img.shields.io/badge/arXiv-2508.21226-yellow)](https://arxiv.org/abs/2508.21226)

* Thein, *Ranocha*,
  **Computing Radially-Symmetric Solutions of the Ultra-Relativistic Euler Equations with Entropy-Stable Discontinuous Galerkin Methods**, 2025.\\
  [![arXiv:2508.21427](https://img.shields.io/badge/arXiv-2508.21427-yellow)](https://arxiv.org/abs/2508.21427)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/ranocha/2025_ultrarelativistic_euler)

* *Doehring*, *Ranocha*, Torrilhon,
  **Paired Explicit Relaxation Runge-Kutta Methods: Entropy-Conservative and Entropy-Stable High-Order Optimized Multirate Time Integration**, 2025.\\
  [![arXiv:2507.04991](https://img.shields.io/badge/arXiv-2507.04991-yellow)](https://arxiv.org/abs/2507.04991)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/DanielDoehring/paper-2025-perrk)

* Babbar, Churavy, *Schlottke-Lakemper*, *Ranocha*,
  **Automatic differentiation for Lax-Wendroff-type discretizations**, 2025.\\
  [![arXiv:2506.11719](https://img.shields.io/badge/arXiv-2506.11719-yellow)](https://arxiv.org/abs/2506.11719)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/Arpit-Babbar/2025_paper_lw_ad)

* Oblapenko, Torrilhon,
  **Entropy-conservative high-order methods for high-enthalpy flows**, 2025.\\
  [![arXiv:2403.16882](https://img.shields.io/badge/arXiv-2403.16882-yellow)](https://arxiv.org/abs/2403.16882)
  [![doi:10.1016/j.compfluid.2025.106640](https://zenodo.org/badge/doi/10.1016/j.compfluid.2025.106640.svg)](https://doi.org/10.1016/j.compfluid.2025.106640)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/knstmrd/paper-ec_trixi_inte)

* Song, Singh, Torrilhon, **Non-equilibrium flow simulations based on Grad-14 and Grad-17 moment equations for polytropic gasess**, 2025.\\
  [![doi:10.1063/5.0257491](https://zenodo.org/badge/doi/10.1063/5.0257491.svg)](https://doi.org/10.1063/5.0257491)

* Qu, Narayan, *Chan*, **Entropy stable reduced order modeling of nonlinear conservation laws using discontinuous Galerkin methods**, 2025.\\
  [![arXiv:2502.09381](https://img.shields.io/badge/arXiv-2502.09381-yellow)](https://arxiv.org/pdf/2502.09381)

* Glaubitz, *Ranocha*, *Winters*, *Schlottke-Lakemper*, Öffner, *Gassner*,
  **Generalized upwind summation-by-parts operators and their application to nodal discontinuous Galerkin methods**,
  Journal of Computational Physics (529) 113841, 2025.\\
  [![arXiv:2406.14557](https://img.shields.io/badge/arXiv-2406.14557-yellow)](https://arxiv.org/abs/2406.14557)
  [![doi:10.1016/j.jcp.2025.113841](https://zenodo.org/badge/doi/10.1016/j.jcp.2025.113841.svg)](https://doi.org/10.1016/j.jcp.2025.113841)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2024-generalized-upwind-sbp)

* *Ersing*, Goldberg, *Winters*,
  **Entropy stable hydrostatic reconstruction schemes for shallow water systems**,
  Journal of Computational Physics (527) 113802, 2025.\\
  [![arXiv:2406.14119](https://img.shields.io/badge/arXiv-2406.14119-yellow)](https://arxiv.org/abs/2406.14119)
  [![doi:10.1016/j.jcp.2025.113802](https://zenodo.org/badge/doi/10.1016/j.jcp.2025.113802.svg)](https://doi.org/10.1016/j.jcp.2025.113802)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/patrickersing/paper-2024-es_hydrostatic_reconstruction)

* Babbar, Chandrashekar,
  **Multi-Derivative Runge-Kutta Flux Reconstruction for Hyperbolic Conservation Laws**,
    Communications on Applied Mathematics and Computation, 2025.\\
  [![arXiv:2403.02141](https://img.shields.io/badge/arXiv-2403.02141-yellow)](https://arxiv.org/abs/2403.02141)
  [![doi:10.1007/s42967-024-00463-1](https://zenodo.org/badge/doi/10.1007/s42967-024-00463-1.svg)](https://doi.org/10.1007/s42967-024-00463-1)

* *Chan*
  **An artificial viscosity approach to high order entropy stable discontinuous Galerkin methods**, 2025.\\
  [![arXiv:2501.16529](https://img.shields.io/badge/arXiv-2501.16529-yellow)](https://arxiv.org/abs/2501.16529)
  [![doi:10.1016/j.jcp.2025.114380](https://zenodo.org/badge/doi/10.1016/j.jcp.2025.114380.svg)](https://doi.org/10.1016/j.jcp.2025.114380)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/jlchan/paper-artificial-viscosity-entropy-stable-2025)

* Neher, Faulhaber, Berger, *Gassner*, *Schlottke-Lakemper*
  **TrixiParticles.jl: Particle-based multiphysics simulation in Julia**,
  Journal of Open Source Software, 10(105), 7044, 2025.\\
  [![doi:10.21105/joss.07044](https://zenodo.org/badge/doi/10.21105/joss.07044.svg)](https://doi.org/10.21105/joss.07044)

* Babbar, Chandrashekar,
  **Lax-Wendroff Flux Reconstruction on adaptive curvilinear meshes with error based time stepping for hyperbolic conservation laws**,
  Journal of Computational Physics (522), 113622, 2025.\\
  [![arXiv:2402.11926](https://img.shields.io/badge/arXiv-2402.11926-yellow)](https://arxiv.org/abs/2402.11926)
  [![doi:10.1016/j.jcp.2024.113622](https://zenodo.org/badge/doi/10.1016/j.jcp.2024.113622.svg)](https://doi.org/10.1016/j.jcp.2024.113622)

* *Ranocha*, *Winters*, *Schlottke-Lakemper*, Öffner, Glaubitz, *Gassner*,
  **On the robustness of high-order upwind summation-by-parts methods for nonlinear conservation laws**,
  Journal of Computational Physics (520) 113471, 2025.\\
  [![arXiv:2311.13888](https://img.shields.io/badge/arXiv-2311.13888-yellow)](https://arxiv.org/abs/2311.13888)
  [![doi:10.1016/j.jcp.2024.113471](https://zenodo.org/badge/doi/10.1016/j.jcp.2024.113471.svg)](https://doi.org/10.1016/j.jcp.2024.113471)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2023-upwind)

### 2024
* Taylor, *Chan*,
  **An Entropy Stable High-Order Discontinuous Galerkin Method on Cut Meshes**, 2024.\\
  [![arXiv:2412.13002](https://img.shields.io/badge/arXiv-2412.13002-yellow)](https://arxiv.org/abs/2412.13002)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/cgt3/ES-CutDG)

* Kopriva, *Winters*, *Schlottke-Lakemper*, Schoonover, *Ranocha*,
  **HOHQMesh: An all quadrilateral/hexahedral unstructured mesh generator for high order elements**,
  Journal of Open Source Software, 9(104), 7476, 2024.\\
  [![doi:10.21105/joss.07476](https://zenodo.org/badge/doi/10.21105/joss.07476.svg)](https://doi.org/10.21105/joss.07476)

* Breit, Moyo, Öffner,
  **Discontinuous Galerkin methods for the complete stochastic Euler equations**, 2024.\\
  [![arXiv:2412.07613](https://img.shields.io/badge/arXiv-2412.07613-yellow)](https://arxiv.org/abs/2412.07613)

* Oblapenko, Tarnovskiy, Ertl, Torrilhon,
  **Entropy-stable fluxes for high-order Discontinuous Galerkin simulations of high-enthalpy flows**, 2024.\\
  [![arXiv:2411.13168](https://img.shields.io/badge/arXiv-2411.13168-yellow)](https://arxiv.org/abs/2411.13168)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/knstmrd/paper_ec_trixi_chem)

* Bach, *Rueda-Ramírez*, Kopriva, *Gassner*,
  **Mimetic Metrics for the DGSEM**, 2024.\\
  [![arXiv:2410.14502](https://img.shields.io/badge/arXiv-2410.14502-yellow)](https://arxiv.org/abs/2410.14502)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/amrueda/paper_2024_mimetic_metrics)

* *Doehring*, *Christmann*, *Schlottke-Lakemper*, *Gassner*, Torrilhon,
  **Fourth-Order Paired-Explicit Runge-Kutta Methods**, 2024.\\
  [![arXiv:2408.05470](https://img.shields.io/badge/arXiv-2408.05470-yellow)](https://arxiv.org/abs/2408.05470)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/DanielDoehring/paper-2024-perk4)

* Bender, Öffner,
  **Entropy-Conservative Discontinuous Galerkin Methods for the Shallow Water Equations with Uncertainty**, 2024.\\
  [![doi:10.1007/s42967-024-00369-y](https://zenodo.org/badge/doi/10.1007/s42967-024-00369-y.svg)](https://doi.org/10.1007/s42967-024-00369-y)

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

* *Lampert*, *Ranocha*,
  **Structure-Preserving Numerical Methods for Two Nonlinear Systems of Dispersive Wave Equations**, 2024.\\
  [![arXiv:2402.16669](https://img.shields.io/badge/arXiv-2402.16669-yellow)](https://arxiv.org/abs/2402.16669)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/JoshuaLampert/2024_dispersive_shallow_water)

* Rueda-Ramírez, Sikstel, *Gassner*,
  **An Entropy-Stable Discontinuous Galerkin Discretization of the Ideal Multi-Ion Magnetohydrodynamics System**,
  Journal of Computational Physics, Volume 523, 113655, 2024. \\
  [![arXiv:2402.14615](https://img.shields.io/badge/arXiv-2402.14615-yellow)](https://arxiv.org/abs/2402.14615)
  [![doi:10.1016/j.jcp.2024.113655](https://zenodo.org/badge/doi/10.1016/j.jcp.2024.113655.svg)](https://doi.org/10.1016/j.jcp.2024.113655)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/amrueda/paper_2024_multi-ion_mhd)

* *Doehring*, *Gassner*, Torrilhon,
  **Many-Stage Optimal Stabilized Runge-Kutta Methods for Hyperbolic Partial Differential Equations**,
  Journal of Scientific Computing, Volume 99, article number 28, 2024.\\
  [![arXiv:2402.12140](https://img.shields.io/badge/arXiv-2402.12140-yellow)](https://arxiv.org/abs/2402.12140)
  [![doi:10.1007/s10915-024-02478-5](https://zenodo.org/badge/doi/10.1007/s10915-024-02478-5.svg)](https://doi.org/10.1007/s10915-024-02478-5)

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

### 2025

* **A High-Order GPU-Accelerated Dynamical Core Based on Discontinuous Galerkin Methods**\\
  *Geihe*, *Schlottke-Lakemper*\\
  16th June 2025, PASC 2025, Brugg, Switzerland.

* **Sustainable research software for accessible high-performance computing**\\
  *Schlottke-Lakemper*\\
  27th May 2025, WSSP 2025, Stuttgart, Germany.

* **Using TRIXI.JL for Adaptively Coupling Multiphysics Problems**\\
  *Candelaresi*\\
  7th March 2025, SIAM CSE 2025, Fort Worth, Texas, USA.

* **Stabilized High-Order Multirate Time-Integration for Multiphysics via Paired-Explicit Runge-Kutta Methods**\\
  *Doehring*\\
  5th March 2025, SIAM CSE 2025, Fort Worth, Texas, USA.

* **Efficient Implementation of High Order Entropy Stable Methods for Computational Fluid Dynamics**\\
  *Chan*\\
  25th February 2025, Energy HPC Conference, Houston, Texas.

### 2024

* **Solving plasma problems using adaptive multiphysics coupling**\\
  *Candelaresi*\\
  4th December 2024, 19th MHD Days, Potsdam , Gremany

* **Modern discontinuous Galerkin methods for atmospheric physics**\\
  *Ranocha*\\
  8th October 2024, Mathematics of the Weather, Bad Orb, Germany

* **Adaptive mesh refinement in Earth-system modeling: first steps**\\
  *Geihe*\\
  8th October 2024, Mathematics of the Weather, Bad Orb, Germany

* **libtrixi: serving legacy codes in earth system modeling with fresh Julia CFD**\\
  *Geihe*\\
  12th July 2024, JuliaCon, Eindhoven, The Netherlands\\
  [slides & reproducibility repo](https://github.com/trixi-framework/talk-2024-juliacon-libtrixi)

* **Towards Aerodynamic Simulations in Julia with Trixi.jl**\\
  *Doehring*\\
  10th July 2024, JuliaCon, Eindhoven, The Netherlands

* **Non-intrusive Multirate Time-Integration for High-Order accurate Compressible Fluid Dynamics with Trixi.jl**\\
  *Doehring*\\
  2nd July 2024, PDESoft 2024, Cambridge, UK

* **Multirate Time-Integration based on Dynamic ODE Partitioning through Adaptively Refined Meshes for Convection-Dominated Flows**\\
  *Doehring*\\
  23rd July 2024, WCCM 2024, Vancouver, BC, CA

* **Adaptively Coupled Multiphysics Simulations with Trixi.jl**\\
  *Candelaresi*\\
  5th June 2024, PASC 2024, Zurich, Switzerland

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

### Google Summer of Code 2024
Trixi.jl participated in the Google Summer of Code 2024, establishing integration with [Enzyme.jl](https://github.com/EnzymeAD/Enzyme.jl) for automatic differentiation. This project was mentored by [Michael Schlottke-Lakemper](https://www.uni-augsburg.de/fakultaet/mntf/math/prof/hpsc) and [Hendrik Ranocha](https://ranocha.de/). [Here](outreach/gsoc/2024/integrating-trixi-jl-with-enzyme-jl) you can find the report from our contributor [Junyi Xu](https://github.com/junyixu).

### Google Summer of Code 2023
Trixi.jl participated in the Google Summer of Code 2023, marking its initial steps towards running on GPUs. This project was mentored by [Hendrik Ranocha](https://ranocha.de/) and [Michael Schlottke-Lakemper](https://www.uni-augsburg.de/fakultaet/mntf/math/prof/hpsc). [Here](outreach/gsoc/2023/gpu-acceleration-in-trixi-jl-using-cuda-jl) you can find the report from our contributor [Huiyu Xie](https://github.com/huiyuxie).


## Authors
[Michael Schlottke-Lakemper](https://www.uni-augsburg.de/fakultaet/mntf/math/prof/hpsc)
(University of Augsburg, Germany),
[Gregor Gassner](https://www.mi.uni-koeln.de/NumSim/gregor-gassner) (University of Cologne,
Germany),
[Hendrik Ranocha](https://ranocha.de/) (University of Hamburg, Germany),
[Andrew Winters](https://liu.se/en/employee/andwi94) (Linköping University, Sweden),
[Jesse Chan](https://jlchan.github.io/) (Rice University, US), and
Andrés Rueda-Ramírez (Polytechnic University of Madrid (UPM), Spain)
are the principal developers of
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
  Interface Coupling of Heterogeneous Models ([SNuBIC](https://www.snubic.io))" (project number 463312734).
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
through the following grants:
* Project grant "Adaptive earth system modeling with significantly reduced computation time for
  exascale supercomputers (ADAPTEX)" (funding id: 16ME0668K)
* Project grant "ICON-DG" of the WarmWorld initiative (funding id: 01LK2315B).

This project has benefited from funding by the
[Daimler und Benz Stiftung](https://www.daimler-benz-stiftung.de) (Daimler and Benz Foundation)
through grant no. 32-10/22.

This project has benefited from funding by the
[Klaus Tschira Stiftung](https://klaus-tschira-stiftung.de/) (Klaus Tschira Foundation)
through the project grant "High-Fidelity Laboratory for the Simulation of Celestial Bodies with their Space Environment (HiFiLab)" (funding id: 00.014.2021).

This project has benefited from funding by the Spanish
[Ministry of Science, Innovation, and Universities](https://www.ciencia.gob.es/en/)
through the "Beatriz Galindo" grant no. BG23-00062.

Trixi.jl is supported by [NumFOCUS](https://numfocus.org/) as an Affiliated Project.
