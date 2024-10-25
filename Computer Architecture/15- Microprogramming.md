## Microprogramming

- In microprogrammed control, execution of microcode instructions produces control signal changes.
- The microprogram converts each microcode instruction into control signals.
- The microprogram is stored in firmware, which is a small piece of read-only memory also called the control store.
- One microcode instruction is retrieved during each clock cycle.
![[Screenshot_20241025_054122.png]]

- If MARIE were microprogrammed, the microinstruction format might look like this:
![[Pasted image 20241025054327.png]]

 - `MicroOp1` and `MicroOp2` contain binary codes for each instruction. `Jump` is a single bit indicating that the value in the `Dest` field is an address that should be placed in the microsequencer, indicating which microprogram instruction should be executed next.
-  The table below contains MARIE’s micro-opcodes along with their corresponding RTL:
![[Pasted image 20241025054505.png]]

- Deletions from the table
	- Don’t use 00111. It is a duplicate of 01010.
- Additions to the table
	- `11000 MBR <- PC`
	- `11001 MBR <- X`
	- `11010 AC <- 1`
	- `11011 PC <- AC`
	- `11100 AC <- MBR`
- The first lines of MARIE’s microprogram are given below (using RTL rather than the micro-opcodes for clarity).
![[Pasted image 20241025054644.png]]

- The first four lines contain the fetch (first 3 lines) and decode (line 4) steps of the execution cycle. The remaining lines are the beginning of a jump table.
- The jump table entries indicate that if the high order bits of the IR (i.e., the opcode) have a given value, the microprogram will jump to the address where the remaining microoperations for that opcode will be found.
- For example, LOAD has opcode 1. Looking through the jump table, we can see that a LOAD instruction will cause the microcode processor to jump to 010 0111.
- At that address, it will find the fetch operand step for that instruction (if required) followed by the execute step, i.e., the RTL in microcode format:
![[Pasted image 20241025054743.png]]

- The last step of the encoded RTL will have a 1 in the JUMP field with a DEST of 000 0000. That will cause the system to jump to 000 0000, i.e., the beginning of the fetch cycle for the next operation.
- The chart above shows the microcode in RTL for convenience, but we could also show it in binary.
![[Pasted image 20241025054838.png]]

- A microprogrammed control unit works like a system- in-miniature. Microinstructions are fetched, decoded, and executed just like regular instructions.
- This extra level of interpretation makes microprogrammed control slower than hardwired, but this is not important since computers are getting faster every day.
- The advantage of microprogrammed control is that only the microprogram needs to be changed if the instruction set changes.
- In fact, all modern machines are microcoded. We study hardwired machines first just to make it easier to understand the microcode architecture.