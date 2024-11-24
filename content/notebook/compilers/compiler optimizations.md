---
title: Compiler Optimizations
tags:
  - seed
---
How to improve code performance? Look to the "[[iron-law|iron law]]"!

Here is the slightly more abstracted version of the iron law, but for compiler optimization.

$$
\frac{1}{\text{performance}} = \frac{\text{time}}{\text{program}} = \frac{\text{operations}}{\text{program}} \times \frac{\text{avg. time}}{\text{operation}}
$$

To reduce execution time, decrease the terms on the right-hand side.

1. **Decrease # ops**. Do the same with less operations.
	1. Good examples are [[common subexpression elimination]] and [[dead-code elimination]].
	2. Not universal, e.g. replacing multiple RISC-like instructions with one CISC-like instruction isn't necessarily faster ([[RISC vs. CISC]]).
2. **Decrease time per op**. Use "quicker" operations.
	1. dsad