## Lecture 1

#### Race conditon example

Thread 1
`x = 3`

Thread 2
`y=x`

What are the possible values of y ? **Ans** = 0 , 3 or some random value

### What is Datarace?
Two threads access the same memory location and atleast one of them is a write (conflict)

### Why is parallel programming harder than sequential programming
1. Easy to write bugs (Dataraces)
2. Hard to find bugs (non-deterministic bugs. During the execution, the bugs may or may not occur)
3. Easy to have underperforming code (weird hardware issues)

### Parallel Processing
Multiple processors co-operate to process a related set of tasks

### Issues with Parallelism
1. ==Decomposition== : Dividing the problem into smaller components
2. Requires some form of communication of synchronization to manage the problem

== Parallel and Concurrent are the same terminologies ==

