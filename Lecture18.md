# Lecture 18

# Relaxed Consistency
Relaxed atomic accesses are ordered between the atomic accesses but amongst themselves they only have coherence and read/write atomicity

Eg:
```
/*Thread 1*/
x1.store(1, RELAXED);
x2.store(1, RELAXED);
flag.store(1, SEQCST);

/*Thread 2*/
while(flag.load(SEQCST) == 0)
{
    ;
}

y1 = x1.load(RELAXED);
y2 = x2.load(RELAXED);
done.store(1,SEQCST);

```

The stores to x1 and x2 can be reordered by the compiler

## Building Concurrency Primitives

### Test and Set Lock