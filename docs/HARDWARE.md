# Computer Hardware
Any tangible part of the computer you can reach out and touch



## Processors

### Central Processing Unit (CPU)
- Computer's nerve center
- Performs a limited set of computational and logical operations
- Assembly language is used write programs that run on a CPU
- **Multitasking**: Can handle two or more tasks simultaneously
- **Multicore**: A core is essentially another "processing chip", nowadays each chip has multiple cores
- **Multiprocessing**: A situation where you have more than one CPU
  - Symmetric Multiprocessing (SMP): all chips are treated equally
  - Massively Parallel Processing (MPP): hundreds or thousands of processors, each with its own OS
- **Multiprogramming**: Outdated, used for mainframes, where multiple programs can run together, but only
  one is executing at a time, the others are not started or waiting for some resource
- **Multithreading**: multiple concurrent tasks within a single process
  - thread: self contained sequence of instructions that can be executed in parallel with other threads
  in a process
  - switching between threads incurs far less overhead
 
### Processing Types
- **Single State**: only one security level at a time
- **Multi State**: multiple states at one time

### Protection Rings
![Protection Rings](/images/protectionrings.png)
