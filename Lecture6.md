# Lecture 6

## Fork Join Model
1. **Fork** : Start a new process or thread
2. **Join** Wait for the process(es) to end

| Advantages      | Disadvantages |
| ----------- | ----------- |
| Straight Forward Decomposition      | Many threads in case of recursion calls       |
| Less overhead in thread swtiching than process switching   | Prohibits thread-thread communication, datarace if not protected by locks|

## Torn Writes
Writes that occur in series of steps

## Volatile
Avoids compiler optimization but does guarantee Torn Writes and Torn Reads

## Write Atomicity
A store is a write atomic if it cannot be torn.
By default all writes in C/C++ are **not write atomic**