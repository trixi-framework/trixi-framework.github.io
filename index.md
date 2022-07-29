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

* [**ReadVTK.jl**](https://github.com/trixi-framework/ReadVTK.jl)

  Julia package for reading VTK XML files

## Publications
The following publications make use of Trixi.jl or one of the other packages
listed above. Author names of Trixi's main developers are in *italics*.

* *Chan*, *Ranocha*, Rueda-Ramírez, *Gassner*, Warburton,
  **On the entropy projection and the robustness of high order entropy stable
  discontinuous Galerkin schemes for under-resolved flows**, 2022.\\
  [![arXiv:2203.10238](https://img.shields.io/badge/arXiv-2203.10238-yellow)](https://arxiv.org/abs/2203.10238)
  [![doi:10.3389/fphy.2022.898028](https://zenodo.org/badge/doi/10.3389/fphy.2022.898028.svg)](https://doi.org/10.3389/fphy.2022.898028)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-2022-robustness-entropy-projection)

* Lukáčová-Medvid’ová, Öffner,
  **Convergence of Discontinuous Galerkin Schemes for the Euler Equations
  via Dissipative Weak Solutions**, 2022.\\
  [![arXiv:2202.10043](https://img.shields.io/badge/arXiv-2202.10043-yellow)](https://arxiv.org/abs/2202.10043)

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

* *Schlottke-Lakemper*, *Winters*, *Ranocha*, *Gassner*,
  **A purely hyperbolic discontinuous Galerkin approach for self-gravitating
  gas dynamics**, Journal of Computational Physics (442), 110467, 2021.\\
  [![arXiv:2008.10593](https://img.shields.io/badge/arXiv-2008.10593-yellow)](https://arxiv.org/abs/2008.10593) 
  [![doi:10.1016/j.jcp.2021.110467](https://zenodo.org/badge/doi/10.1016/j.jcp.2021.110467.svg)](https://doi.org/10.1016/j.jcp.2021.110467)
  [![reproduce me!](https://img.shields.io/badge/reproduce-me!-brightgreen)](https://github.com/trixi-framework/paper-self-gravitating-gas-dynamics)


## Talks

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
[Michael Schlottke-Lakemper](https://www.hlrs.de/people/schlottke-lakemper)
(University of Stuttgart, Germany),
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

