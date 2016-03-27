# read03b
Converting an Unsigned Integer Product to a Signed Integer Product

Consider the problem of finding the product of two signed 2’s complement integers. We’ll do this using the same approach we used for fixed-point multiplication, i.e., compute the unsigned product and then modify it — except that we need to keep the full double-length result rather than just the middle half. We’ll do it here using four-bit operands, but the principle is the same regardless of operand size.

First the math:
$$
\begin{align*}
A_uB_u&=\left(2^3A_3+A_{2..0}\right)\left(2^3B_3+B_{2..0}\right)\\
&=2^6A_3B_3+2^3\left(A_3B_{2..0}+B_3A_{2..0}\right)+A_{2..0}B_{2..0}\\\\
A_sB_s&=\left(-2^3A_3+A_{2..0}\right)\left(-2^3B3+B_{2..0}\right)\\
&=2^6A_3B_3-2^3\left(A_3B_{2..0}+B_3A_{2..0}\right)+A_{2..0}B_{2..0}\\\\
&=A_uB_u-2^4\left(A_3B_{2..0}+B_3A_{2..0}\right)
\end{align*}
$$

This equation tells us that for each negative operand, we should subtract the three least-significant bits of the other operand from the most-significant half of the unsigned product. When performing these subtractions, even though the math says to subtract only the three least-significant bits (i.e., $$A_{2..0}$$ or $$B_{2..0}$$ or both) from the unsigned product, you can actually use the entire 4-bit operand (As or Bs):

$$
A_sB_s=A_uB_u2^4\left(A_3B_S+B_3A_S\right)
$$

**Case 1**: Both operands are positive: No subtractions are performed.

**Case 2**: Operands of different signs: We subtract the positive operand from the most-significant half of the unsigned product. The fourth bit of the positive operand is zero, and thus has no effect on the result.

**Case 3**: Both operands are negative: The most-significant bits of both 4-bit operands are 1’s. The first subtraction thus changes the sign of the result; the second subtraction changes it back ─ the same final result you would get if the subtraction used only the least-significant three bits (i.e., $$A_{2..0}$$ and $$B_{2..0}$$).

#### EXAMPLE 1:
