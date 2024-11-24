---
title: Cache Incoherence Example
date: 2024-8-26
tags:
  - sapling
---
Assume a two-core system where the cores both access shared memory and each have a private cache. Assume there is no system-level protocol that is managing [[notebook/comparch/coherence/index|coherence]].

Assume the following order of operations:
1. Core 0 reads address A, sees 42, and caches it.
2. Core 1 reads address A, sees 42, and caches it.
3. Core 0 writes 43 to address A, and caches it.

At this point in time, core 0 has 43 in its cache, while core 1 cache and shared memory have 42.

4. Core 1 reads address A. What should it see?

Without a protocol managing coherence across the system, core 1 might naively look at its private cache and see 42. In reality, the most up-to-date value would be 43, written by core 0.