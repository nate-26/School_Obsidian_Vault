## Indirect Addressing

- So far, all of the MARIE instructions that we have discussed use direct addressing.
- This means that the address of the operand is explicitly stated in the instruction.
- In indirect addressing, the address of the address of the operand is given in the instruction.
	- If you have ever used pointers in a program, you are already familiar with indirect addressing.
	- Indirect addresses are needed to point at different values in a table so you can use a loop to process them, i.e., to get values from an address that changes during the run.
- MARIE contains two indirect instructions:
	- ADDI X (op code B): Look at address X, lookup the address stored there, and add that value to the AC.
- JUMPI X (op code C): Branch to the address in memory cell X. Can be used to return from a subroutine implemented with JNS (see next slide for JNS).
- MARIE also contains two other useful instructions that we have not described before:
	- JNS X (op code 0): Store return address (i.e., next sequential address) at X, then jump to X+1.
	 - CLEAR (op code A) sets the contents of the accumulator to zero.
- In this section we will look at how RTL is created for instructions with indirect addresses.
- The ADDI instruction specifies the address of the address of the operand. The following RTL shows us what is happening at the register level
```
MAR <- X
MBR <- M[MAR]
MAR <- MBR
MBR <- M[MAR]
AC <- AC + MBR
```

- The first two lines find the data value stored at the address X.
- The next two lines treat that data value as an address and find the value stored there. These are the lines that make ADDI different from ADD.
- Finally the last line adds the data value now in MBR to the accumulator.
```
MAR <- X
MBR <- M[MAR]
MAR <- MBR
MBR <- M[MAR]
AC <- AC + MBR
```

---
### Subroutines

- Subroutines are another helpful programming tool.
- The jump-and-store instruction, JNS, gives us limited subroutine functionality.
- JNS X does the following:
	- Stores the return address (i.e., the address of the next sequential instruction) at address X.
	- Jumps to the address specified at address X+1.
- After the subroutine is finished, JUMPI X can be used to return to the original address, since JUMPI jumps to the address stored at X.
- For example, JNS 108 will store the return address (i.e., the address of the instruction after the JNS) at 108, then continue with the subroutine code at 109.
- Here is the RTL for JNS.
```
MBR <- PC
MAR <- X
M[MAR] <- MBR
MBR <- X
AC <- 1
AC <- AC + MBR
PC <- AC
```

- The first 3 lines store the address of the next instruction (which is always in the PC) in memory address X.
- The remaining lines load X+1 into the PC so that the instruction at X+1 will be executed next.
- Note that JNS cannot handle recursive calls because JNS X always uses the same address, namely X, to store the return address. In other words, the return address is stored in the first word of the subroutine. (Of course, that is not good programming practice today.)

---
### CLEAR

- Our last helpful instruction is the CLEAR instruction (op code A). It is not an indirect addressing instruction.
- All it does is set the contents of the accumulator to all zeroes.
- This is the RTL for CLEAR:
	- `AC <- 0`
- We put our new instructions to work in the program below.
![[Pasted image 20241022154605.png]]
![[Pasted image 20241022154853.png]]
![[Pasted image 20241022154909.png]]
*Example of Indirect Addressing*

- It adds the five numbers at addresses 117-11B.
- This shows the data section of the program, with an explanation of each variable below.
- The variable Addr contains the starting address of the numbers to be added.
- The variable Num contains the number of numbers to be added.
- The variables Next and Ctr are work variables.
- The variable Sum contains the answer.
- The variable One contains the loop increment.


