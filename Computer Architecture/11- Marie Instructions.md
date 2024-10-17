## MARIE
*aka* **The Machine Architecture that is Really Intuitive and Easy**

- Designed to illustrate basic architecture concepts.
- Makes it easy to understand more complex system architectures

### MARIE Architecture Characteristics:
- Binary, two's complement data representation.
- Stored program, fixed word length data and instructions.
- 4K words of word-addressable main memory.
- 16-bit data words.
- 16-bit instructions, 4 for the opcode and 12 for the address.
- 16-bit arithmetic logic unit (ALU).
- Seven registers for control and data movement.

### MARIE'S Seven Registers:

- Accumulator, AC, a 16-bit register that holds a conditional operator (e.g., "less than") or one operand of a two-operand instruction.
- Memory address register, MAR, a 12-bit register that holds the memory address of an instruction or the operand of an instruction.
- Memory buffer register, MBR, a 16-bit register that holds the data after its retrieval from, or before its placement in memory.
- Program counter, PC, a 12-bit register that holds the address of the next program instruction to be executed.
- Instruction register, IR, which holds an instruction immediately preceding its execution.
- Input register, lnREG, an 8-bit register that holds data read from an input device.
- Output register, OutREG, an 8-bit register, that holds data that is ready for the output device.

![[{20C25253-6701-4C77-806E-3217F39409B0}.png]]
*MARIE architecture shown graphically*

- The registers are interconnected, and connected with main memory through a common data bus.
- Each device on the bus is identified by a unique number that is set on the control lines whenever that device is required to carry out an operation.
- Separate connections are also provided between the accumulator and the memory buffer register, and the ALU and the accumulator and memory buffer register.
- This permits data transfer between these devices without use of the main data bus.
![[{3AFA38FE-3201-48AD-ACB9-8CD6AF6F2B6B}.png]]
*MARIE data path shown graphically*

- All the bits of the control bus enter and leave each component.
- The bus address on the diagram shows which bit configuration needs to be represented (e.g., I = 001, 2 = 010, etc.) in order for that component to know that it is being spoken to.

### MARIE ISA

- A computer's instruction set architecture (ISA) specifies the format of its instructions and the primitive operations that the machine can perform.
- The ISA is an interface between a computer's hardware and its software.
- Some ISAs include hundreds of different instructions for processing data and controlling program execution. 
- The MARIE ISA has only thirteen instructions.
![[{A041FC8E-A835-43E5-BD51-27A488D200CA}.png]]
*MARIE Instruction Format*

![[{47D66D41-8170-42DA-AB21-E45B3E3D1B35}.png]]
*Fundamental MARIE Instructions*

![[{3DED357F-F39A-4568-8A73-CCC28061763A}.png]]
*This is a bit pattern for a LOAD instruction as it would appear in the IR*

- We see that the opcode is 1 and the address from which to load the data is 3.

![[{06EE9C22-94D9-406A-AE47-21185D8385BC}.png]]
*This is a bit pattern for a SKIPCOND instruction as it would appear in the IR*

- We see that the opcode is 8 and bits 11 and 10 are 10, meaning that the next instruction will be skipped if the value in the AC is greater than zero.
### MARIE RTL

- Each of our instructions actually consists of a sequence of smaller instructions called microoperations.
- The exact sequence of microoperations that are carried out by an instruction can be specified using register transfer language (RTL).
- In the MARIE RTL, we use the notation M\[X] to indicate the actual data value stored in memory location X, and <- to indicate the transfer of bytes to a register or memory location.
- The RTL for the LOAD instruction is:
```
MAR <- X
MBR <- M[MAR]
AC <- MBR
```
- Similarly, the RTL for the ADD instruction is:
```
MAR <- X
MBR <- M[MAR]
AC <- AC + MBR
```

- Recall that SKIPCOND skips the next instruction according to the value of the AC.
- The RTL for this instruction is the most complex in our instruction set:
```
If IR[11 - 10] = 00 then
	If AC < 0 then PC <- PC + 1
else If IR[11 - 10] = 01 then
	If AC = 0 then PC <- PC + 1
else if IR[11 - 10] = 10 then
	If AC > 0 then PC <- PC + 1
```
