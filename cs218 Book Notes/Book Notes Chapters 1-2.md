#### 1.1 Intro
	- This book addresses x86-64 class of processor
	- will work under any linux-based os
	- x86-64 is Complex Instruction Set Computing (CISC2) CPU Design
	- CISC is the internal process design philosophy

#### 1.2 What is Assembly Language
	- Low Level Machine Language that can be converted to machine code
	- Lowest Level that you can get to a processor
	- Direct Control of System Resources
		- Sets Processor Registers
		- Access Data Locations
		- interfacing with

#### 1.3 Why Learn ASM
	- To understand better how a computer works
	- Gives us tools to understand how technology changes, and cope.
	- Provides richer understanding of computer architecture and manipulation
	- Better understanding of tool chain
		- Tool chain code written by human and turning it into something a CPU can use
	- Improve Algorithm skills

## Chapter 2

#### 2.1 Architecture Overview
	- CPU, RAM, Secondary Storage, I/O, Bus
	- Von Neumann Architecture

#### 2.3 CPU
	- CPU is the brains
		- Called processor, chip or die
	- CPU Consists of 
		- Arithmetic Logic Unit (ALU)
	- To Support the ALU
		- Processor Registers, and cache memory are located "onthe die"

##### 2.3.1 CPU Registers
	- Register is a temp storage or working location. 
	- Computations are performed by 
	- General Purpose Registers (GPRs)
		- 16, 64 bit GPRS, can access whole or parts of register
		- Some of the GPRS are used for specific tasks
	-Different Register Types
		-Stack Pointer Registers (RSP)
			- points to the current top of stack
		- Base Pointer Register (RBP)
			- used as base pointer, should not be used for data or anything else
		- Instruction Pointer Register (RIP)
			- Used for the NEXT instruction
		- Flag Register (rFlag)
			- used to show CPU status
		- XMM Registers 
			- Used to support 64bit and 32 bit floating points