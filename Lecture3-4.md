# Lecture 3
## Computer Organization

### MultiCore Processor

![Multicore](Images/MulticoreProcessor.jpg)

### Instruction Level Parallelism
![ILP](Images/InstructionLevelParallelism.jpg)

ILP is at **run time**
The CPU can execution the instructions in **parallel** and also **out of order**

**Threads are an example ILP**

### Simultaneous Multi-Threading (Hyper Threading)
Running two threads on the same core
Since the threads are never dependent on each other, stalling can be reduced. Threads are modelled in such a way so as to have independent code.

## Memory Hierarchy

![Memory System Hierarchy](Images/MemorySystemHierarchy.jpg)
The Hot data is usually kept close to the CPU (Ideally in the registers or in the caches)
This is determined by the OS

## Cache
Most architectures use **64 byte cache line**

### Coherent vs Non-coherent Cache
In Coherent sytems, only 1 modifiable copy of the cache-line at any time is maintained

### Inclusive vs Exclusive Caches
1. Inclusive : Contains all cache line that its descendents contain
2. Exclusive : Do not contain all cache line that its descendents contain

#### Cache Line
Smallest unit of memory that can migrate between DRAM and cache and between the caches