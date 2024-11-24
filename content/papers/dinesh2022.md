---
tags:
  - seed
title: "SynthCT: Towards Portable Constant-Time Code"
date: 2024-9-18
---
**Authors:** Sushant Dinesh, Grant Garrett-Grossman, Christopher W. Fletcher<br>
**Conference:** NDSS 2022<br>
**DOI:** [NDSS](https://www.ndss-symposium.org/ndss-paper/auto-draft-223/)

## Background

**Main Problem**. Constant-time code can be written once, and it can be compiled once for a specific architecture. However, the same code for the same architecture can expose different side channels based on the microarchitecture.

**Proposed Solution**. SynthCT is a framework for automating the translation of unsafe code into safe code for any given program, ISA, and microarchitecture.

### Concepts

**Constant-time programming**. A method of writing programs such that they avoid side-channel attacks. The goal is to make the execution time of a function consistent regardless of the input data. There are three key sources of side-channel attacks:
1. Secret-dependent memory accesses
2. Secret-dependent branches
3. Secret inputs to variable-latency instructions

The paper introduces this notion **unsafe vs. mostly safe vs. safe** code:
- **Unsafe** code does not mitigate any side-channel attacks.
- **Mostly safe/constant-time** code avoids side-channel attacks due to memory accesses and branches, but not side-channel attacks from the use of variable-latency instructions.
- **Safe** code avoids all known side-channel attacks.

### Threat Model

1. Victim program runs on a shared machine co-located with an attacker program.
2. The attacker aims to gather data private to the victim via microarchitectural side channels.
3. The victim program is [public](https://en.wikipedia.org/wiki/Kerckhoffs%27s_principle).

## Three Main Points

### 1. SynthCT Architecture

SynthCT takes the following inputs:
- A *mostly constant-time* program in binary form (the code is **already compiled**)
- The ISA and its semantics
- A microarchitecture and a specification listing which instructions in the ISA are safe

And provides the following output:
- A translated version of the program that replaces unsafe instructions with safe, constant-time instructions.

![[dinesh2022_fig1.png|center]]

#### Step 1: Synthesis

Using the ISA and its associated semantics, SynthCT creates a library of translations, mapping each instruction to sets of other instructions that can be used to implement that instruction.

#### Step 2: Microarchitecture Targeting

SynthCT combines the translation library with the given safe-set specification for a given  microarchitecture to generate a library of *safe* translations for that microarchitecture. If there are multiple ways to safely translate an unsafe instruction, SynthCT opts for the shortest sequence as a proxy for performance.

### Step 3: Deployment



## Biggest Weakness



## Conclusions for Future Work

