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
