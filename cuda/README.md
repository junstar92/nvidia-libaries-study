# CUDA

## References

- [NVIDIA CUDA Documentation](https://docs.nvidia.com/cuda/index.html)
- [Github: CUDA C++ Core Libraries](https://github.com/NVIDIA/cccl/tree/main) (CCCL)
- [NVIDIA C++ Standard Library Documentation](https://nvidia.github.io/libcudacxx/)
- Professional CUDA C Programming By John Cheng, Max Grossman, Ty Mckercher
- [Thrust Documentation](https://nvidia.github.io/thrust/)
- [Thrust Doxygen Documentation](https://thrust.github.io/doc/)
- [Thrust Examples](https://github.com/NVIDIA/thrust/tree/master/examples)

## CUDA Documentations

> CUDA 12.1 문서를 기준으로 작성됨

### Programming Guide

- [Programming Guide Intro](/cuda/doc/01_programming_guide/01_intro.md)
- [Programming Model](/cuda/doc/01_programming_guide/02_programming_model.md)
- Programming Interface
  - [Compilation with NVCC](/cuda/doc/01_programming_guide/03-01_compilation_with_nvcc.md)
  - [CUDA Runtime](/cuda/doc/01_programming_guide/03-02_cuda_runtime.md)
    - [Device Memory](/cuda/doc/01_programming_guide/03-02-02_device_memory.md)
    - Device Memory L2 Access Management
    - [Shared Memory](/cuda/doc/01_programming_guide/03-02-04_shared_memory.md) (Example: Matrix Multiplication with Shared Memory)
    - [Page-Locked Host Memory](/cuda/doc/01_programming_guide/03-02-06_page_locked_host_memory.md)
    - [Asynchronous Concurrent Execution](/cuda/doc/01_programming_guide/03-02-08_asynchronous_concurrent_execution.md) (CUDA Streams)
      - Programmatic Dependent Launch and Synchronization
      - CUDA Graphs
      - [CUDA Events](/cuda/doc/01_programming_guide/03-02-08-08_cuda_events.md)
      - Synchronous Calls
    - Multi-Device System
    - [Unified Virtual Address Space](/cuda/doc/01_programming_guide/03-02-10_unified_virtual_address_space.md)
  - [Versioning and Compatibility](/cuda/doc/01_programming_guide/03-03_versioning_and_compatibility.md) (호환성 관련 내용)
- Hardware Implementation
- Performance Guidelines
  - [Maximize Utilization](/cuda/doc/01_programming_guide/05-02_maximize_utilization.md)
  - [Maximize Memory Throughput](/cuda/doc/01_programming_guide/05-03_maximize_memory_throughput.md)
  - [Maximize Instruction Throughput](/cuda/doc/01_programming_guide/05-04_maximize_instruction_throughput.md)
- C++ Language Extensions
  - [Function Execution Space Specifiers](/cuda/doc/01_programming_guide/07-01_function_execution_space_specifiers.md)
  - [Variable Memory Space Specifiers](/cuda/doc/01_programming_guide/07-02_variable_memory_space_specifiers.md)
  - [Built-in Vector Types](/cuda/doc/01_programming_guide/07-03_04_builtin_types_vars.md#built-in-vector-types)
  - [Built-in Variables](/cuda/doc/01_programming_guide/07-03_04_builtin_types_vars.md#built-in-variables)
  - [Memory Fence Functions](/cuda/doc/01_programming_guide/07-05_06_memory_fence_and_syn_func.md#memory-fence-functions) (Example: Single-Pass Reduction)
  - [Synchronization Functions](/cuda/doc/01_programming_guide/07-05_06_memory_fence_and_syn_func.md#synchronization-functions)
  - Texture Functions
  - Surface Functions
  - [Read-Only Data Cache Load Function](/cuda/doc/01_programming_guide/07-10_11_12_load_store_using_cache.md#read-only-data-cache-load-function)
  - [Load Functions Using Cache Hints](/cuda/doc/01_programming_guide/07-10_11_12_load_store_using_cache.md#load-functions-using-cache-hints)
  - [Store Functions Using Cache Hints](/cuda/doc/01_programming_guide/07-10_11_12_load_store_using_cache.md#store-functions-using-cache-hints)
  - [Atomic Functions](/cuda/doc/01_programming_guide/07-14_atomic_functions.md)
  - Alloca Function
  - [Warp Matrix Functions](/cuda/doc/01_programming_guide/07-24_warp_matrix_functions.md)
  - [Asynchronous Barrier](/cuda/doc/01_programming_guide/07-26_asynchronous_barrier.md)
  - [Asynchronous Data Copies](/cuda/doc/01_programming_guide/07-27_asynchronous_data_copies.md)
  - [Asynchronous Data Copies using `cuda::pipeline`](/cuda/doc/01_programming_guide/07-28_asynchronous_data_copies_using_cuda_pipeline.md)
  - Launch Bounds
  - #pragma unroll
- Cooperative Groups
- CUDA Dynamic Parallelism
- Virtual Memory Management

### Best Practices Guide

- [Performance Metrics](/cuda/doc/02_best_practice_guide/08_performance_metrics.md)
- [Memory Optimizations](/cuda/doc/02_best_practice_guide/09_memory_optimizations.md)
  - [Data Transfer Between Host and Device](/cuda/doc/02_best_practice_guide/09-01_data_transfer_between_host_and_device.md)
  - [Device Memory Spaces](/cuda/doc/02_best_practice_guide/09-02_device_memory_spaces.md)
- [Execution Configuration Optimizations](/cuda/doc/02_best_practice_guide/10_execution_configuration_optimizations.md)
- [Instruction Optimization](/cuda/doc/02_best_practice_guide/11_instruction_optimization.md)
- [Control Flow](/cuda/doc/02_best_practice_guide/12_control_flow.md)
- [Understanding the Programming Environment](/cuda/doc/02_best_practice_guide/14_understanding_the_programming_environment.md)
- [CUDA Compatibility Developer's Guide](/cuda/doc/02_best_practice_guide/15_cuda_compatibility_developers_guide.md)
- [Preparing for Deployment](/cuda/doc/02_best_practice_guide/16_preparing_for_deployment.md)

### Thrust

**Thrust**는 STL을 기반으로 CUDA용 C++ 템플릿 라이브러리이다. Thrust를 사용하면 CUDA C와 완벽하게 상호 호환이 가능하면서 최소한의 프로그래밍으로 고성능의 병렬 처리를 구현할 수 있다고 한다.

이 라이브러리에는 복잡하게 구현된 parallel scan, sort, reduce 등의 다양한 기능을 제공하는데, 고수준의 추상화를 통해 thrust가 가장 효율이 좋은 구현을 자동으로 선택한다. 생산성이 중요한 프로토타입뿐만 아니라 견고함과 절대적인 성능이 중요한 어플리케이션에서 활용할 수 있다고 한다.

- [Vectors](/cuda/doc/21_thrust/02_vectors.md)
- [Algorithms](/cuda/doc/21_thrust/03_altorithms.md)
- Fancy Iterators

## Study

- Basic
  - [Heterogeneous Computing](/cuda/study/01_heterogeneous_computing.md)
  - [CUDA Programming Model](/cuda/study/02_cuda_programming_model.md) (Example: Vector Addition)
  - [Organizing Parallel Threads](/cuda/study/03_organizing_parallel_threads.md) (Example: Matrix Addition)
  - [Device Query](/cuda/study/04_device_query.md)
  - [CUDA Execution Model](/cuda/study/05_cuda_execution_model.md) (GPU Architecture Overview)
  - [Understanding Warp Execution and Warp Divergence](/cuda/study/06_understanding_warp_execution.md)
  - [Avoiding Branch Divergence](/cuda/study/07_avoiding_branch_divergence.md) (Example: Sum Reduction)
  - [Unrolling Loops](/cuda/study/08_unrolling_loops.md) (Example: Sum Reduction)
  - [CUDA Memory Model](/cuda/study/09_cuda_memory_model.md) (CUDA Memory Types Overview)
  - [Memory Management](/cuda/study/10_memory_management.md) (Pinned Memory / Zero-copy Memory / UVA / Unified Memory)
    - [Example: Matrix Addition with Unified Memory](/cuda/study/10-1_matrix_addition_with_unified_memory.md)
  - [Global Memory Access Patterns](/cuda/study/11_memory_access_patterns.md)
    - [Example: Matrix Transpose](/cuda/study/11-1_matrix_transpose_problem.md)
  - [Warp Shuffle Instruction](/cuda/study/16_warp_shuffle.md) (Example: Sum Reduction with Warp Shuffle Instruction)
  - [Precision Issues of Floating-Point Number in CUDA](/cuda/study/17_precision_issues_in_cuda.md)
  - [Driver APIs와 Runtime APIs의 차이점](/cuda/study/18_difference_between_the_driver_and_runtime_apis.md)
  - [Runtime API 동기화 동작 분석](/cuda/study/19_api_synchronization_behavior.md)
  
- Shared Memory
  - [Introducing CUDA Shared Memory](/cuda/study/12_shared_memory.md) (Shared Memory Bank / Synchronization / Volatile Qualifier)
  - [Layout of Shared Memory](/cuda/study/12-1_data_layout_of_shared_memory.md) (Square & Rectangular Shared Memory)
  - [Reducing Global Memory Access](/cuda/study/12-2_reducing_global_memory_access.md) (Example: Sum Reduction with Shared Memory)
  - [Coalescing Global Memory Accesses](/cuda/study/12-3_coalescing_global_memory_accesses.md) (Example: Matrix Transpose with Shared Memory)
  
- Constant Memory
  - [Constant Memory and Read-Only Cache](/cuda/study/13_constant_memory.md)

- CUDA Stream
  - [Introducing CUDA Streams](/cuda/study/14_introducing_cuda_streams.md) (+ False Dependency, Hyper-Q)
  - [Concurrent Kernel Execution](/cuda/study/14-1_concurrent_kernel_execution.md)
  - [Overlapping Kernel Execution and Data Transfer](/cuda/study/14-2_overlapping_kernel_execution_and_data_transfer.md)
  - [Stream Callback](/cuda/study/14-3_stream_callback.md)
  - [Stream 동기화 동작 분석](/cuda/study/20_stream_synchronization_behavior.md)

- CUDA Event
  - [Introducing CUDA Events](/cuda/study/15_introducing_cuda_event.md)

- Optimization Techniques
  - [Register Cache: A Virtual Caching Layer for Threads in a Single Warp](/cuda/study/26_register_cache.md)
  - [Threadblock Swizzling for Locality-Friendly CTA Identifiers](/cuda/study/27_threadblock_swizzling.md)

- Tensor Cores
  - [Overview of Tensor Cores](/cuda/study/21_overview_of_tensor_cores.md) (using `wmma`)
  - [A Layout of WMMA](/cuda/study/22_a_layout_of_wmma.md)

- Asynchronous Barrier
  - [Simple Two Vector Normalization](/cuda/study/25_simple_normalize_vector.md)

- Matrix Multiplication Optimization
  - [Optimize a Matrix Multiplication Kernel (SGEMM)](/cuda/study/23_optimizing_a_matmul_kernel.md)
  - [Efficient Matrix Multiplication in CUDA](/cuda/study/24_efficient_gemm_in_cuda.md) (for CUDA Cores)
  - Matrix Multiplication Using Asynchronous Copy from Global Memory to Shared Memory

- PTX (Parllel Thread eXcution)
  - [Warp-level matrix load instruction (ldmatrix)](/cuda/study/28_ldmatrix.md)
  - [Warp-level matrix multiply-accumulation (mma.m16n8k16)](/cuda/study/29_mma_m16n8k16_fp16.md)