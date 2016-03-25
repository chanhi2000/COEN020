# lab03
Read Binary

## GOAL:
A stronger understanding of unsigned and signed (2’s complement) binary representation.

## OBJECTIVE:
To implement a C program that converts a binary string to a decimal integer

## ASSIGNMENT:
Write a C program that does the following:
1. Read an ASCII string of eight 0’s and 1’s from the keyboard into an array of chars using the C library function gets.
2. Convert the string into an array of exactly 8 binary digits (integers 0 and 1), so that the least-significant digit is in the first element (subscript 0) of the array.
> **NOTE**: If the original string had more than 8 characters, use only the last (right-most) 8. If it had less than 8 characters, fill the most-significant bits of the binary array with zeroes.
3. Convert the binary array into an unsigned decimal integer and display its value
4. Convert the binary array into an signed (2’s complement) decimal integer and display its value

When you run your program, the screen should look something like:
```sh
Enter a binary string: 11110000
The unsigned decimal integer is: 240
The 2’s complement integer is: -16
```

Verify that your program operates correctly for several different binary input strings in the range $$00000000$$ to $$11111111$$, including positive, negative and end-of-range values. Demonstrate your program to the teaching assistant.

## EXTRA CREDITS:
Organize your program into four functions:

#### 1.
A function with two parameters—one that is a character string, and a second that is an array of eight integers. This function converts the ASCII characters from the string into binary digits (integer values 0 or 1) to fill the elements of the binary array.
> **NOTE**: The right-most digit in the input string should become the first element (subscript position 0) of the binary array. This function should NOT call printf or scanf.

Function prototype: `void Asc2Bin(char *string, int binary[8]);`

#### 2.
A function with one parameter—an array of eight binary digits (integers 0 and 1). This function should convert the sequence of binary digits into the corresponding unsigned decimal integer and return its value.
> **NOTE**: The first element of the binary array (subscript position 0) is the least-significant bit. This function should NOT call `printf` or `scanf`.

Function prototype: `int Bin2Unsigned(int binary[8]);`
