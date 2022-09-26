# Lecture 10

## Locking Patterns

### Single Global Lock
1. A single global lock to lock the whole data structure.
2. Doesnt mess up with partial orders, deadlock.
3. Minimal Concurrency as locking and unlocking is less often

### Hand-over-Hand Locking
Useful for pointer traversals

### 2 Phase Locking (2PL)
