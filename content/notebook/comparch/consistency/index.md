---
title: Consistency
---
> [!def] **Definition** (Memory Consistency v1)
> A definition for shared memory correctness in a multicore system.

As exemplified by this [[Memory Reordering Example|memory reordering example]], modern processors might reorder memory accesses. 

Reordering is done for performance reasons.

1. **Store-store reordering.** e.g. a non-FIFO write buffer
2. **Load-load reordering.** e.g. simply due to out-of-order execution
3. **Load-store / store-load reordering.** e.g. in-order execution + FIFO write buffer
	* Store might execute first but not make it to memory (still in the FIFO) until after the load finishes

Correctness is maintained so long as the programmer understands how their program will behave under the given memory model.

> [!def] **Definition** (Memory Consistency Model v1)
> A specification of the allowed behavior of multithreaded programs executing with shared memory.

A memory consistency model partitions all possible executions into those that obey the model and those that do not.

Thus, there can be **multiple** correct behaviors.

> [!def] **Definition** (Memory Consistency Model v2)
> Defines the set of legal observable orders of memory operations during an execution.

Some helpful terms to define before diving into memory models:
1. **Total ordering.** All elements in a set with total ordering can be compared to each other and have some sort of relation (greater, less, equal).
2. **Program order.** A per-core total order that captures the order in which each core logically executed memory operations.
3. **Memory order.** A total order on the memory operations of all cores (combines and orders the program orders of all cores).

To help further formalize the definitions of different consistency models, the following notation helps:[^1]
- $\mathrm{op1} <_m \mathrm{op2}$ means that $\mathrm{op1}$ precedes $\mathrm{op2}$ in memory order
- $\mathrm{op1} <_p \mathrm{op2}$ means that $\mathrm{op1}$ precedes $\mathrm{op2}$ in program order

There are many memory consistency models:
1. [[Sequential Consistency|Sequential consistency]]
2. [[Total Store Order|Total store order]]

[^1]: Hill 2011, A Primer on Memory Consistency and Cache Coherence