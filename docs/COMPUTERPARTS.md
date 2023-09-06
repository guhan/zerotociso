# Computer Parts
Any tangible part of the computer you can reach out and touch

## Terms 
- **Need to know**: consider not just privilege level but also relevance of the data/object to the role the subject plays. 

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
  - thread: self contained sequence of instructions that can be executed in parallel with other threads
  in a process
  - switching between threads incurs far less overhead
  - **Registers**: stroage in the cpu
  - 
 
### Processing Types
- **Single State**: only one security level at a time
- **Multi State**: multiple states at one time

### Processing modes
- **privileged, kernel, system, supervisor**:
  - full privileges
- **problem state, user**:
  - limited privileges
  - CPU only allows a subset of full instruction set

### Protection Rings
Organize code and components in an operating system. 

![Protection Rings](/images/protectionrings.png)

### Process States
The lifecycle of a process is illustrated below. 
- Supervisory state: when a process needs to perform a actoin that requires priviliges
![Process States](/images/Process-State-1.png)

### Security Modes
US Government has approved security modes for systems with classified information. 
- Dedicated:
  - Each user must have security clearance for all info
  - Each user must have access approval all info
  - Each user must have a valid need
- System High Mode:
  - Each user must have a valid security clearance
  - Each user must have access approval _for all info_ 
  - Must have need to know but _not for all information_
- Compartmented:
  - Each user must have security clearance for all info
  - Each user must have access approval _for just what they need_
  - Must have a need to know for all information they have access to
- **Compartmented mode workstations (CMWs)**: users with necessary clearances can process multiple compartments of data at the same time
  - Sensitivity label: what level an object must be protected
  - Information label: prevent data overclassification and add metadata
- Multilevel:
  - Some users do not have valid security for all info
  - each user must have access approval for all information they will access on the system
  - each user must ahve a valid need to know 

## Memory

### Read Only Memory (ROM)
Factory burned in data and cannot be changed
- **Programmable Read Only Memory (PROM)**: user can burn in chip data once
- **Eraseable Programmable Read Only Memory (EPROM)**: can be erased with UV light withing a small window of time
- **Electronically Eraseable Programmable Read Only Memory (EEPROM)**: electronically eraseable, entire chip must be erase, used for BIOS
- **Flash Memory**: can be electornically erased and rewritten, can be erased in blocks

### Random Access Memory (RAM)
Readable and writeable
- Dynamic RAM (DRAM): uses capacitors that hold charges (0 or 1) and need to be refreshed periodically and is cheaper
- Static RAM: uses flip flops, switches which don't need to be refreshed
- Real:
- Cache:
  - On the processor
  - L1, L2, L3, L4
- Volatile: once the power is shutoff the memory loses its data

### Memory Addressing
- Register addressing: in CPU
- Immediate addressing: a holding spot for current data and then instuctions for next register
- Direct addressing: CPU is given actual address of memory location to access, address must be on same memory page
- Indirect addressing: the holding spot is a another memory location maybe on a different page
- Base + Offset addressing: base value is stored in one the CPU registers and an offset is given for the operand

### Secondary memory
magnetic, optical, or flash based media
- Virtual Memory: a pagefile that exists on a hard disk

## Basis Input/Output System (BIOS)
- OS independent primitives to start a computer and load the OS
- **phlashing**: installing a malicious version of BIOS

## Unified Extentisible Firmware Interface (UEFI)
- More advanced interface between hardware and software
- Supports legacy BIOS

## Embedded System
An embedded system is a specialized computer system designed to perform specific tasks or functions within a larger system or product. Unlike general-purpose computers, which can run a variety of applications and software, embedded systems are dedicated to a particular purpose or set of tasks. They are often designed to be compact, efficient, reliable, and sometimes operate in real-time.

Key characteristics of embedded systems include:

- Dedicated Functionality: Embedded systems are designed to perform a specific function or set of functions. Examples include control systems in appliances, automotive systems, industrial automation, medical devices, consumer electronics, and more.
- Integration: Embedded systems are integrated into larger systems or products. They can be found in various devices and equipment that we use in our daily lives, from household appliances to complex machinery.
- Resource Constraints: Embedded systems often have resource limitations, such as limited processing power, memory, and storage. This requires careful optimization of software and hardware components.
- Real-time Operation: Many embedded systems operate in real-time, meaning they must respond to inputs and events within strict timing constraints. For instance, an anti-lock braking system in a car needs to respond instantly to changes in wheel rotation to ensure effective braking.
- Fixed or Custom Software: The software running on embedded systems is often purpose-built and tailored to the specific application. It may be written in assembly language or low-level languages for efficiency.
- Hardware-Software Integration: Hardware and software components in embedded systems are tightly integrated to achieve the desired functionality efficiently.
- Low Power Consumption: Embedded systems often need to be energy-efficient, as they might run on batteries or in environments where power consumption is a concern.
- Reliability and Stability: Many embedded systems are designed for critical applications where reliability and stability are paramount. For example, medical devices and aerospace systems must operate flawlessly to ensure safety.

