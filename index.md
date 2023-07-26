@def title = "Trixi Framework"

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
listed above. Author names of Trixi's main developers are in *italics*.

* *Ranocha*, Giesselmann,
  **Stability of step size control based on a posteriori error estimates**, 2023.\\
  [![arXiv:2307.12677](https://img.shields.io/badge/arXiv-2307.12677-yellow)](https://arxiv.org/abs/2307.12677)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/ranocha/2023_RK_error_estimate)

* *Chan*, Shukla, Wu, Liu, Nalluri,
  **High order entropy stable schemes for the quasi-one-dimensional shallow
  water and compressible Euler equations**, 2023.\\
  [![arXiv:2306.12699](https://img.shields.io/badge/arXiv-2307.12089-yellow)](https://arxiv.org/abs/2307.12089)

* Ersing, *Winters*,
  **An entropy stable discontinuous Galerkin method for the two-layer
  shallow water equations on curvilinear meshes**, 2023.\\
  [![arXiv:2306.12699](https://img.shields.io/badge/arXiv-2306.12699-yellow)](https://arxiv.org/abs/2306.12699)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2023-es_two_layer)

* Rueda-Ramírez, Bolm, Kuzmin, *Gassner*,
  **Monolithic Convex Limiting for Legendre–Gauss–Lobatto Discontinuous Galerkin
  Spectral Element Methods**, 2023.\\
  [![arXiv:2303.00374](https://img.shields.io/badge/arXiv-2303.00374-yellow)](https://arxiv.org/abs/2303.00374)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/amrueda/paper_2023_MCL_LGL-DGSEM)

* *Ranocha*, *Winters*, Castro, Dalcin, *Schlottke-Lakemper*, *Gassner*, Parsani,
  **On error-based step size control for discontinuous Galerkin methods for
  compressible fluid dynamics**, 2023.\\
  [![arXiv:2209.07037](https://img.shields.io/badge/arXiv-2209.07037-yellow)](https://arxiv.org/abs/2209.07037)
  [![doi:10.1007/s42967-023-00264-y](https://zenodo.org/badge/doi/10.1007/s42967-023-00264-y.svg)](https://doi.org/10.1007/s42967-023-00264-y)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2022-stepsize_control)

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

* *Ranocha*, *Schlottke-Lakemper*, *Chan*, Rueda-Ramírez, *Winters*, Hindenlang, *Gassner*,
  **Efficient implementation of modern entropy stable and kinetic energy
  preserving discontinuous Galerkin methods for conservation laws**, (submitted), 2021.\\
  [![arXiv:2112.10517](https://img.shields.io/badge/arXiv-2112.10517-yellow)](https://arxiv.org/abs/2112.10517)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2021-EC_performance)

* Singh, Chandrashekar, **On a linear stability issue of split form schemes for
  compressible flows**, 2021.\\
  [![arXiv:2104.14941](https://img.shields.io/badge/arXiv-2104.14941-yellow)](https://arxiv.org/abs/2104.14941)

* *Ranocha*, *Gassner*, **Preventing pressure oscillations does not fix local
  linear stability issues of entropy-based split-form high-order schemes**,
  Communications on Applied Mathematics and Computation, 2021.\\
  [![arXiv:2009.13139](https://img.shields.io/badge/arXiv-2009.13139-yellow)](https://arxiv.org/abs/2009.13139)
  [![doi:10.1007/s42967-021-00148-z](https://zenodo.org/badge/doi/10.1007/s42967-021-00148-z.svg)](https://doi.org/10.1007/s42967-021-00148-z)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-EC-KEP-PEP)

* *Gassner*, Svärd, Hindenlang,
  **Stability Issues of Entropy-Stable and/or Split-form High-order Schemes**, 2022.\\
  [![arXiv:2007.09026](https://img.shields.io/badge/arXiv-2007.09026-yellow)](https://arxiv.org/abs/2007.09026)
  [![doi:10.1007/s10915-021-01720-8](https://zenodo.org/badge/doi/10.1007/s10915-021-01720-8.svg)](https://doi.org/10.1007/s10915-021-01720-8)

* *Schlottke-Lakemper*, *Winters*, *Ranocha*, *Gassner*,
  **A purely hyperbolic discontinuous Galerkin approach for self-gravitating
  gas dynamics**, Journal of Computational Physics (442), 110467, 2021.\\
  [![arXiv:2008.10593](https://img.shields.io/badge/arXiv-2008.10593-yellow)](https://arxiv.org/abs/2008.10593)
  [![doi:10.1016/j.jcp.2021.110467](https://zenodo.org/badge/doi/10.1016/j.jcp.2021.110467.svg)](https://doi.org/10.1016/j.jcp.2021.110467)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-self-gravitating-gas-dynamics)


## Talks

* **Scaling Trixi.jl to more than 10,000 cores using MPI**\\
  *Schlottke-Lakemper*, *Ranocha*\\
  27th July 2023, JuliaCon 2023, Cambridge, US

* **Research Software Engineering for Sustainable Scientific Computing**\\
  *Schlottke-Lakemper*\\
  30th January 2023, SSD Seminar Series, Aachen, Germany

* **Trixi.jl: High-Order Numerical Simulations of Conservation Laws in Julia**\\
  *Schlottke-Lakemper*\\
  19th January 2023, SNuBIC Seminar\\
  [tutorials & notebooks](https://github.com/trixi-framework/tutorial-2023-snubic)

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


## Authors
[Michael Schlottke-Lakemper](https://lakemper.eu)
(RWTH Aachen University, Germany),
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
<p align="center">
  <!-- BMBF -->
  <img align="middle" src="https://user-images.githubusercontent.com/3637659/231436391-b28a76a4-f027-40f9-bd28-14e3a2f3e16a.png" height="140"/>

  <!-- DFG -->
  <img align="middle" src="https://user-images.githubusercontent.com/3637659/231429826-31fd7e78-19b4-4bac-8d4c-d292c6570d93.jpg" height="120"/>

  <!-- SRC -->
  <img align="middle" src="https://user-images.githubusercontent.com/3637659/231433851-97dd9d3e-4f66-4a8c-a4ee-aca262a2e505.png" height="80"/>

  <!-- ERC -->
  <img align="middle" src="https://user-images.githubusercontent.com/3637659/231434670-64b3644f-9860-4139-a54d-13b538711e1b.jpg" height="140"/>

  <!-- NSF -->
  <img align="middle" src="https://user-images.githubusercontent.com/3637659/231508947-e3d119c8-bafb-472c-b6fb-18eda2009a55.jpg" height="100"/>
</p>
~~~

This project has benefited from funding by the Deutsche Forschungsgemeinschaft (DFG, German Research Foundation)
under Germany's Excellence Strategy EXC 2044-390685587, Mathematics Münster:
Dynamics-Geometry-Structure.

This project has benefited from funding by the Deutsche Forschungsgemeinschaft (DFG, German Research Foundation)
through the research unit FOR 5409 "Structure-Preserving Numerical Methods for Bulk- and
Interface Coupling of Heterogeneous Models (SNuBIC)" (project number 463312734).

This project has benefited from funding from the European Research Council through the
ERC Starting Grant "An Exascale aware and Un-crashable Space-Time-Adaptive
Discontinuous Spectral Element Solver for Non-Linear Conservation Laws" (Extreme),
ERC grant agreement no. 714487.

This project has benefited from funding from Vetenskapsrådet (VR, Swedish Research Council), Sweden
through the VR Starting Grant "Shallow water flows including sediment transport and morphodynamics",
VR grant agreement 2020-03642 VR.

This project has benefited from funding from the United States National Science Foundation under awards
DMS-1719818 and DMS-1943186.

This project has benefited from funding from the German Federal Ministry of
Education and Research through the project grant "Adaptive earth system modeling
with significantly reduced computation time for exascale supercomputers
(ADAPTEX)" (funding id: 16ME0668K).
