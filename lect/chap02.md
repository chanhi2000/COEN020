# chap02
Data Representation

## KINDS OF DATA
- #### Numbers
 	- Integers
 		- unsigned
 		- signed
	- Reals
		- fixed-point
		- floating-point
	- Binary-coded decimal
- #### Text
	- ASCII Characters
	- Strings
- #### Other
	- Graphics
	- Images
	- Video
	- Audio


## NUBMERS ARE DIFFERENT
- Computers use binary numbers (0's and 1's).
	- Requires more digits to represent the same magnitude.

- Computers store and process numbers using a fixed number of digits (“fixed-precision”).

- Computers represent signed numbers using 2's complement instead of the more natural (for humans) “sign-plus-magnitude” representation.


## POSITIONAL NUMBER SYSTEMS
- Numeric values are represented by a sequence of digit symbols.

- Symbols represent numeric values.
	- Symbols are not limited to ‘0’-’9’!

- Each symbol’s contribution to the total value of the number is weighted according to its position in the sequence.


## POLYNOMIAL EVALUATION
- Whole Numbers (Radix = 10):
$$
1234_{10}=1\times10^3+2\times10^2+3\times10^1+4\times10^0
$$

- With Fractional Part (Radix = 10):
$$
36.72_{10}=3\times10^1+6\times10^0+7\times10^{-1}+2\times10^{-2}
$$

- General Case (Radix = R):
$$
(S_1S_0.S_{-1}S_{-2})_R=S_1\times{R}^1+S_0\times{R}^0+S_{-1}\times{R}^{-1}+S_{-2}\times{R}^{-2}
$$

## CONVERTING RADIS $$R$$ to Decimal