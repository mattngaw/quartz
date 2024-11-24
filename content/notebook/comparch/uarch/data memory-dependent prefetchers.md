---
title: Data Memory-Dependent Prefetchers
date: 2024-10-10
tags:
  - seed
---
A class of prefetchers that aim to prefetch memory access patterns that depend on data memory.

Such access patterns are typically irregular, for example:
- Indirect array accesses (`A[B[i]]`)
- Linked data structures (`node->next`)