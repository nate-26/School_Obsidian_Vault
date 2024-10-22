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
