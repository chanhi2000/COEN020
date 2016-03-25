# lab09
Multiplication of two 64-bit Integers

## GOAL:
Learning how to implement 64x64 bit integer multiplication on a 32-bit cpu.


## OBJECTIVE:
To replace the C functions defined in `Integer64x64.c` by equivalent assembly code in `Integer64x64.s`.


## BACKGROUND:
Most 32-bit CPUs can multiply two 32-bit integers in a single instruction, but 64x64-bit multiplication must be implemented as a sequence of instructions or as a subroutine. When you multiply two 64-bit integers in C, the compiler generates code that calls a library function to do the multiplication. The purpose of this assignment is write our own version of that routine in assembly.


## APPROACH:
Multiplying two 64-bit unsigned integers on a 32-bit CPU requires breaking each number into two 32-bit halves, i.e.: $$N=2^{32}\times{N}_{\text{hi}}+N_{\text{lo}}$$, where $$N_{\text{hi}}$$ and $$N_{\text{lo}}$$ are respectively the most and least significant 32-bit halves. Thus:

$$
\begin{align*}
A\times{B}&=(2^{32}A_{\text{hi}}+A_{\text{lo}})\times(2^{32}B_{\text{hi}}+B_{\text{lo}})\\
&=2^{64}A_{\text{hi}}B_{\text{hi}}+2^{32}(A_{\text{hi}}B_{\text{lo}}+B_{\text{hi}}A_{\text{lo}})+A_{\text{lo}}B_{\text{lo}}
\end{align*}
$$

Each partial product term requires computing the 64-bit product of two 32-bit numbers. After shifting left 0, 32, or 64 bits according to the corresponding power of 2 scale factor, these partial products are then added to compute the final 128-bit product.
![fig01](lab09/lab09-fig01.png)

Multiplication of 64-bit integers in C keeps only the least significant 64 bits of the product, so one entire partial product term and the most significant half of two others are not needed. Note that one algorithm works for both signed and unsigned multiplication, since the only difference is in the discarded most- significant half of the product.

