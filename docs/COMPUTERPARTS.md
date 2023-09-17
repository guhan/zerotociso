# Computer Parts
Any tangible part of the computer you can reach out and touch 

## Processors
### Central Processing Unit (CPU)
- Computer's nerve center
- Performs a limited set of computational and logical operations
- Assembly language is used write programs that run on a CPU
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
  
 
## Memory
### Read Only Memory (ROM)
Factory burned in data and cannot be changed
- **Programmable Read Only Memory (PROM)**: user can burn in chip data once
- **Eraseable Programmable Read Only Memory (EPROM)**: can be erased with UV light within a small window of time
- **Electronically Eraseable Programmable Read Only Memory (EEPROM)**:
  - (EE) Electronically Eraseable
  - entire chip must be erase
  - used for BIOS
- **Flash Memory**: can be electornically erased and rewritten, can be erased in blocks
- Secondary memory: magnetic, optical, or flash based media


### Random Access Memory (RAM)
Readable and writeable
- **Dynamic RAM (DRAM)**: uses capacitors that hold charges (0 or 1) and need to be refreshed periodically and is cheaper
- **Static RAM**: uses flip flops, switches which don't need to be refreshed
- Real:
- **Volatile**: once the power is shutoff the memory loses its data
- Considered to be the _primary_ storage of a computer

### Memory Addressing
- **Register addressing**: in CPU
- **Immediate addressing**: a holding spot for current data and then instuctions for next register
- **Direct addressing**: CPU is given actual address of memory location to access, address must be on same memory page
- **Indirect addressing**: the holding spot is a another memory location maybe on a different page
- **Base + Offset addressing**: base value is stored in one the CPU registers and an offset is given for the operand
- **Virtual Memory**: a pagefile that exists on a hard disk

## Basis Input/Output System (BIOS)
- OS independent primitives to start a computer and load the OS
- **phlashing**: installing a malicious version of BIOS

## Unified Extentisible Firmware Interface (UEFI)
- More advanced interface between hardware and software
- Supports legacy BIOS



