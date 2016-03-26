# mt-sg

## Chapter 2: Data Representation

1. #### Unsigned:
	1. converting Base $$R$$ to Base $$10$$: polynomial evaluation
	2. converting Base $$10$$ to Base $$R$$: Repeated Multiplication/Division (by R)
	3. converting between two bases, neither of which is decimal
	4. conversion by inspection when bases are power-related (e.g. $$2^4=16$$)
	5. Representation errors (e.g. representing $$0.1_{10}$$ in binary)
	6. **Range**: N’b binary integer: $$0$$ to $$2^{N}-1$$
	7. Rollover (pattern behavior) vs. overflow (arithmetic behavior)
	8. Overflow during addition/subtraction: carry/borrow-out = 1
2. #### 2's Complement
	1. **Changing sign** (2 methods)
		1. Invert all the bits and add $$1$$
		2. Work right to left, copy through first $$1$$, then copy inverse
	2. **Converting to decimal** (2 methods)
		1. If negative,expand to $$N$$ bits, form 2’s complement, polynomial evaluation, add minus sign
		2. Polynomial evaluation, but change the sign of the most significant term
	3. **2’s complement (or unsigned) subtraction** (2 methods)
		1. Form 2’s complement of subtrahend (on bottom) and add, “or”
		2. Use subtraction table (only way to get the borrow bits!)
	4. **Overflow during addition / subtraction**
		1. Overflow impossible if adding / subtracting operands with same signs
		2. Detecting by inspection (human method - is the result reasonable?)
		3. Overflow if carry/borrow-in vs. carry/borrow-out of MS bit differ.
	5. **Range**: N’b integer: $$-(2^{N-1})$$ to $$+(2^{N-1}-1)$$


## Chapter 3: Implementing Arithmetic
1. Multiplication of two N’b operands produces 2(N’b) of product.
2. __Signed vs. unsigned multiplication__ (only MS half of product differs)
3. __Multiplication by $$2^N$$__: Shift left by N bits.
4. __Multiplication by other constants__: Use combination of left shifts, adds, and subtracts
5. __Divide by $$2^N$$__ : Arithmetic right shift by N’b (off by 1 if dividend is a negative odd number)
6. __Divide by other constants__: Use reciprocal multiplication: A+k = [A x (2N/k)]2N-1 .. N
7. __Fixed-point reals__ (e.g., 32.32)




