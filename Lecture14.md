# Lecture 14

# Coherence
A memory location is coherent if :
1. All threads see the same sequence of values at that location
2. By default, variables are not coherent


Almost all shared memory systems enforce cache lines
-> But the compiler doesnt guarantee this

Coherence is enforced by the cache-coherency protocol
-> Enforces the invariant **only one modifiable copy of the cache line in the system**

# No data race if read and writes are atomic

# Atomic Class
All stores to an atomic variable are write-atomic
All loads to an atomic variable are read-atomic

*All atomic variables are coherent* ???????

If a core wants to write to the cache line, it needs to invalidate read-only copies to ensure nobody reads stale data

# 4 Cs of Cache Misses
1. Cold
2. Capacity
3. Conflict
4. Contention: If two cores write to a cache line, it can ping-pong back and forth, causing misses at each write

