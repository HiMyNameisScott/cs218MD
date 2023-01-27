Notes for Lecture 1-2.

### Recap
Assembly Process
	-> Assembly source file -> Object File -> EXE
	-> Machine and Assembly are 1 to 1
	Assembly is the last abstracted step prior to machine code.

### Architecture
	-CPU
	-I/O
	-Primary Storage
	-Secondary Storage
	--All connected by a BUS

### Storage Elements
	Mem is stored in bytes, not bits.
		-Byte Addressable
	Each mem location is a byte
	Basic Storage Elements
		Bytes -> 8 bits -> Char
		Words -> 16 bits -> short
		double-words -> 32 bits -> int/float
		quad-words -> 64 bits -> long/double
	Important to remember that we default to single bytes and not to    individual bits.


### Registers
	Temporary Storage Locations built into the CPU
	Temporary storage for intermediate results. Calcs done in CPU

	Register Names: rax, rbc, rcx....etc 
	All registers hold up to 64 bits.
	But, sometimes need to access < 64 bits, and can from there use sub-parts of the register to access lower bit portions of the registers.
	ie, if you have a 32 bit data structure you can get away with only using 32 bits of the 64 bits. 
	if we use rax we talk about the entire 64 bits, if eax we are talking about 32 bit registers.


### Special Registers
	- RIP -> points to next instruction to be executed
	- RSP -> points to the current top of stack


## Data Representation
	Everything is a 1 and 0.

### Decimal / Binary / Hex
	Decimal -> Positional based numbering system. Base 10
	10^0, 10^1...

#### Binary
	-Positional based numbering system on Base 2.
	2->4->8->16...

Most examples in hardware use 8 bits, so data is usually shown in 8 bits.
	00001010 = 10
	00000011  = 3

### Hex
	Base 16 numbering system. 
	1-10 + A B C D E F. A-F is used to represent digits past 9. A = 10, B = 11.... etc etc. 
	Each hex is 4 bits of binary.

#### Integers
	- Whole numbers only, no fractions
	- 32 bits -> Double word
	- Byte -> 8 bits, so 4 bytes in an int
	- unsigned -> binary 8 bits -> 2 hex digits
	- Examples of binary to hex
		- 00000000 = 0 = 0x00
		- 11111111 = 255 0xFF
		- 10000000 = 128 = 0x80

#### Integers Signed
- Based on the element sizes, have a limited amount of space to store info
- Example 8 bits -> 0-255
- 300 can not be stored in a byte variable
- Positive and negative numbers chang the range of values we can assign to a byte var
	- Shifting from 0-255 to 128 - 127
- Same rules apply to larger sizes however
- words ( 16 bits ) 0 - 65,535, double-words, quad-words, double quadword etc all have the same rules

### Twos Compliment
	- Only applies to signed data !!
	- If Value is > 0, use binary
	- If value < 0
		- Take ones compliment (negate)
		- Add 1 ( in binary )
	- Signed Data only needs extra work if the value is < 0.
		- Invery then add 1. 
	- Example
		- If your value is -9,
		- Write 9 in binary -> 00001001
		- Then reverse the 1 and 0s
		- 00001001 -> 11110110
		- Then add 1 in binary
		- 11110110 -> 11110111 (we cant tell if the number is negative just from the 1/0s, this needs to be declared by the program or asked by the question)
	- To go backwards from twos comp to non-twos comp is same process
		- invert, then add 1

### Signed and Unsigned Addition
	- This is a part of why declartion is important
	- 2 binary numbers can mean 2 different things when signed/unsigned
	- 248 -> 11111000 or -8 11111000 (prior to 2s compliment). 
	- This can lead to confusing situations and is why declaration is important

### Floating Point Representation
	-Representation for floats are more complex
	- Multiple scehemes 
	- We Will look at IEEE 754 32-bit floating point standard
	- 32 bits split into pieces
		-leading bit is sign
		-next 8 bits are exponent
		-rest of the compenent is the rest of the fraction. 
			| sign | 2^3, 2^2, 2^1, 2^0 | . | 2^-1(1/2) , 2^-2(1/4)...|
	Conversion happens as such:
		Determine Sign
		Convert value to binary
		normalize (scientific notation)
		Determine bias exponent
		Write in binary
		convert to hex
		located on pg 26 of text.
		



## Ast02
	-Data on PDF or Text File
	-Data goes in data section, code in text section
	