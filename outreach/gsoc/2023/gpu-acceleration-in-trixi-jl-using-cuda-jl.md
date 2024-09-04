@def title = "GSoC 2023: GPU acceleration in Trixi.jl using CUDA.jl"
@def maxtoclevel=2

# GSoC 2023: GPU acceleration in Trixi.jl using CUDA.jl

 
- Mentee: [Huiyu Xie](https://github.com/huiyuxie)
- Mentors: [Hendrik Ranocha](https://github.com/ranocha) and [Michael Schlottke-Lakemper](https://github.com/sloede)
- Project Link: [https://github.com/huiyuxie/trixi\_cuda](https://github.com/czha/TrixiGPU.jl/tree/legacy)

The goal of this GSoC project was to accelerate Trixi.jl using GPUs.

**Table of contents**
\toc

## Project Overview
The project was focused on enhancing the [Trixi.jl](https://github.com/trixi-framework/Trixi.jl) numerical simulation framework, a prominent tool used for solving hyperbolic conservation laws within the Julia programming language. The primary aim was to introduce GPU support through [CUDA.jl](https://github.com/JuliaGPU/CUDA.jl) and essentially [CUDA](https://docs.nvidia.com/cuda) to accelerate the discretization processes used in solving partial differential equations (PDEs). This work was undertaken as part of the [Google Summer of Code 2023](https://summerofcode.withgoogle.com/) program, and the progress is summarized below:

- GPU Implementation: The GPU implementations were prototyped using CUDA, starting with 1D equation kernels and gradually extending to more complex 2D and 3D equation kernels. These developments formed the backbone of the Discontinuous Galerkin Collocation Spectral Element Method (DGSEM) in the framework.

- Performance Benchmarks: A series of benchmarks were conducted on the developed CUDA kernels to assess their efficiency. These benchmarks demonstrated substantial performance enhancements through a strategic integration of various factors including data transfer, kernel architecture, and method characteristics.

- Acceleration Extension: The GPU support was not limited to basic kernels but was extended to more intricate methods within the framework. This included integration with the DG solver that allows meshes with simplex elements (DGMulti) and other summation-by-parts (SBP) schemes like Finite Differences (FD) and Continuous Galerkin Spectral Element Method (CGSEM) through the DGMulti solver.

Please note that the third step was planned but remains incomplete due to time constraints and this step will be completed in the future if possible.

### How to Setup 
This project was entirely set up and tested on Amazon Web Services (AWS), and the instance type chosen was [`p3.2xlarge`](https://aws.amazon.com/ec2/instance-types/#Accelerated_Computing). Here is the link to the specific information of both [CPU and GPU](https://github.com/czha/TrixiGPU.jl/blob/legacy/docs/env_info.md) used for this project. Note that this project is reproducible by following the setup instructions provided link aboout [how to set up environment](https://github.com/czha/TrixiGPU.jl/blob/legacy/docs/project_setup.md). Also, for individuals without an Nvidia GPU but interested in experimenting with CUDA, here is a link detailing how to [set up a cloud GPU on AWS](https://github.com/czha/TrixiGPU.jl/blob/legacy/docs/aws_gpu_setup.md).


## Key Highlights
The overview of the project repository can be accessed through this [README.md](https://github.com/czha/TrixiGPU.jl/blob/legacy/README.md) file. Here is a detailed description of the highlights of this project.

### 1. Kernel Prototyping
Several function (kernel) naming rules were applied in the kernel prototyping process:
- The functions for GPU kernel parallel computing must end with `_kernel`
- The functions for calling the GPU kernels must begin with `cuda_`

These rules make the whole structure of the GPU code consistent with the original CPU code. Also, the implementation essentially revolves around three points: 
- Using custom kernel implementation instead of direct array (and matrix) operations through `CuArray` type
- Avoiding the use of conditional statement (like `if/else` branches) from the original CPU code
- Minimizing the number of GPU kernel calls within a certain function (like `cuda_volume_integral!`)

Based on these points, the work began with `dg_1d.jl`, and then extended to `dg_2d.jl` and `dg_3d.jl` under the `src/solvers/dgsem_tree` directory. The prototying mainly focused on the `rhs!` functions that are called in the `semidiscretize` process. Besides, it is worthwhile to mention some caveats in this GPU prototyping process:

- CUDA.jl does not support dynamic array access and the use of other dynamic types inside kernels ([Issue #6](https://github.com/huiyuxie/trixi_cuda/issues/6), [Issue #8](https://github.com/huiyuxie/trixi_cuda/issues/8), and [Issue #11](https://github.com/huiyuxie/trixi_cuda/issues/11)) 
- GPU parallel computing can run into race conditions ([Issue #5](https://github.com/huiyuxie/trixi_cuda/issues/5))
- The `Float32` type can be promoted to `Float64` type in the GPU computing process ([Issue #3](https://github.com/huiyuxie/trixi_cuda/issues/3) and [PR #1604](https://github.com/trixi-framework/Trixi.jl/pull/1604))

### 2. Kernel Configuration 
The GPU kernels were designed to be launched with the appropriate size of threads and blocks. The occupancy API `CUDA.launch_configuration` was used to create kernel configurator functions for 1D, 2D, and 3D kernels (i.e., `configurator_1d`, `configurator_2d`, and `configurator_3d`). 

Specifically, in kernel configurator functions, `CUDA.launch_configuration` would first return a suggested number of threads for the compiled but not yet run kernel, and then the number of blocks would be computed through dividing the corresponding array size by the number of threads. 

Thus, in the process of calling a GPU kernel, the kernel is first compiled and then run based on the returned launching data from the configurator. For example, it is common to see code like 
```Julia 
sample_kernel = @cuda launch = false sample_kernel!(arg1, arg2, arg3)
sample_kernel(arg1, arg2, arg3; configurator_1d(sample_kernel, size_arr)...) # Similar for `configurator_2d` and configurator_3d`
```
in kernel calling functions. In this way, the GPU kernels are configured and launched with the intention of achieving maximal occupancy (i.e., optimizing the utilization of GPU computing resources), potentially enhancing overall performance. However, it should be noted that the maximal occupancy cannot be reached in most cases.

Also, this method of kernel configuration may not be optimal, considering that it may not be applicable to different GPU versions. Given that
```Julia
julia> attribute(device(),CUDA.DEVICE_ATTRIBUTE_MAX_GRID_DIM_X) 2147483647 
julia> attribute(device(),CUDA.DEVICE_ATTRIBUTE_MAX_THREADS_PER_BLOCK) 1024
```
the kernel could be addressed in the crrent GPU version but may not in some other GPU versions (as different GPU gives different attribute data like `CUDA.DEVICE_ATTRIBUTE_MAX_GRID_DIM_X` and `CUDA.DEVICE_ATTRIBUTE_MAX_THREADS_PER_BLOCK`). So it was suggested to introduce the use of a stride loop for the current GPU kernels.

### 3. Kernel Optimization
Some work on kernel optimization has already been done during the process of kernel prototyping, such as avoiding the use of conditional branches and minimizing kernel calls. But the general work for kernel optimization has not yet been introdued (so this part is somewhat related to the future work). 

In summary, the kernel optimization should be based on kernel benchmarks and kernel profiling, and here are some factors that can be considered to improve performance:
- Data Transfer: The process of data transfer from CPU to GPU (and back) mainly occurs in the `rhs!` function when calling `semidiscretize`. Since `rhs!` is called multiple times during the process of time integration, it would be more efficient to complete the data transfer before calling the `rhs!` function.
- Stride Loop Tuning: The stride loop has not yet been introduced to the current GPU kernels. By applying stride loop tuning, the loop structure (i.e., stride length) can be modified to improve performance.
- Multi-GPU/Multi-Thread: The performance can be further improved if multiple GPUs or multiple threads are used.

## Performance Benchmarks
The performance benchmarks were conducted for both CPU and GPU on `Float64` and `Float32` types, respectively. The example files `elixir_advection_basic.jl`, `elixir_euler_ec.jl`, and `elixir_euler_source_terms.jl` were chosen from `tree_1d_dgsem`, `tree_2d_dgsem`, and `tree_3d_dgsem` under the `src/examples` directory. These examples were chosen because they are consistent in case of 1D, 2D, and 3D. Please note that all the examples have passed the accuracy tests and you can check them using this [link to examples](https://github.com/czha/TrixiGPU.jl/tree/legacy/src/examples).

The benchmark results were archived in another file and please use this [link to benchmarks](https://github.com/czha/TrixiGPU.jl/blob/legacy/docs/cuda_benchmark.md) to check them. Also note that the benchmarks were focuesd on the time integration part (i.e., on `OrdinaryDiffEq.solve`), see a benchmark exmaple below 
```Julia
# Run on CPU
@benchmark begin
    sol_cpu = OrdinaryDiffEq.solve(ode_cpu, BS3(), adaptive=false, dt=0.01;
        abstol=1.0e-6, reltol=1.0e-6, ode_default_options()...)
end

# Run on GPU
@benchmark begin
    sol_gpu = OrdinaryDiffEq.solve(ode_gpu, BS3(), adaptive=false, dt=0.01;
        abstol=1.0e-6, reltol=1.0e-6, ode_default_options()...)
end
```

From the benchmark results, it is shown that the GPU did not perform better than the CPU in general (but there were some exceptions). Furthermore, the `Memory estimate` and `allocs estimate` statistics from the GPU are much larger than those from the CPU. This is probably due to the design that all the data transfer happens in the `rhs!` function and thus the memory cost is extremely high when transferring data repeatedly between the CPU and GPU. 

In addition, the results indicate that the GPU performs better with 2D and 3D examples than with 1D examples. That is because GPUs are designed to handle a large number of parallel tasks, and 2D and 3D problems usually offer more parallelism compared to 1D problems. Essentially, the more data you can process simultaneously, the more efficiently you can utilize the GPU. 1D problems may not be complex enough to take full advantage of the GPU parallel processing capability.

## Future Work
The future work is listed here, ranging from specific to more general, from top to bottom:
1. Resolve [Issue #9](https://github.com/huiyuxie/trixi_cuda/issues/9) and [Issue #11](https://github.com/huiyuxie/trixi_cuda/issues/11) (and any upcoming issues) 
2. Complete the prototype for the remaining kernels (please refer to the Kernel to be Implemented from the [README.md](https://github.com/czha/TrixiGPU.jl/blob/legacy/README.md) file).
3. Update [PR #1604](https://github.com/trixi-framework/Trixi.jl/pull/1604) and make it merged into the repository
4. Optimize CUDA kernels to improve performance (especially data transfer, please refer to the kernel optimization part)
5. Prototype the GPU kernels for other DG solvers (for example, `DGMulti`, etc.)
6. Extend the single-GPU support to multi-GPU support (similarly, from single-thread to multi-thread)
7. Broaden compatibility to other GPU types beyond Nvidia (such as those from Apple, Intel, and AMD)

## Acknowledgements
I would like to express my gratitude to Google, the Julia community, and my mentors ([Hendrik Ranocha](https://github.com/ranocha), [Michael Schlottke-Lakemper](https://github.com/sloede), and [Jesse Chan](https://github.com/jlchan)) for this enriching experience during the Google Summer of Code 2023 program. This opportunity to participate, enhance my skills, and contribute to the advancement of Julia has been both challenging and rewarding.

Special thanks go to my GSoC mentor [Hendrik Ranocha](https://github.com/ranocha) (@ranocha) and another person from JuliaGPU [
Tim Besard](https://github.com/maleadt) (@maleadt, though he is not my mentor), whose guidance and support throughout our regular discussions have been instrumental in answering my questions and overcoming hurdles. The Julia community is incredibly welcoming and supportive, and I am proud to have been a part of this endeavor.

I am filled with appreciation for this fantastic summer of learning and development, and I look forward to seeing the continued growth of Julia and the contributions of its vibrant community.
