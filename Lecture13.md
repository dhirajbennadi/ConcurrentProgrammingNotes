# Lecture 13

## Orders and Data Race Conditions

## Order
An order is a definition of some set of elements

Order is a definition of the binary relation <= on a set S where:
1. Reflexivity : a <= a for all a in S
2. Anti-Symmetry : a <= b and b <= a implies a == b
3. Transitivity : a <= b and b <= c imples a <= c


### Total Order
Every Element is comparable 
A total order is an order where all objects can be compared using the <= that is:
Comparability: For any a,b in S, either a <= b or b <= a
Otherwise the order is partial

### Partial Order
Not every element is comparable
E.g Subset

In concurrent programming, partial orders represent **time**

**Critical Sections under a single lock form a total order at run-time**
**Critical Sections across multiple locks form a partial order at run-time**

### Sequenced Before Order
Appears to the user, the program executes in a particular order


