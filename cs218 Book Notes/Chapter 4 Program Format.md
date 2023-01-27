
#### 4.0 Program Format
	- Summarizes formatting requirements for assembly
	- Formating in this book are specific to yasm assembler
	- Other assemblers may have slight differences
	- Properly formated assembly source file consists of several main parts
		- Data Section - Initialized data declared here
		- BSS Section - uninitialized data is declared here
		- Text Section - Where the code be

#### 4.1 Comments
	- ; is used to denote comments
	- may be placed anywhere
	- anything following is ignored by assembler

#### 4.2 Numeric Values
	- Number values may be specified as
		- Hex
		- Decimal
		- Octal
	- Hex and base-16 are precded with 0x
		- 127 as hex -> 0x7f
	- octal, or base 8 is followed by q
		- 777q

#### 4.3 Defining Constants
	- constants are defined with equ
		- name equ value
	- Values cannot be changed during execution
	- constants are not assigned memory location
		- A bit more flexible as they are not assigned a specific type/size
		- still limited by range however
		- SIZE equ 10000 -> This could be a word or double-word too large for a byted

#### 4.4 Data Section
	- initialized data must be declared in "section .data" section.
	- must be space after word 'section'
	- var names must start with a letter, followed by letters or numbers
	- can use some special characters such as "_"
	- Var definitions must include name, data type and initial value for the variable
	- <variableName> <dataType> <initialValue>
		- db -> 8 bit var
		- dw -> 16 bit var
		- dd -> 32 bit var
		- dq -> 64 bit var
		- ddq -> 128 bit int
		- dt -> 128 bit float
	- Can be declared as such
		- bVar db 10 ;byte var
		- cVar db "H" ;char var
		- strng db "Hello World" ;string var
		- wVar dw 5000 ;16 bit var
		- dVar dd 50000 ;32 bit var
		- arr dd 100, 200, 300 ;3 element array
		- flt1 dd 3.14159 ; 32-bit float
		- qVar dq 1000000000 64-bit float
	- if sized too big will return assembler error

#### 4.5 BSS Section
	- Uninitialized data is declared in the "section .bss"
	- must be a space after the word section
	- all uninitialized data is declared here
	- variable names and declarations follow the same rules
	- supported data types are:
		- resb - 8 bit var
		- resw - 16 bit var
		- resd -32 bit var
		- resq - 64 bit var
		- resdq - 128 bit var
	- These are the primary assembler directives for uninitialized data
	- simple examples:
		- bArr resb 10 ; 10 element byte array
		- wArr resw 50 ; 50 element word array
		- dArr resd 100 ; 100 element double array
		- qArr req 200 ; 200 element quad array
			- allocated array is not init to any specific value


#### 4.6 Text Section
	- code is placed in here
	- must be a space after the word "section"
	- instructions are specified one per line
	- each line must be valid instruction
	- must have appropriate operands
	- will include headers or labels that define the initial program entry point
		- global _start
		- _start:
	- No special label or directives are required to terminate program
	- HOWEVER: system service should be used to inform OS that program is termed
		- This frees the resources to be recovere and re-utilized

#### 4.7 Example Program on pg 37

