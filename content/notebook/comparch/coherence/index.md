---
title: Coherence
---
Coherence (without the cache) is a general problem that most commonly shows up as *cache coherence*.

The motivation for coherence can be demonstrated by a [[incoherence example|cache incoherence example]].

> [!def] **Definition** (Coherence v1)
> A property of a multiprocessor system with shared memory that ensures that all processors have a unified and up-to-date view of the data despite each processor having its own cached copies of the data.

Coherence is a **single-address** problem, meaning it is not concerned with the interaction between memory accesses to different memory address.

> [!def] **Definition** (Coherence v2)
> A property that is upheld **if and only** if the system maintains two invariants for any memory location **A** at any given time:
> 1. **Single-Writer, Multiple-Reader Invariant.** There exists *either* a single core that can read/write to **A** *or* some number of cores that can only read from **A**.
> 2. **Data-Value Invariant.** The value at **A** at the start of any epoch (read-only, read/write) is the same as the value at **A** at the end of the *most recent* read-write epoch.

Coherence can be maintained at **any granularity**
- typically for cache coherence tracked at the **cache-block level**
- i.e. there is either one writer or any number of readers for an entire cache block

Coherence is **NOT** architectural.

Cache coherence is maintained by a [[Cache Coherence Protocol|cache coherence protocol]] to which all private cores adhere.