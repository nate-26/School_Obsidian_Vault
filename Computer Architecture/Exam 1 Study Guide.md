### **Part I: Conceptual Questions on History**
- [[06- Computer History#Stored Program Computer|Stored Program Computer]]: What is it?
   - Stores the program so that you can change the program without changing the machine.
- Important figures: [[06- Computer History#Generation 1|Atanasoff, Mauchley, and Eckert]]
	- **Atanasoff Berry Computers** 
		   - John Atanasoff & Clifford Berry
	- **Electronic Numerical Integrator and Computer, e.g., ENIAC** 
		- John Mauchly and J. Presper Eckert
- [[06- Computer History#Generation 2|Transistors vs. Vacuum Tubes:]]
	- Why transistors were an improvement?
		- Transistors were more reliable than vacuum tubes.
- [[06- Computer History#Generation 3|Integrated Circuits]] and [[06- Computer History#Generation 4| and VSLI]]:
	- Integrated Circuits were an improvement over transistors because they took less space.
	- Definition of VLSI: Very Large Scale Integration
		- Had more than 10,000 components per chip
	- Impact of VLSI on computer design: 
		- Enable the creation of microprocessors
-  **IBM's Business Decisions**:
	- Architectural decisions contributing to IBM's success:
		- Backwards compatibility & Upgrade Path
-  [[06- Computer History#Backwards Compatibility|Backwards Compatibility]]:
	- The ability of a new machine to run software intended for the previous generation.
-  [[06- Computer History#Moore’s Law (1965)|Moore's Law]]
	- Concept and its limitations.

---

### **Part II: Gates**
- **Gate Symbols & Truth Tables**:
	- [[01-Boolean Algebra#AND & OR|AND & OR]]
	- [[01-Boolean Algebra#NOT|NOT]]
	- [[05-Logic Gates#**Three Basic Gates**|AND, OR & NOT]]: gate symbols
	- [[05-Logic Gates#**XOR Gate**|XOR Gate]]
	- [[05-Logic Gates#**NAND and NOR Gates**|NAND & NOR]] 
- **Boolean Algebra**:
	- [[01-Boolean Algebra#Order of Operations|Order of operations]] and symbols.
	- Number of [[04-Truth Tables|truth table]] rows with *n* variables.
		- One row for each possible value of the set of variables in the expression
	- [[03-Canonical Forms|Sum-of-Products Form]]: how to derive it and its usefulness.
- **Boolean Identities**:
	- [[02-Boolean Identities#**Identity Table **|Identity Table]]
	- [[02-Boolean Identities#**The Identity Law**|The Identity Law]]
	- [[02-Boolean Identities#**The Null Law**|The Null Law]]
	- [[02-Boolean Identities#**The Idempotent Law**|The Idempotent Law]]
	- [[02-Boolean Identities#**The Commutative Law**|The Commutative Law]]
	- [[02-Boolean Identities#**The Associative Law**|The Associative Law]]
	- [[02-Boolean Identities#**The Associative Law**|The Associative Law]]
	- [[02-Boolean Identities#**The Distributive Law**|The Distributive Law]]
	- [[02-Boolean Identities#**Absorption Law**|The Absorption Law]]
	- [[02-Boolean Identities#**DeMorgan's Law**|DeMorgan's Law]]
	- [[02-Boolean Identities#**Double Complement Law**|Double Complement Law]]
-  **Dual of an Expression**:
	- Definition and significance.
- **Universal Gates & Associativity of NAND**:
	- [[05-Logic Gates#**NAND is Universal**|NAND & NOR]] as universal gates and their usefulness.
	- Demonstrating lack of associativity using truth tables.

---

### **Part III: Combinational Circuits**
- [[07-Combinational Circuits#Half Adder|Half Adder]]:
	- Black box representation and bit addition.
- [[07-Combinational Circuits#Full Adder|Full Adder]]:
	- Differences from half adder and black box representation.
	- Implementation using two half adders.
- **Adder for 2-Bit Binary Numbers**:
	- Full adder configuration for binary numbers.
- [[07-Combinational Circuits#Ripple-Carry Adder|Ripple Carry Adder]]:
	- Inputs, outputs, and black box representation.
	- Components of ripple-carry adder.
- [[07-Combinational Circuits#Decoders|Decoders]]:
	- Purpose and black box diagram.
	- Input-output configuration for an 8-bit decoder.
- [[07-Combinational Circuits#Multiplexers|Multiplexers]]:
	- Purpose and black box diagram.
	- Input-output configuration for an 8-selection-line multiplexer.
- [[07-Combinational Circuits#Shifter|Shifters]]:
	- Purpose, control lines, and input-output lines for an 8-input shifter.
- [[07-Combinational Circuits#A Two-Bit ALU|Arithmetic Logic Unit (ALU)]]:
	- Operations it handles, control/data lines, and output.

---

### **Part IV: Sequential Circuits**
- **Sequential vs. Combinational Circuits**:
	- Differences and need for a clock line:
		- [[09- Register Memory#Sequential Circuits|Sequential Circuits]] are needed anytime there is a "stateful" application
- [[08- Sequential Circuits#Clocks|Clock Line]]:
	- Relationship to state changes in a sequential circuit.
	- Rising edge, falling edge, edge-triggered, and level-triggered circuits.
- [[08- Sequential Circuits#Feedback|Feedback]]:
	- Its purpose and usefulness.
- **Flipflops**:
	- [[08- Sequential Circuits#SR Flipflop|SR]]
	- [[08- Sequential Circuits#JK Flipflop|JK]]
	- [[08- Sequential Circuits#D Flipflop|D]]
- **Characteristic Table**:
	- Differences from truth tables
		- **Truth Table**: shows how a logic circuits output responds to various combination of inputs
		- **Characteristic Table**: defines the next state of flip-flop in terms of flip-flop input and current state
- [[09- Register Memory#Register|Register Building]]
	- Flipflops as building blocks, number of flipflops needed for an n-bit register.
- [[09- Register Memory#Memory|Memory]]:
	- Selector lines, write enable bit, and flipflop requirements for memory.
- [[09- Register Memory#Counter|Counters]]:
	- Flipflop requirements for counters and count enable lines.

---

### **Additional Notes**:
- Review the **homework problems**, especially ones you answered incorrectly.
- Memorize **Boolean identities** and the black box representations of components like adders, multiplexers, and decoders.
- Be prepared to **read circuit diagrams** without provided keys (like 3e-37b).
