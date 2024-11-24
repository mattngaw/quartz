---
title: "Token Coherence: decoupling performance and correctness"
tags:
  - coherence
  - seed
date: 2024-8-13
---
**Authors:** Milo M. K. Martin, Mark D. Hill, David A. Wood<br>
**Conference:** ISCA 2003<br>
**DOI:** [IEEE](https://ieeexplore.ieee.org/document/1206999)

## Background

### Brief
This paper provides a new cache coherence architecture that tries to decouple performance from correctness. This architecture is called *Token Coherence* because of it explicitly counts and exchanges tokens to manage coherence permissions.
### Context
This paper was written around the time when multicore processors were becoming popular. Of course with multiple cores, each with their own private caches, ensuring coherence was necessary. 

There are two main ways of implementing a cache coherence protocol:
1. **Snooping**. All coherent nodes observe coherence requests in the same total global order and each collectively perform operations that maintain coherence.
2. **Directory**. Coherence requests get sent to a centralized "point-of-coherence" that keeps track of sharing. Coherence management is offloaded to the point-of-coherence, which interacts with coherent nodes directly (point-to-point).

There are tradeoffs associated with each of these strategies:
1. **Snooping**. 
	1. **Pro**. Simpler to implement (e.g. a shared bus)
	2. **Pro**. Lower latency, there is not as much indirection/lookups associated with snooping
	3. **Con**. Scales poorly with higher core counts (full broadcasting gets more expensive)
2. **Directory**.
	1. **Pro**. Less coherence traffic (keeping track of sharers allows for selective communication)
	2. **Pro**. More scalable to higher core counts
	3. **Con**. Added latency due to indirection (coherence requests must first go through directory before being sent out)

## Three Main Points

...

## Biggest Weakness

...

## Conclusions for Future Work

...