# Lecture 12 

## Task Queues, Condition Variables

To implement Task Queues, a queue with a mutex is used.


```
class task_queue{
    queue<task> q;
    lock lk;

    void push(task val)
    {
        lk.lock();
        q.push(val);
        lk.unlock();
    }

    task pop()
    {
        while(true)
        {
            lk.lock();
            size_t sz = q.size();

            if(sz == 0)
            {
                lk.unlock();
            }
            else if(sz != 0)
            {
                task ret = q.back();
                q.pop();
                lk.unlock();
                return ret;
            }
        }
    }
}
```

The above code suffers from **starvation**
E.g If there are 20 threads executing pop, and only 1 thread is executing push, the push will be **starved**

## Condition Variables
1. A Condition Variable is a concurrency primitive that allows threads to efficiently wait for a condition to be true
2. Abstracts the state of some condition
3. A condition variable is always associated with a lock(which protects the condition) and is always modified under the lock
4. Together the condition variable and lock form a monitor

Methods:
1. wait() - wait until notified my condition is true
2. signal() - notify one waiter that the condition is true
3. broadcast() - notify all waiters that the condition is true

Waiting on the locks is **expensive**