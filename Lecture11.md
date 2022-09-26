# Lecture 11

## Task Oriented / Dataflow Parallelism
1. Parallel Design Pattern
2. Assign Units of Work to Threads
3. User Level Scheduling
   
| Fork-Join      | Task-oriented |
| ----------- | ----------- |
| Prohibits thread-to-thread communication via globals and heap objects      | Decouples task from thread       |
| Explicitly joins threads back to the master thread   | No Master Thread        |
| Easier to conceptualize   | No explicit joins       |
| -   | Faster but hard to program         |

## Task Graph
Task Graph represents data dependencies

## Task Queue
Task Queues are used to assign (unit-of-work) tasks to threads

Each thread executes the following steps:
1. Gets a task and if dependencies are met runs it, creating new tasks
2. Inserts all new tasks into the queue
3. Repeats