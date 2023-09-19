# Central Processing Unit (CPU)
- Computer's nerve center
- Performs a limited set of computational and logical operations
- Assembly language is used write programs that run on a CPU

## Key Concepts
- **Multitasking**: Can handle two or more tasks (programs) simultaneously
- **Multicore**: A core is essentially another "processing chip", nowadays each chip has multiple cores
- **Multiprocessing**: A situation where you have more than one CPU
  - Symmetric Multiprocessing (SMP): all chips are treated equally
  - Massively Parallel Processing (MPP): hundreds or thousands of processors, each with its own OS
- **Multiprogramming**: Outdated, used for mainframes, where multiple programs can run together, but only
  one is executing at a time, the others are not started or waiting for some resource
- **Multithreading**: multiple concurrent tasks within a single process
  - **thread**: self contained sequence of instructions that can be executed in parallel with other threads
  in a process
  - switching between threads incurs far less overhead
- **Registers**: storage in the cpu
- Cache:
  - On the processor
  - L1, L2, L3, L4
