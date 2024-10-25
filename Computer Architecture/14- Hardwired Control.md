### Decoding

- A computer’s control unit ensures that each instruction is executed in sequence, making sure that data flows to the correct components as each instruction is executed..
- There are two general ways in which a control unit can be implemented: hardwired control and microprogrammed control.
	- In a hardwired machine, digital logic components are used to select the “from” and “to” components and ensure that data flows to them at the correct time.
	- A microprogrammed machine contains a small program in a piece of read-only memory in a component called the microcontroller. The microprogram contains the RTL for each instruction. In order to execute an instruction, the microcontroller interprets the corresponding piece of this program.
- MARIE is a hardwired machine. The operation of MARIE’s control unit is defined by the RTL for each instruction..
- Each line of RTL is implemented with digital logic components that cause the appropriate data to flow from the component on the right-hand side of the RTL line to the left-hand side..
- For example, the RTL for the ADD instruction is:
```
MAR <- X
MBR <- M[MAR]
AC <- AC + MBR
```

- Each of MARIE’s registers has a unique address along the datapath.
- The addresses take the form of signals issued by the control unit.
- MARIE needs 3 lines to identify addresses 0 - 7 on the bus.
- Many machines would use 8 signals, one of which would be high at any given time.
![[Pasted image 20241022155419.png]]

- The MARIE CPU contains two sets of three signals.
- $P_2$, $P_1$ and $P_0$ determine which component data will be read from.
- $P_5$, $P_4$ and $P_3$ determine which component data will be written to.
- The component addresses are shown in the diagram.
- For example, the MBR has address 3.
- Since the MBR is a 12-bit register, we can build it as a set of 12 D flipflops.
- We add gates implementing P3 AND P4 AND NOT P5 before the input to these flipflops so that data will only flow into the MBR (i.e., writing to the MBR) when address 3 is activated.
- Similarly, we add gates implementing P0 AND P1 AND NOT P2 after the output of these flipflops so that data will only flow out of the MBR (i.e., reading from the MBR) to the bus when those signals are activated.
- In the picture below, you can see P0 AND P1 AND NOT P2 on the right.
- You can see P3 AND P4 AND NOT P5 on the left.
- You can also see the connections between each of the 16 bits of the data bus (for legibility, shown on both sides of the diagram) and its corresponding D flipflop.
![[Pasted image 20241022155950.png]]

- Looking again at the first line of the RTL for ADD:
	- `MAR <- X`
- After an ADD instruction is fetched, the address field, X, is in the rightmost 12 bits of the IR. The IR has a datapath address of 7.
- According to this line of RTL, X must be copied to the MAR. The
- MAR has a datapath address of 1.
- Thus we need to raise signals P2, P 1 , and P0 to read from the IR, and signal P 3 to write to the MAR.
- When the high order bits of the IR contain the opcode for ADD, these signals must be set high to implement the first line of the RTL. In succeeding clock ticks, the remaining lines of the RTL for ADD will be implemented.
- Most instructions need multiple clock ticks, one for each line of RTL. A binary counter is used to identify which line of RTL is being executed.
- MARIE has a maximum of 3 lines of RTL for an instruction (7 if you include the advanced instructions in 4e). Therefore 4 timing signals (8 including the advanced instructions) are needed, one to indicate each line of RTL and one to reset the counter for the next instruction.
- These timing signals are named $T_0$, $T_1$, $T_2$ , ... $T_7$.
	- Theoretically, we could use combinations of two timing signals to obtain 4 clock times, or combine 3 timing signals to get 8 clock times, but we won’t do it that way.
- The $C_r$ signal is used to reset the counter.
- Looking at the RTL chart, we can see that the ALU has only three operations: add, subtract, and clear.
- We have four ALU signals, A 0 through A 3, available to indicate these operations. We will use:
	- $A_0$ = add | $A_1$ = subtract | $A_2$ = clear
	- We could use A 3 = no operation, but it’s not necessary, so we won’t.
	- Another design alternative would be to use combinations of two signals to generate four values.
	- These signals don’t need to match the ALU control values in 3c- 40c.
- When we want to signal an ALU instruction, we raise the corresponding signal.
- Therefore the entire set of MARIE’s control signals contains:
	- Register controls P0 through P5
	- ALU controls A 0 through A3
	- Timing signals T0 through T7 and counter reset C r
- All of the RTL lines needed for MARIE’s instructions can be implemented by ensuring that the correct register and/or ALU control signals are raised during the correct clock ticks for a specific instruction.
- Here is the full signal sequence for ADD. It shows which control signals must be set high at each clock tick.
![[Screenshot_20241025_053255.png]]

- Line 1: input is address 7 (low order bits of the IR) and output is address 1 (MAR).
- Line 2: input is address 0 (main memory) and output is address 3 (MBR).
- Line 3: input is address 3 (MBR), output is address 4 (AC), and the operation happening inside the ALU (i.e., what happens to the AC) is addition.
- The diagram below is called a timing diagram ($P_4$ is not shown).
![[Screenshot_20241025_053500.png]]

- You can see which signals, including the timing signals, are high at each clock tick.
- This instruction has 4 clock ticks, $C_0$ - $C_3$ 
![[Screenshot_20241025_053604.png]]

- The RTL and the control signals are the same whether the machine is hardwired or microprogrammed.
- In hardwired control, the bit pattern of an instruction feeds directly into the combinational logic of the control unit.
![[Screenshot_20241025_053711.png]]

- Now you can see why the decoder, the binary counter and the adder are needed to build a computer.
- More complex instructions sets would also contain shift instructions.
- A shifter is also useful for implementing multiplication.
![[Screenshot_20241025_053812.png]]

- The flipflops at the top show that this code is only executed when the high order bits of the IR (i.e., the opcode) is 0011.
