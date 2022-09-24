# Lecture 5

## OS Organization

### Process
A process is an executing instance of a program
A program is a passive entity until its launched

Processes do not share memory.

Each process consists of:
1. System resources that are allocated to it
2. A section of memory
3. Security Attributes (Such as its owner and set of permissions)
4. Processor State

### Thread
A thread is an executing instance of a sequential set of instructions
A single process can contain multiple threads, all of which are executing the same program

In Linux both process (single-thread) and threads are tasks

| Shared      | Not Shared |
| ----------- | ----------- |
| Global Variables      | Stacks       |
| Heap   | Registers        |
| -   | Stack Pointers        |
| -   | Return values        |

### Threads vs Hardware Threads

| Threads (Software)      | Hardware Threads |
| ----------- | ----------- |
| Linux Task (Software Construct)      | Hardware Execution Context ( Hardware Construct)       |
| -   | Core        |


#### Example of Hardware Threads

### Context Switching
A Context switch (also referred to as process switch or task switch) is the switching of the hardware thread from one process to another
Involves suspension and resuming of tasks

### Multi-Tasking
An OS in which multiple tasks can execute on a single core **seemingly simultaneously** and **without interfering** with each other
This is accomplished by Context Switching

### Scheduling
The OS **schedules** tasks to hardware threads (cores) to allow the task to make progress
The Code for this assignment is the **scheduler**
The algorithm for this assignment is the **Scheduling Policy**

Scheduling Policy varies according to:
1. Task Priority
2. Time Slice
3. IO Operation and other latency ops(e.g sleep)



