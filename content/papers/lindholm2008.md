---
tags:
  - seed
title: "NVIDIA Tesla: A Unified Graphics and Computing Architecture"
date: 2024-9-12
---
**Authors:** Erik Lindholm, John Nickolls, Stuart Oberman, John Montrym<br>
**Conference:** MICRO 2008<br>
**DOI:** [IEEE](https://ieeexplore.ieee.org/document/4523358).,

## Background

If you couldn't already guess, this paper is a deep dive on NVIDIA's Tesla architecture. This architecture was first introduced in 2006, and it is significant for two reasons: 
1. It was the first architecture to unify execution of vertex and pixel-fragment shader programs.
2. It was developed and released along with CUDA (an example of hardware-software co-design).

> **CUDA (Compute Unified Device Architecture).** A parallel programming model built on top of C that enables developers to leverage NVIDIA GPUs for high-performance parallel computing applications.

The unification of compute was motivated by **poor resource utilization** by typical programs. Each GPU has a fixed amount of processing elements for each kinds of compute in the graphics pipeline. Unification would allow for **dynamic load-balancing**.

This paper specifically looks at the GeForce 8800 GPU in detail.

## Three Main Points

### 1. System Architecture

**Terminology**
- SP (streaming-processor)
- SPA (SP array)
- SM: streaming multiprocessor 
- TPC: texture/processor cluster
- ROP: raster operation processor

![[lindholm2008_fig1.png]]

The architecture has 128 SPs. The SPs are organized into 16 SMs with 8 SPs each. The SMs are organized into 8 TPCs with 2 SMs each. In Figure 1, work flows from top to bottom. Most processing happens in the SPA, but some processing in memory is done by the ROP, which is integrated into the memory system. In the figure, the elements above the SPA and memory are focused on work distribution and scheduling.

![[lindholm2008_fig2.png]]

The SPA scales with the number of TPCs. A more powerful GPU will have more TPCs, a smaller one will have less. A TPC is made up of the following:

- **Geometry controller**. To be honest, I am not sure what this does.
- **SMC (SM controller)**. Arbitrates usage of resources in the SM, load-balancing across three different workload types (vertex, geometry, pixel).
- **Two SMs**. Executes vertex, geometry, and pixel-fragment shader programs.
- **Texture unit**. Does texture work (idk lol). My understanding is that texturing is done at the end of the SM pipeline.

### 2. Streaming Multiprocessor Architecture

![[lindholm2008_fig3.png|center]]

SMs are the core compute elements of the Tesla architecture. It has eight SPs, two special-function units (SFUs), a multithreaded instruction fetch and issue unit (MT issue), an instruction cache (I cache), a read-only constant cache (C cache), and a 16 KB read/write shared memory.

A vertex/pixel shader describes how to process a vertex/pixel. This maps directly to a CUDA kernel, which describes in "C" how to compute a result. A good CUDA description will describe a massively parallel computation. An SM manages and executes up to 768 concurrent hardware threads, with "zero scheduling overhead".

SMs are based on a SIMT architecture. SIMT is different from SIMD—it is more "flexible" than SIMD, as it parallelizes execution/branching paths rather than just compute on data. Threads in SMs are organized in groups of 32 parallel threads called **warps**.

![[lindholm2008_fig4.png|center]]

Threads in the same warp are launched together, but each thread can afterwards branch and execute independently. Each thread has its own execution state.

Warps perform best when follow the same execution path. If the threads diverge (due to a branch instruction), the threads are grouped by which path they took and each path is executed serially.

An interesting thing to note about Tesla's SMs is that they move away from vector instructions and use scalar instructions instead. **The job of expressing parallelism is shifted away from the ISA and instead to the programming model.**

As one would expect, the Tesla SM abides by an instruction set architecture. The ISA is register based and has all kinds of instructions: floating-point, integer, bit manipulation, conversion, flow control, memory.

Regarding memory, threads have access to three different memory spaces. 
- **Local**. Per-thread, private, temporary data (external DRAM).
- **Shared**. Shared by cooperating threads in the same SM (on-chip, within SM).
- **Global**. Shared by all threads in a computing application (external DRAM).

Loads/stores to external DRAM are **coalesced** to minimize the number of redundant accesses. The coalescing is done at a "block"-level granularity.

### 3. CUDA

## Biggest Weakness



## Conclusions for Future Work

