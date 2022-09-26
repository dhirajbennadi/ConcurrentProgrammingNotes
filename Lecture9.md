# Lecture 9

## Lock
A Lock is an object which provides mutual exclusion. Only 1 thread can acquire a lock at any time. Other threads will be waiting for to acquire the lock in `lock()` method

Methods:
1. `lock()`
2. `unlock()`

If 2 threads hold different locks, they are not mutually exclusive.

```
/*Thread 1*/
for(int i = 0; i < 100; i++)
{
    l1.lock()
    cntr++;
    l1.unlock()
}

/*Thread 2*/
for(int i = 0; i < 100; i++)
{
    l2.lock()
    cntr++;
    l2.unlock()
}
```

## Locking Anamolies

### Starvation
Starvation is when a task is unable to acquire a requested resource , even while the rest of the system makes progress

### Priority Inversion
Priority Inversion is when a higher priority task gets **preempted/starved** by a lower priority task

### Livelock
Livelock is a state where multiple tasks continue to execute code but unable to make any progress

## Reader-Writer Locks
If there are 2 readers, its not a data-race as no thread is modifying the memory locations
If there are 2 writers, its a data-race condition

The **Writer** thread should acquire using the **lk.lock()**, while the **reader** threads should acquire the lock using **lk.lock_shared()**
lk.lock_shared is used only for reader threads 

RW are useful for periodic/rare writes