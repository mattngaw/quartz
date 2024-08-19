---
title: Why On-Chip Cache Coherence is Here to Stay
tags:
  - coherence
  - seed
date: 2024-8-19
---
**Authors:** Milo M. K. Martin, Mark D. Hill, Daniel J. Sorin<br>
**Conference:** [Communications of the ACM, July 2012](https://dl.acm.org/toc/cacm/2012/55/7)<br>
**DOI:** [ACM](https://dl.acm.org/doi/10.1145/2209249.2209269)

## Background

### Context

This paper was written in 2012, multiple years after the breakdown of Dennard Scaling, which created a "power wall" that limited further increases in clock frequency. This wall prompted an industry shift towards multicore processors to extract performance through thread-level parallelism rather than focusing solely on single-threaded instruction-level parallelism.

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

...

## Biggest Weakness

...

## Conclusions for Future Work

...