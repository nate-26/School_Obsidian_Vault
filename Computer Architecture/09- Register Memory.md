---

---
## Sequential Circuits

- Used anytime that we have a "stateful" application.
	- A stateful application is one where the next state of the machine depends on the current state of the machine and the input. 
- A stateful application requires both combinational and sequential logic.
- The following explain the operation of a **register, memory and a binary counter**.
---
## Register

The following Images show a 4-bit register consisting of D flipflops. You will usually see its block diagram instead.
![[Pasted image 20240925202311.png]]
*Block diagram below*
![[Pasted image 20240925202258.png]]

- This register maintains its state as the clock ticks because the value $ln_n$ is equal to the value of $Out_n$. 
- The small triangle in each flipflop represents the clock input. The clock is connected to each bit of the register.
---
## Memory

- The following is a picture of four words of memory.
	- Each word has 3 bits, represented in one column.
![[Pasted image 20240925202621.png]]

- A 4-word memory needs 2 selector lines to address the four words.
	- We need to know which word the data is going to or from.
	- Note that $S_1$ is the high-order bit even though it's shown on the right. Look carefully at the AND gates $S_0$ and $S_1$ feed into.
- When data is being written into memory, it comes from the 3 input bits on the left.
	- $ln_0$ is connected to bit 0 of each word, but the update only happens if the corresponding selector line is 1 (and the write enable bit is 1) when the clock ticks.
- When data is being read from memory (i.e., output), it goes into the 3 output bits on the right.
	- Each output bit contains the 'OR' of the corresponding output bits from the four words.
	- Only one of those bits can be true at any one time. That's the output bit from the word that is selected, i.e., the word whose number (address) is represented by the selector lines.
## Memory Read (i.e., output) does not require a clock tick.

- The output is always there. To get the data from the Q signals for each memory cell to Out only requires combinational logic. 
	- *Review picture on 3f-51 or characteristic table on 3f-51*
	- The clock isn't needed for combinational logic.

## Memory Write (i.e., input)

- Memory update (also input) only happens when the clock ticks.
	- That's the only time the clock bit in the lower left is on.
	- Input is sampled on the rising edge and the output is stable by the time of the falling edge.
- Also, memory update only happens when the write enable is on.
	- Memory can only be updated when the "write enable" bit is on. There is a write enable line that is AND-ed with the clock. Look for it in the left corner of the diagram above.
	- The clock ticks regularly, and there is always some value on the input lines (every bit is either 0 or 1 ), but we don't want to update memory every time the clock ticks.
	- So we only turn the write enable bit on when we want to update memory.
---
### Writing to memory example
- We will use bit 0 as an example. All 3 bits act the same way. 
- Input $ln_0$ is connected to bit 0 of each of the words.
- But the data in bi $ln_0$ does not flow to bit 0 of each word. It only flows to the word represented by the selector.
- Furthermore, the new value from $ln_0$ is only written when the clock ticks and write enable is on. (You can see the clock line and the write enable line AND-ed together, and that result AND-ed together with the selector line for the column.)
- If write enable is off or the particular word is not selected, the data in the memory remains the same. That's how a D flipflop works, and it's also what you'd expect from a computer memory. We want values to be stable unless updated.
---
### Reading memory example
- We will use bit 0 as an example again.
- Bit 0 of each word is AND-ed to the selector for that word number (i.e., that word's address.)
- So bit 0 of a given word is only output from the D flipflop it's stored in when the selector for that word is on.
- All of the bit 0's from the different words are OR'd together to form output bit $Out_0$, bit only one of them (the one from the selected word) will have a 1 in it.
- So the value of $Out_0$ will contain the value of bit 0 of the selected word, i.e., whatever is in the D flipflop. If the word has been updated during this clock cycle (as explained on the previous slide), $Out_0$ will contain the new value. Otherwise it will contain the old value. Again, that's what we expect from a computer memory.
---
## Memory Use
Example 1: Implementing $y = x$
- In binary, that is: `LOAD X; STORE Y`.
- First read the value of x from memory:
	- Load the address of x on the selector lines ($S_1 S_0$ on slide ch03g62)
	- Now the value of x will be available on the Out lines.
- Then, write the value of y into memory:
	- Load the address of y on the selector lines.
	- Load the new value of y (i.e., the value of x) on the $ln$ lines.
	- Turn on the write enable bit.
	- The next time the clock ticks, the new value of y will be loaded into the cells pointed to by the address of y.

Example 2: Implementing $y= x + 1$
- Basically the same as the previous slide.
- Just use the ALU on 3e40f to calculate $x+1$ (or any other expression) between the first and second steps on the previous slide. 
- Directions for using the ALU can be found on 3e40c.
---
## Counter
- A binary counter is another sequential circuit. Among other things, it can be used to keep track of how many cycles the clock has ticked. 
- This is a **4-bit counter**. It represents the 4-bit binary number $B_3 B_2 B_1 B_0$.
- It counts B'0000', B'0001', etc. Note that the high-order bits are at the bottom of the diagram.
- After it hits B'1111' it returns B'0000'. Now it can count forever.
![[Pasted image 20241002222655.png]]
- When the count enable line is on, a pulse is produced every time the clock ticks.
- The input is sampled on the rising clock edge and the output is stable at the time of the falling clock edge.
- The count enable line feeds into both J and K of the top flipflop.
- When `J=1` and `K=1` at a clock tick, the `JK` flipflop changes state, i.e., the output is the inverse of the previous output. Assuming the original value of $B_0$ was 0, it is now 1. The value of $B_0$ is also sent to the AND gate below it. So $B_3 B_2 B_1 B_0$ now equals B'0001'.
- When will $B_1$ flip to 1?
	- On the next clock pulse, the `J=1`, `K=1` input causes $B_0$ to flip from 1 to 0. At the same time, the 1 from $B_0$ is AND-ed with the 1 from the count enable line and sent to $B_1$, causing it to flip from 0 to 1. So $B_3 B_2 B_1 B_0$ now equals B’0010’.
- When will $B_2$ flip to 1?
	- Its input comes from an AND gate. One of the inputs is $B_1$, and the other is the AND of the clock enable line and $B_0$.
	- The clock enable is 1 during counting, so the relevant part is $B_0$.
	- In other words, $B_2$ will become 1 when $B_1$ = 1 and $B_0$ = 1, as we expect from a counter. So the value after B’0010’ is B’0011’, and the following value is B’0100’.
- When $B_3 B_2 B_1 B_0$ = B’1111’, the the largest value that the counter can hold has been reached.
- The next cycle will reset $B_3 B_2 B_1 B_0$ to B’0000’ (i.e., all four bits will flip).
- You can use a combinational circuit to add 1 to a number, but you need a sequential circuit, i.e., one that knows its previous value, to implement a counter.