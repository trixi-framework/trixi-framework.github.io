# Final Report: GSoC '24 - Integrating Trixi.jl with Enzyme.jl

- Mentee: [Junyi Xu](https://github.com/junyixu).
- Mentors: [Michael Schlottke-Lakemper](https://github.com/sloede) and [Hendrik Ranocha](https://github.com/ranocha)
- Project Link: <https://github.com/junyixu/TrixiEnzyme.jl>

The goal of this GSoC project was to integrate [Trixi.jl](https://github.com/trixi-framework/Trixi.jl)
with compiler-based automatic differentiation via [Enzyme.jl](https://github.com/junyixu/TrixiEnzyme.jl).

## Project Overview

The core idea was to bring together two powerful Julia packages: Trixi.jl, which is this amazing CFD framework for conservation laws, and Enzyme.jl,
which does compiler-level automatic differentiation.
Why? Because this combination lets us do some really cool stuff - we can differentiate through complex numerical simulations faster,
handle both forward and reverse mode AD, and (this is the really neat part) deal with all the mutation and caching that
Trixi.jl uses to keep things running fast.
This work was undertaken as part of the [Google Summer of Code 2024 program](https://summerofcode.withgoogle.com/archive/2024/projects/MQRCkokT),
and the progress is summarized below:

- Forward Mode Implementation: Developed efficient forward mode automatic differentiation for DGSEM, with special attention to performance optimization and batching strategies.
- Reverse Mode Implementation: Created a complementary reverse mode implementation to provide users with workflow flexibility.
- GPU Support: Implemented initial GPU acceleration through CUDA.jl, including gradient computation for vanilla upwind schemes.

Please note that some aspects of the GPU integration remain in progress and will be completed in future work.

### How to Setup

#### CPU Version
To install the package, run the following command in the Julia REPL:

```julia
]  # enter Pkg mode
(@v1.10) pkg> add https://github.com/junyixu/TrixiEnzyme.jl.git
```

Then simply run the following command to use the package:

```julia
using TrixiEnzyme
```

#### GPU Version
For GPU support, you'll need additional setup steps. Please refer to the detailed setup guide from GSoC 2023's GPU implementation: [GPU Setup Guide](https://trixi-framework.github.io/outreach/gsoc/2023/gpu-acceleration-in-trixi-jl-using-cuda-jl/#how_to_setup).

## Key Highlights

### API Overview

Here are the **[main APIs](https://junyixu.github.io/TrixiEnzyme.jl/dev/api.html)** we developed. Some of them are:

#### CPU Differentiation
- `jacobian_enzyme_forward(semi::SemidiscretizationHyperbolic)`: Our workhorse for forward-mode AD. It computes Jacobians efficiently with automatic batch size selection.

- `jacobian_enzyme_reverse(semi)`: The reverse-mode implementation. For Jacobian computations, it serves as an alternative to forward mode with similar computational complexity. We implemented both modes to provide users with flexibility in their workflows.

- `pick_batchsize(x)`: A helper function that determines the optimal batch size for differentiation. It defaults to `min(total_size, 11)`, which we found balances memory usage and computational efficiency.

- `pick_batchsize(semi::SemidiscretizationHyperbolic)`: A specialized version for Trixi's semidiscretization structures that takes into account the specific characteristics of the problem.

#### GPU Differentiation 
- `grad_rhs_gpu!(du, du_shadow, u, u_shadow, ...)`: The GPU-accelerated gradient computation for the right-hand side of our PDEs. This function handles both the primal computation and its derivative on the GPU, using Enzyme's forward-mode AD capabilities.

- `compute_gradient_gpu(du, u, v, numerical_flux)`: A high-level interface for computing gradients on the GPU. It manages memory transfers and kernel launches automatically, making it easier to work with GPU-accelerated gradients.

- `grad_upwind_kernel_gpu!(du, du_shadow, u, u_shadow, ...)`: The corresponding gradient kernel for the upwind scheme, using Enzyme's forward-mode AD directly on GPU code.


## What We Achieved

One of our major accomplishments was implementing efficient automatic differentiation for DGSEM (Discontinuous Galerkin Spectral Element Method). We implemented both forward and reverse mode, each with its own strengths. Both modes work equally well for computing Jacobians, and our implementation lets users choose based on their specific workflow preferences.

Performance optimization was a big focus. We developed sophisticated batching strategies to handle Trixi's complex caching system efficiently. The automatic batch size selection turned out to be crucial for balancing memory usage and computation speed.

In the Enzyme4CUDA branch, we made significant progress on GPU support:
- Successfully implemented gradient computation for the vanilla upwind scheme on GPU
- Created new interfaces for TrixiCUDA to enable automatic differentiation
- Set up initial support for differentiating through CUDA kernels
- Developed GPU-specific memory management strategies to minimize data transfer overhead

However, we encountered some technical challenges with GPU integration. There's currently a circular dependency issue during precompilation when using CUDA.jl with Enzyme.jl - it affects Julia 1.10.7 and we're waiting for 1.10.8 to fix it. For now, we found that avoiding module wrappers for CUDA+Enzyme test code works as a workaround ([Issue #5](https://github.com/junyixu/TrixiEnzyme.jl/issues/5)).

## The Technical Nitty-Gritty

Here are some key technical insights we gained:

### Enzyme Integration
When working with Enzyme.autodiff, naming conventions are crucial. We prefix everything with `enzyme_` to ensure proper unpacking of `semi.cache` and correct interaction with Enzyme's APIs.

### Forward vs Reverse Mode Implementation
The core difference between forward and reverse mode in Enzyme.jl comes down to whether you set `dy` or `dx` as your onehot vector. However, there are important considerations:
- Reverse mode requires resetting `dx` between calculations to prevent accumulation
- Mutating functions must return `nothing` in reverse mode
- All intermediate values must be initialized to zero for correct reverse mode operation

### Performance Characteristics
We observed interesting performance patterns:
- For small caches (toy models), `jacobian_enzyme(semi)` outperforms ForwardDiff
- Larger DGSEM simulations face challenges due to cache sizes (`elements._surface_flux_values` and `cache.interfaces._u`)
- GPU performance heavily depends on problem size and memory transfer patterns

### GPU Implementation Details
Our GPU implementation required careful attention to:
- Memory management to minimize CPU-GPU transfers
- Kernel launch configurations for optimal occupancy
- Handling of derivative computations in CUDA kernels

## Future Work

- **GPU Integration**: Complete the prototype of Enzyme-based Jacobian computation for `rhs_gpu!` functions to match all TrixiCUDA.jl's functionalities
  - [X] Implement a GPU-accelerated gradient computation for the vanilla upwind scheme (To compute the full Jacobian, I need to devise an efficient method that fully utilizes the GPU to avoid performance issues. [Issue #4](https://github.com/junyixu/TrixiEnzyme.jl/issues/4#issuecomment-2585557874))
  - [X] Add interfaces for gradient computation for TrixiCUDA
  - [ ] Compute Jacobian for TrixiCUDA (Both Forward and Reverse)
- More benchmarking (WIP: [Issue #3](https://github.com/junyixu/jacobian4DG/issues/3))
  - Batch mode achieves better performance through reduced memory allocations compared to Enzyme's batching implementation
  - Computing the Jacobian using **reverse mode** automatic differentiation introduces additional overhead
- **Resolve [Issue #1](https://github.com/junyixu/TrixiEnzyme.jl/issues/1) and [Issue #2260](https://github.com/EnzymeAD/Enzyme.jl/issues/2260)**
  - To define a custom Enzyme rule for matrix `inv`?
- **Machine Learning Applications**: I'm particularly excited about extending the [Differentiating through a complete simulation](https://github.com/junyixu/TrixiEnzyme.jl/issues/5) section in Trixi's docs. Think time series as neural network inputs, k as outputs, with an energy-based loss function leveraging Enzyme's capabilities - could be really powerful for inverse problems!

## Acknowledgements
This project was made possible through the support and guidance of many incredible people in the Julia community. My mentors played crucial roles throughout the project - Michael Schlottke-Lakemper ([@sloede](https://github.com/sloede)) spent numerous video calls helping me debug issues and guided me in seeking help on Slack, while Hendrik Ranocha ([@ranocha](https://github.com/ranocha)) provided invaluable insights into type stability issues that significantly improved our implementation.

William Moses ([@wsmoses](https://github.com/wsmoses)) from the Enzyme.jl team deserves special thanks for his documentation examples and responsive support through both Slack discussions and GitHub issues. His work on Enzyme.jl has been foundational to this project.

I'm also grateful to Huiyu Xie ([@huiyuxie](https://github.com/huiyuxie)) for her technical support regarding GPU implementation. Her expertise with CUDA.jl integration proved invaluable as we worked to extend TrixiEnzyme's capabilities to GPU computing.

The project also received helpful feedback from Benedict from the Trixi Framework community.

The newer versions of Enzyme.jl have been super helpful with their improved error messages - makes debugging much more manageable!
