# Lecture 5

## OS Organization

### Process
A process is an executing instance of a program.
A program is a passive entity until its launched.

Processes do not share memory.

Each process consists of:
1. System resources that are allocated to it
2. A section of memory
3. Security Attributes (Such as its owner and set of permissions)
4. Processor State

### Thread
A thread is an executing instance of a sequential set of instructions
A single process can contain multiple threads, all of which are executing the same program

| Shared | Not Shared |
| Global Variables | Stacks |
| Heap | Registers |
| - | Stack Pointers |
| - | Return values |
