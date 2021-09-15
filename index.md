@def title = "Trixi Framework"

# Trixi Framework

**Adaptive high-order numerical simulations of hyperbolic PDEs in Julia**

This page gives an overview of the different repositories that, together,
constitute the Trixi framework on [GitHub](https://github.com/orgs/trixi-framework).

\toc


## Trixi
* [Trixi.jl](https://github.com/trixi-framework/Trixi.jl)

  Adaptive high-order numerical simulations of hyperbolic PDEs in Julia

* [Trixi2Vtk.jl](https://github.com/trixi-framework/Trixi2Vtk.jl)

  Convert output files generated with Trixi.jl to VTK

## Mesh generation
* [HOHQMesh.jl](https://github.com/trixi-framework/HOHQMesh.jl)

  HOHQMesh.jl is a wrapper for the HOHQMesh mesh generator, which allows to
  produce curved quadrilateral and hexahedral meshes for high-order numerical
  simulations.

* [HOHQMesh](https://github.com/trixi-framework/HOHQMesh.jl)

  High Order Hex-Quad Mesh (HOHQMesh) package to automatically generate
  all-quadrilateral meshes with high order boundary information.

## Wrapper packages for external tools
* [P4est.jl](https://github.com/trixi-framework/P4est.jl)

  P4est.jl is lightweight wrapper for the p4est C library.

* [KROME.jl](https://github.com/trixi-framework/KROME.jl)

  KROME.jl is a lightweight wrapper for KROME, a Fortran library for including
  chemistry and microphysics in astrophysics simulations.

## Publications
The following publications were created with the help of Trixi.jl. Where
available, links to reproducibility repositories are given, which allow to
reproduce the respective numerical results. Authors with names in *italics* are
part of the core development team.

* *Ranocha*, *Schlottke-Lakemper*, *Winters*, *Faulhaber*, *Chan*, *Gassner*,
  **Adaptive numerical simulations with Trixi.jl: A case study of Julia for
  scientific computing**, (submitted to JuliaCon 2021 proceedings), 2021.

  [arXiv:2108.06476](https://arxiv.org/abs/2108.06476) |
  [reproduce me!](https://github.com/trixi-framework/paper-2021-juliacon)

* *Ranocha*, *Gassner*, **Preventing pressure oscillations does not fix local
  linear stability issues of entropy-based split-form high-order schemes**,
  Commun. Appl. Math. Comput., 2021.

  [arXiv:2009.13139](https://arxiv.org/abs/2009.13139) |
  [doi:10.1007/s42967-021-00148-z](https://doi.org/10.1007/s42967-021-00148-z) |
  [reproduce me!](https://github.com/trixi-framework/paper-EC-KEP-PEP)

* *Schlottke-Lakemper*, *Winters*, *Ranocha*, *Gassner*,
  **A purely hyperbolic discontinuous Galerkin approach for self-gravitating
  gas dynamics**, Journal of Computational Physics (442), 110467, 2021.

  [arXiv:2008.10593](https://arxiv.org/abs/2008.10593) | 
  [doi:10.1016/j.jcp.2021.110467](https://doi.org/10.1016/j.jcp.2021.110467) |
  [reproduce me!](https://github.com/trixi-framework/paper-self-gravitating-gas-dynamics)


## Talks

* tbd.

## Get in touch!

* Refer to Trixi.jl as main page, Slack, authors
