---
tags:
  - seed
title: Complexity-Effective Superscalar Processors
date: 2024-9-3
---
**Authors:** Subbarao Palacharla, Norman P.Jouppi, J.E. Smith<br>
**Conference:** ISCA 1997<br>
**DOI:** [ACM](https://dl.acm.org/doi/10.1145/264107.264201)

## Background

Most processors at the time of writing could be put into one of two camps:
- **Brainiacs**. Complex processors that aim for higher IPC at the cost of clock frequency.
- **Speed Demons**. Simple processors that aim for higher clock frequency at the cost of IPC.

This paper has two objectives:
1. Analyze sources of superscalar out-of-order pipeline complexity.
2. Propose and evaluate a new "complexity-effective" microarchitecture.

Through an analysis of logic complexity in today's pipelines, a complexity-effective design hopes to achieve the IPC of a brainiac while keeping the clock frequency of a speed demon.

This new microarchitecture proposed by this paper is "dependence-based", since it focuses on grouping dependent instructions together.

## Three Main Points

### Sources of Complexity

The paper uses the following model of a superscalar out-of-order processor.

![[palacharla1997_pipeline.png|twothirds|center]]

From this model, the paper chooses a few key structures to analyze as sources of complexity:

1. **Register rename logic**. This logic maps architectural (logical) register to physical registers.
2. **Wakeup logic**. This logic wakes up an instruction waiting in the issue window (reservation station) once it is ready to be issued into the execution stage.
3. **Selection logic**. The logic responsible for picking which instruction to execute next out of the set of ready instructions.
4. **Bypass logic**. The logic responsible for broadcasting/forwarding results of executed instructions to other instructions waiting in the issue window.

#### Analysis

This paper analyzes these four sources of complexity in two phases.
1. Gathering of representative CMOS circuits used by industry
2. Delay analysis + optimization of the circuits to determine the critical path of the pipeline (cost of complexity)

## Biggest Weakness

> "Hence, as architects build machines with wider issue widths and larger window sizes in advanced technologies, it is essential to consider microarchitectures that are complexity-effective i.e. microarchitectures that facilitate a fast clock while exploiting similar levels of ILP as an ideal large-window machine."

The paper frequently points to "future" technologies and microarchitectures—it looks to mitigate future problems that will arise from scaling. Of course, this microarchitecture did not stick, and so here are my guesses why:

1. The paper assumes clock frequency will be limited by scaling of structures. My understanding is that instead clock frequency was instead limited by power and heat.
2. The paper assumes there is good reason to keep scaling the size of structures. There should be diminishing performance returns for increasing structure sizes due to limited ILP in traditional programs.

## Conclusions for Future Work

...