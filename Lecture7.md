# Lecture 7

Threads should have **exclusive access** to a memory location
Threads should have **mutual exclusion (Exclusive Access)**

## Locks
A **Lock** (latch, mutex) provides **mutual exclusion**

Locks work as ordering constraint

Ordering Constraint = mutex.unlock() -> mutex.lock()

Why does the order change at run-time?
1. OS Scheduling
2. To improve cache performance, once a lock is acquired it tries to require it
   
## Deadlock
Each process is waiting for another process to take action

## Coffman Conditions
The following conditions must occur simultaneously in order to enter a deadlock:
1. Mutual Exclusion : Tasks claim exclusive control of the resources (memory locations) they require
2. Wait For : Tasks hold resources already allocated to them while waiting for additional resources
3. No Premption : Resources cannot be forcibly removed from the tasks holding them until the resources are used to completion
4. Circular Wait: A circular chain of tasks exists, such that each task holds one or more resources that are being requested by the next task in chain

Mutual Exclusion and No Premption cannot be met if locks are being used