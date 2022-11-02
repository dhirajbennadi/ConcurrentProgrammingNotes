# MSI Protocol

Simplest Broadcast Snoop Protocol

Cache Lines can be in one of the states:
1. Modified - There has been a write or is about to write
2. Shared - Read only access
3. Invalid

## Transaction 1
Core 1 wants to write on Line B (PrWr(B))
Since Line B is shared not write access. So raise an event in the bus - **Bus Up (Upgrade)**
Core 2 will invalidate Line B
Core 1 will update B and change the state to modifiable

![MSI Protocol](Images/MSI_Protocol.jpg)

#Events

## Events from Processor
* PrRd : Processor request to read a cache line
* PrWr:  Processor request to write a cache line

## Events on the Bus
* BusRd : Request the cache line
* BusRdX - I dont have the copy, I get the copy, invalidate others and then update it
  Request the cache line and invalidate the lines in the caches of other processors (because I am about to write)
* BusUp : Request the line s invalidated from other processors (because I am about to write and already have the line - I need to upgrade it)
* Flush - Request the line is written back to memory

# MESI
Modified, Exclusive, Shared, Invalid

# MESIF
Modified, Exclusive, Shared, Invalid, Forward

All cache lines have a home node

Steps for each transaction:
1. Requester broadcasts to all nodes using point-to-point network
2. All nodes respond with:
   1. Cache line state
   2. Data if available/required
   3. An indication if there is a conflicting transaction
3. Requester notifies the home node of its transaction and conflicts
4. Home node mediated conflict, sends cache-line if needed
5. If needed, the requester acks the node it got a copy from

# Directory Protocols
