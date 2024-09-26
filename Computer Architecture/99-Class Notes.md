## Sequential Circuits
- e.g., clocks, register, memory, counter
- Capable of storing memory, that is to change its current state based on previous and current input.
- State changes are controlled by clocks
	- A clock is a special circuit that "ticks" 
- There are multiple circuit types that change at different times of the wave
	- *In this class we will use a level circuit*
- To retain state values, seq circuits rely on *feedback*
- Feedback occurs when an output is looped back to the input
	- Called a feedback loop obviously
- SR flipflop:
	- set/reset
	- Has three inputs technically, set, reset and clock
	- Two outputs: Q and Q'
	- JK circuit will not be used because there are some undefined instances
- JK circuit:
	- J = set, K = reset
	- for 3/4 cases, same as SR
	- Only difference is when J =1 & K =1, making it equal to when J =0 & K =0.
	- Will be kept for building a computer
- D flipflop:
	- D is good for building register, memory and counter.
	- Built by sending D and D' into S and R of an SR flipflop
---
## Registers
- 4 bit memory
---
## Marie
- Imaginary machine we're building in class
- Has 16 bit words
- Every word has it's own number
---
## Memory
- Write Enable and the Clock get ANDed together and visit each D flipflop
- Different cases:
	- S0 = 0 & S1 = 0 -> Word 0 Select
	- S0 = 1 & S1 = 0 -> Word 1 Select
	- S0 = 0 & S1 = 1 -> Word 2 Select
	- S0 = 1 & S1 = 1 -> Word 3 Select
---
## Counter
