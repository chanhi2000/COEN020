# read03a
2's Complement Multiplication by Hand

There are a couple of ways of doing 2’s complement multiplication by hand. Neither is actually used by the circuitry of a computer because there are more efficient (and more complex) algorithms for hardware implementation.

First, recall that multiplying one N-bit number by another N-bit number will create a product of $$2N$$ bits.

__Method #1__: First, *sign-extend both operands from $$N$$ to $$2N$$ bits* and then perform normal binary multiplication. Use the least-significant $$2N$$ bits of the result and discard the rest.

__Example__: Multiplying two 4-bit 2’s complement numbers
![fig01](read03a-fig01.png)

__Method #2__: Never multiply by a negative value, and *always sign-extend the partial products*:
- If both operands are positive: no problem
- If operands are of different sign: put positive operand on the bottom and proceed
- If both operands are negative: convert both to their positive equivalent and proceed

__Example__: Multiplying two 4-bit 2’s complement numbers
![fig02](read03a-fig02.png)

Now apply this to the problem we had in class ($$-1_{10}\times-2_{10}$$)

__Method #1__: First, *sign-extend both operands from $$N$$ to $$2N$$ bits* and then perform normal binary multiplication. Use the least-significant $$2N$$ bits of the result and discard the rest.
![fig03](read03a-fig03.png)

__Method #2__: Never multiply by a negative value, and always *sign-extend the partial products*:
![fig04](read03a-fig04.png)

Actually, if you didn't notice, there's a problem here! The first partial product is $$10$$, which when  sign-extended should be $$1110$$, not $$0010$$. We know that $$10$$ is supposed to be $$+2$$, but there's no way the computer would know because it just thinks that it's a 2-bit 2's complement number. The reality here is that $$+2$$ cannot be represented as a 2-bit 2's complement number, and so this method will not work in this case.

