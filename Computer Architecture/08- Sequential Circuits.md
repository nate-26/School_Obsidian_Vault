## Combinational Logic Circuits
- Perfect for situations when we require the immediate application of a Boolean function to a set of inputs.
- There are other times, however, when we need a circuit to change its value with consideration to its current state as well as its inputs.
	- These circuits have to “remember” their current state.
- Sequential logic circuits provide this functionality for us.
---
## Clocks
- As the name implies, sequential logic circuits require a means by which events can be sequenced.
- State changes are controlled by clocks.
	- A “clock” is a special circuit that sends electrical pulses through a circuit.
- Clocks produce electrical waveforms such as the one shown below.
![[Pasted image 20241002224301.png]]

---
## State Changes
- Occur in sequential circuits only when the clock ticks.
- Circuits can change state on the rising edge, falling edge, or when the clock pulse reaches its highest voltage.
![[Pasted image 20241002224336.png]]

- Circuits that change state on the rising edge, or  falling edge of the clock pulse are called edge-triggered.
- Level-triggered circuits change state when the clock voltage reaches its highest or lowest level.
- In general, the circuits that we will look at will get their inputs on the rising edge.
- By the time of the falling edge, the output will be stable and we can use it.
---
## Feedback
- To retain their state values, sequential circuits rely on feedback.
- Feedback in digital circuits occurs when an output is looped back to the input.
- A simple example of this concept is shown below.
- If Q is 0 it will always be 0. If it is 1, it will always be 1.
![[Pasted image 20241002224554.png]]

---
## SR Flipflop
- You can see how feedback works by examining the most basic sequential logic components, the SR flipflop.
	- The “SR” stands for set/reset.
- The block diagram for an SR flipflop is shown below along with its characteristic table.
![[Pasted image 20241002224639.png]]
- For those who are interested, the diagram below shows the internals of the SR flipflop.
- To understand basic computer architecture, we can consider flipflops as fundamental units, just as we treat gates, i.e., we don’t need to know their internals.
![[Pasted image 20241002224733.png]]
- The SR flipflop actually has three inputs: S, R, and its current output, Q.
- Thus, we can construct a truth table for this circuit, as shown below.
- Notice the two undefined values.  When both S and R are 1, the SR flipflop is unstable.
![[Pasted image 20241002224809.png]]

---
## JK Flipflop
- If we can be sure that the inputs to an SR flipflop will never both be 1, we will never have an unstable circuit.
- The SR flipflop can be modified to provide a stable state when both inputs are 1.
- This modified flipflop is called a JK flipflop, shown at the right.
	- The “JK” is named after  Jack Kilby.

![[Pasted image 20241002224948.png]]

- At the right, we see how an SR flipflop can be modified to create a JK flipflop.
- The characteristic table indicates that the flipflop is stable.
- When J and K are both 1, the JK flipflop changes its output from the preceding value.
![[Pasted image 20241002225115.png]]

---
## D Flipflop

- Another modification of the SR flipflop is the D flipflop, shown below with its characteristic table.
- The output of the D flipflop remains the same during subsequent clock pulses. The output changes only when the value of D changes.
- A D flipflop is built by sending D and D’ into the S and R inputs of an SR flipflop.
![[Pasted image 20241002225210.png]]

- Since its value is constant unless the input changes, the D flipflop is the fundamental circuit of computer memory.
	- D flipflops are usually illustrated using the block diagram shown below.
	- In addition to D, the clock input is needed as for any sequential circuit.
	- It is convenient but not required to output both Q and Q’.

![[Pasted image 20241002225310.png]]