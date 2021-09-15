@def title = "Trixi Framework"

# Trixi Framework

**Adaptive high-order numerical simulations of hyperbolic PDEs in Julia**

This page gives an overview of the different activities that, together,
constitute the Trixi framework on [GitHub](https://github.com/orgs/trixi-framework).

\toc


## Trixi
* [**Trixi.jl**](https://github.com/trixi-framework/Trixi.jl)

  Adaptive high-order numerical simulations of hyperbolic PDEs in Julia

* [**Trixi2Vtk.jl**](https://github.com/trixi-framework/Trixi2Vtk.jl)

  Convert output files generated with Trixi.jl to VTK

## Mesh generation
* [**HOHQMesh.jl**](https://github.com/trixi-framework/HOHQMesh.jl)

  HOHQMesh.jl is a Julia wrapper for the HOHQMesh mesh generator, which allows to
  produce curved quadrilateral and hexahedral meshes for high-order numerical
  simulations.

* [**HOHQMesh**](https://github.com/trixi-framework/HOHQMesh.jl)

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
* *Ranocha*, *Schlottke-Lakemper*, *Winters*, *Faulhaber*, *Chan*, *Gassner*,
  **Adaptive numerical simulations with Trixi.jl: A case study of Julia for
  scientific computing**, (submitted to JuliaCon 2021 proceedings), 2021.\\
  [arXiv:2108.06476](https://arxiv.org/abs/2108.06476) |
  [reproduce me!](https://github.com/trixi-framework/paper-2021-juliacon)

* *Ranocha*, *Gassner*, **Preventing pressure oscillations does not fix local
  linear stability issues of entropy-based split-form high-order schemes**,
  Commun. Appl. Math. Comput., 2021.\\
  [arXiv:2009.13139](https://arxiv.org/abs/2009.13139) |
  [doi:10.1007/s42967-021-00148-z](https://doi.org/10.1007/s42967-021-00148-z) |
  [reproduce me!](https://github.com/trixi-framework/paper-EC-KEP-PEP)

* *Schlottke-Lakemper*, *Winters*, *Ranocha*, *Gassner*,
  **A purely hyperbolic discontinuous Galerkin approach for self-gravitating
  gas dynamics**, Journal of Computational Physics (442), 110467, 2021.\\
  [arXiv:2008.10593](https://arxiv.org/abs/2008.10593) | 
  [doi:10.1016/j.jcp.2021.110467](https://doi.org/10.1016/j.jcp.2021.110467) |
  [reproduce me!](https://github.com/trixi-framework/paper-self-gravitating-gas-dynamics)


## Talks

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
  15th march 2021, GAMM Annual Meeting 2021

* **Julia for adaptive high-order multi-physics simulations**\\
  *Schlottke-Lakemper*\\
  27th January 2021, Numerical Analysis Seminar, Lund University\\
  [presentation & notebooks](https://github.com/trixi-framework/talk-2021-julia-adaptive-multi-physics-simulations)


## Get in touch!

There are a number of ways to reach out to us:
* Meet us on [Slack](https://join.slack.com/t/trixi-framework/shared_invite/zt-sgkc6ppw-6OXJqZAD5SPjBYqLd8MU~g)
* Create an issue in one of the repositories listed on this page
* Check out the websites of the [Trixi Authors](https://github.com/trixi-framework/Trixi.jl/blob/main/AUTHORS.md)
