- Since there is a circuit to implement the Boolean function:
$$F(x,y,z) = x+!yz$$
- This circuit is an example of a combinational or *combinatorial* logic circuit..
- Combinational logic circuits produce a specified output at the instant when input values are applied.
	- In a later section, we will explore circuits where this is not the case.
---
# Half Adder #
- Combinational logic circuits give us many useful devices.
- One of the simplest is the *half adder,* which finds the sum of two bits.
- To build a half adder, look at its truth table, shown below.
- It had two inputs and two outputs.

| x   | x   | sum | carry |
| --- | --- | --- | ----- |
| 0   | 0   | 0   | 0     |
| 0   | 1   | 1   | 0     |
| 1   | 0   | 1   | 0     |
| 1   | 1   | 0   | 1     |
- As shown, the sum can be calculated with XOR - SUM(x, y) = x XOR y
- The carry can be calculated with AND - CARRY(x, y) = x AND y
![[Pasted image 20240919100522.png]]

- **Every aspect of building a computer derives from this ability to use gates to build arithmetic functions**
- To extend the half adder to a full adder
	- In addition to adding two bits and producing the result and a carry, a full adder can take in a carry from a previous column
	- Thus full adders can be chained together to add multi-bit numbers.
- Then we will see how to build an ALU
- Later we will also see how to build logic functions such as "if" by using the assembler to convert a program to a binary string.
---
# Full Adder #
- A full adder handles the complete calculation of one column of a binary addition.
- It has 3 inputs and 2 outputs.
- The truth table for a full adder is shown below.
![[Pasted image 20240919120511.png]]

- How can we change the half adder shown below to make it a full adder?
![[Pasted image 20240919120713.png]]

`SUM - FULL (x,y, carry-in) = SUM(SUM(x,y), carry-in) = (x XOR y) XOR c-in`
![[Pasted image 20240919120841.png]]

`CARRY-OUT (x,y, carry-in) = CARRY(x,y) OR CARRY(SUM(x,y), carry-in) = (x AND y) OR (SUM(x,y) AND carry-in)
![[Pasted image 20240919121048.png]]

- The equations above should match the truth table.
![[Pasted image 20240919121122.png]]

---
# Ripple-Carry Adder #

- Full adders can be connected in a series.
- The carry bit "ripples" from one adder to the next; hence, this circuit is called a *ripple-carry adder*
- Current computes use more complex circuits that are more efficient.
![[Pasted image 20240919121441.png]]
- The right-most full adder does not need a carry-in.
- However, from the point of view of manufacturing efficiency, it does not hurt to use a full adder with the carry-in set to 0.
	- You can do that by having no input to that item.
	- Or you could replace the right-most full adder by a half-adder.

![[Pasted image 20240919121647.png]]

---
- We've seen how to build a half adder from gates.
- Then we saw how to build a full adder from two half adders, and a ripple-carry adder from a series of full adders.
- In this section we will see how to build two key control circuits, **the decoder and the multiplexer**
- We will also see how to build a binary shifter, which shifts a binary number left or right one bit.
- Finally, we will put these pieces together to build a small ALU, or **arithmetic-logic unit**
---
# Decoders #

- Another important type of combinational circuit.
- Among other things, they are useful in selecting a memory location according a binary value placed on the address lines of a memory bus.
- Address decoders with *n* inputs can select any of $2^n$ locations
![[Pasted image 20240919151328.png]]
This is a block diagram for a decoder.

- The diagram below shows the internals of a 2-to-4 decoder.
![[Pasted image 20240919151416.png]]

- for example, the xy output is only true if x is true and y is true.
- Each AND gate has exactly two inputs.
- A decoder is used to convert a binary number (B'xy') to a value (0th, 1st, 2nd, 3rd output is true, counting from the bottom of the diagram).
- Given an address, a decoder can be used to access the memory cell at the address.
---
## Multiplexers

- A multiplexer, abbreviated *mux* is the opposite of a decoder.
- It selects a single output from several inputs.
- The particular input chosen for output is determined by the value of the multiplexer's control lines.
- To be able to select among *n* inputs, $log_2 n$ control lines are needed.
- This diagram shows the internals of a 4-to-1 multiplexer.
![[Pasted image 20240919151921.png]]

- Note that only one of the AND gates can be true at any given time.
- Each input $I_n$ is only connected to one of the AND gates. That AND gate is only true for a specific pair of values of $S_0$ and $S_1$. For example, the top one is true when $S_1 S_0$ = 0b11.
- Input $I_n$ is connected to the AND gate where the binary value $S_1 S_0 = n$. From top to bottom, the AND gates are connected to inputs #3,2,1 and 0.
- Each control input, $S_0$ and $S_1$, is provided in its original and negated form to make it easy to build the four AND gates.
- Since only one of the AND gates is true at any one time, we can OR together their values to get the value of the input ($I_0, I_2,$ or $I_3$) selected by the two S lines.
- A multiplexer can be used to send data from a given memory cell to a register. The memory address is given in $S_1 S_0$. 
---
## Shifter
- The shifter below moves the bits of a nibble one position to the left or right.
![[Pasted image 20240919153032.png]]

- If S = 1, we have a right shift, Output $O_2$ comes from input $I_3$.
- If S = 0, we have a left shift, Output $O_2$ comes from input $I_1$.
- Check out the OR gates to ensure only one input can be true at a time.
- Make sure you know how each of the four outputs is calculated for S = 0 and S = 1.
---
## A Two-Bit ALU

- Remember that the ALU, or arithmetic-logic unit, is a core part of the CPU that handles arithmetic and logic.
- We can use the combinational circuits we have learned to build an ALU. Our sample ALU (*see last slide for picture*) will handle four operations - AND, OR, NOT and addition - for two-bit numbers.
- The inputs are $A_1 A_0$ and $B_1 B_0$. The output is $C_1 C_0$.
- The control lines $I_0 I_1$ determine which operation will be done.
	- 00 = addition; 01 = NOT
	- 10 = OR; 11 = AND
- For AND and OR, make sure you can see how the righthand bits of A and B are channeled into the righthand bits of A and B are channeled into the righthand bit of C, and similarly for the lefthand bit.
- For NOT, make sure you can see how each bit of A is inverted before passing it into C.
- For A + B, make sure you can see how the rightmost bits go into the half-adder and the leftmost bits go into the full adder.
	- Also verify that the carry from the half-adder to the full adder, and the carry from the full adder to the overflow, are correctly passed along.
- Then check the control logic
- Make sure you can see how each of the four possible outputs of the decoder are AND'ed to the gates for the corresponding operation so that the result from only one operation is passed to the output.
	- Note that this is an additional use of a decoder. Earlier we saw how a decoder can be used to select one memory cell from a set of $2^n$ memory cells. Here we are selecting one operation from a set of $2^n$ operations.
- Finally, make sure you can see how the outputs from the different operations are OR'ed together to create a single output.
![[Pasted image 20240919171917.png]]
