#### Instruction Set Overview
	-Groups or categories of instructions
		-Data movement (mov)
			-Arithmetic  (add, sub, multi, div)
		-Conversion
			-Changing sizes (change size)
	- Data movement is getting something from register to mem or mem to reg

#### Notations
	<reg> register oper must be reg
	<reg8> 8 bit register
	<reg16> 16 bit register
	<reg32> 32 big register
	<reg64> 64 bit register
		-# reps the bit size of the reg
	<dest> dest operand
	<src> source operand
	<imm> immediate number, gives the num/char/Literal
	<mem> Memory Location
	<op8> Represent the bit operand in reg or mem
	<op16> 16 bit operand
	<op32> 32 bit operand
	<op64> 64 bit operand
		-This is an oper that is a 8-64 bit operan
	<label> Program Label
	[] = Dereference -> Deref gives the data at the [address]
		-If you don't have brackets it will returna pointer to the address


### Data Movement
	- mov dest, src
		- must be the same size
		- source oper is unchanged
		- destiation operand is overwritten
		- destination oper can not be an immediate
		- both operands can not be memory locations
		- For var1 = var2, two instructions are required.
		- Example:
			- mov -> eax, dword[dVar1]
			- What to do -> where to put the data -> how much to get -> source
			- if dVar1 move is declared as a byte, it'll only take a byte of info
			- So declaration of how much, and grabbing proper source is important.
			- mov eax, 100
			- mov rcx, -1
			- mov eax, r8d
			- mov 5, ax ( wrong syntax )
			- mov eax, r8d (wrong sizes)
			- mov eax, r8
	Examples:
		- bVar1 db 42
		- Wvar2 dw 73
		- dVar3 dd 1729
		- dVar4 dq 22815088913
		- mov c1, byte [bVar1]
		- mov eax, dword[dVar3]
		- mov eax, qword[bVar1]
		- mov ax, word[dVar3]
			- Things to note. 
			- The size declaration
			- The ending locations
			- mem to mem
#### Conversion
	- Conversion of Size 
		- Larger -> Smaller possibly unsafe
			- Can lead to data loss or corruption
	- Widening Conversion
		- smaller to larger, very common
		- For unsigned, just zero upper bits
			- mov al, byte[bVar1]
			- mov rcx, 0
			- mov cl,al jrcx= bVar1
		- also:
			- mov zx, rcx, byte[Bvar1]
	- Restrictive Conversions:
		- Also, signed widening conversion forA register
			- cbw, cwde, cwd, cdqe, cdq, cqo
			- Used often arithmetic operations. 
#### Addition
	add <dest>, <src>
	operation: 
		dest = dest + src
	- must be the same size
	- src operand unchanged
	- dest overwritten
	- dest not immediate
	- both cant be in mem

	Addition how to work
	-Based on asst#3 data declartions
	;Bars1 = bnum + bnum3
		mov al, byte[bnum]
		add al, byte[bNum3]
		(rest in video...)

#### Subtraction
	- sub <dest>,<src>
	- dest = dest - source
	- same size, operand unchanged, dest overwritten, not immediate, both not mem
	- mov al, byte[bnum1]
	- sub al, byte[bnum3]
	- mov

#### Multi
	- imul = signed
	- mul = signed
		-mul <src>
		-imul <src>
	- Multiplies A register (al, ax, eax, rax) by source operand
	- Produces Larger ( x2 ) result!
	- Byte: al * <op8> = ax
	- word: ax * <op16> = dx:ox
	- dword: eax * <op32> = edx:eax
	- qword: rax * <op64> = rdx:rax

### Located on Page 88 of the Text

For homework dx is always upper, ax always lower portion


#### Div
	- idiv signed
	- div unsigned
	- divide A register by the source operand
	- produces smaller result
	- Byte: AX / <op8> = al Remained -> ah
	- Word: dx/ax / op16 = ax remainder -> dx
	- dWord: edx:Eax / op32 = eax -> edx
	- qWord: rdx:rax / op64 = rax -> rdx


## Located on Page 96 of the Text

