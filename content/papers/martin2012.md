---
title: Why On-Chip Cache Coherence is Here to Stay
tags:
  - coherence
  - seed
date: 2024-8-19
---
**Authors:** Milo M. K. Martin, Mark D. Hill, Daniel J. Sorin<br>
**Journal:** [Communications of the ACM, July 2012](https://dl.acm.org/toc/cacm/2012/55/7)<br>
**DOI:** [ACM](https://dl.acm.org/doi/10.1145/2209249.2209269)

## Background

### Context

This paper was written in 2012, multiple years after the breakdown of [[dennard|Dennard Scaling]], which created a "power wall" that limited further increases in clock frequency. This wall prompted an industry shift towards multicore processors to extract performance through thread-level parallelism rather than focusing solely on single-threaded instruction-level parallelism.

The multicore processors mainly use shared memory as the means for communication between cores. Each of these cores have their own private caches that can hold copies of shared data, providing the potential for incoherence if not managed correctly. Ensuring that all cores see a unified and up-to-date view of shared memory is the responsibility of a cache coherency protocol. These protocols are typically implemented in hardware for better performance over software implementations.[^1]

[^1]: I'd like to know how coherence is implemented in software.

### Exigence

According to this paper, hardware coherence is claimed to not be scalable due to five concerns:
1) Excessive traffic over the interconnect to communicate with other cores
2) Infeasible storage needed to track sharing cores
3) Inefficiencies cause by adhering to an inclusive cache inclusion policy
4) Poor latency of cache misses
5) Energy overheads compounded by the first four problems

### Purpose

This paper tries to demonstrate that hardware-managed cache coherency will continue to scale alongside increasing core counts. It provides solutions to each of the five concerns above.

## Five Main Points

### Traffic

The paper analyzes interconnect traffic at a pretty high level of abstraction. It does not consider interconnect or router microarchitecture, and instead does an analysis using only the number of bytes transferred from core to core. The analysis is done in two parts: in the absence of sharing and in the presence of sharing. The analysis assumes that the shared last-level cache (LLC) follows an inclusive policy[^2], and it focuses only on cache misses as the source of coherence overheads.[^3]

[^2]: The LLC acts as the point-of-coherence, and thus it should have some sort of structure (i.e. a directory) to keep track of coherence state.
[^3]: Private cache hits have no need to generate coherence messages—if it's in the cache, you have your data. It's the misses that may need to shift data around the system via the coherence protocol.

#### Without Sharing

The analysis uses a 2x2 matrix to study coherence overheads without sharing. In the steady-state, a cache miss will cause an eviction of either a clean or dirty block (the first dimension). The analysis compares the number of bytes transferred with and without coherence (the second dimension).

|                   | Clean                         | Dirty                         |
|-------------------|-------------------------------|-------------------------------|
| Without Coherence | Req+Data = 80B/miss           | Req+Data+Data = 152B/miss     |
| With Coherence    | Req+Data+Evict+Ack = 96B/miss | Req+Data+Data+Ack = 160B/miss |
| Per-Miss Overhead | (96 - 80) / 80 = 20%          | (160 - 152) / 152 = 5.2%      |


**Evicting Clean Block Without Coherence**. A clean block need not be written back to the LLC. The private cache makes a request (8 bytes), and the LLC responds with data (8-byte address + 64 bytes of data).

**Evicting Clean Block With Coherence**. On top of the 80 bytes, the private cache must also let the LLC know what it evicted (8 bytes), and the LLC will send back an acknowledgement (8 bytes).

**Evicting Dirty Block Without Coherence**. A dirty block requires that data be sent back to the LLC. So on top of 80 bytes, another 64+8 bytes are sent to the LLC with the dirty data.

**Evicting Dirty Block With Coherence**. I guess the eviction data bytes signal an eviction, and so the only extra bytes needed are 8 acknowledgement bytes.

> [!info] Takeaway
> The overhead of coherence is "modest" for non-shared data. 5.2% for dirty evictions is good, but 20% for clean evictions isn't great. However, it's good that these overheads are fixed—they do not scale with core count.

#### With Sharing

With sharing, there are other cores that have a copy of the shared data. A private cache miss can either be a read miss or a write miss. This analysis first assumes that sharers are tracked with precise tracking (1 bit per sharer).



> [!info] Takeaway
> bruh

### Storage

### Inefficiencies of Inclusion

### Latency

### Energy

## Weaknesses

...

## Conclusions for Future Work

...