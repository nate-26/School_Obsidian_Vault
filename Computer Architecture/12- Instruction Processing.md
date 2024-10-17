## The Fetch-Decode-Execute Cycle

- The series of steps that a computer carries out when it runs a program.
- We first have to fetch an instruction from memory, and place it into the IR.
- Once in the IR, it is decoded to determine what needs to be done next.
- If a memory value (operand) is involved in the operation, it is retrieved and placed into the MBR.
- With everything in place, the instruction is executed.
![[{CD775F71-648C-4975-B31E-38BDE1AE841D}.png]]
*Flow Chart of the process*

- The fetch-decode-execute cycle is sometimes called the fetch-decode-fetch-execute cycle.
	- That’s because after you decode an instruction, you may have to fetch data from one or memory addresses, depending on the format of the instruction.

---
### A Simple Program

- Consider the simple MARIE program given below. We show a set of mnemonic instructions stored at addresses 100 - 106 (hex):
![[{E77E9819-8083-4AA0-BB4C-A769208E69BA}.png]]
- Explanation of chart on preceding slide:
	- First column: address of that line of program
	- Second column: instruction in words
	- Third column: instruction encoded in binary
	- Fourth column: instruction encoded in hex
- Things to notice
	- First nibble of instruction is op code; the rest is address
	- Op code is 4 bits, so fits in one nibble
	- Address is 12 bits, so needs 3 nibbles
	- The data in 104 - 106 isn’t important; program will work with any data. Data for Marie is in 2’s complement form.
- Let’s look at what happens inside the computer when our program runs. This is the LOAD 104 instruction.
- For each line, make sure you understand what happens in each column. Changes are highlighted in blue.
![[{113FF1C3-9456-4722-AD3D-1F6B461E1C8C}.png]]

- RTN = register transfer notation, a synonym for RTL.
- The RTN on each line tells you which register is updated and where the new value comes from.
- The line in parentheses means that the RTN “branches” according to which instruction was decoded.
- That line needs no RTN because it uses combinational logic.
- That instruction will be executed in the execute step. Here it is the ‘load’ instruction.
- Our second instruction is ADD 105.
- The fetch, decode and “get operand” (i.e., fetch the data) steps are the same.
![[{34486B65-8E08-4C74-B7BF-470AE81ABEFA}.png]]
- The only thing that is different is the execute, since the instruction is ‘add’ instead of ‘load’.
- The AC now has the value of AC + MBR. Remember that MARIE has 2’s complement addition.