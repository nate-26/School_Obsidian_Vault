## CPU Basics

- The computer's CPU fetches, decodes, and executes program instructions.
- The two principal parts of the CPU are the *Datapath* and the control unit.
	- The *Datapath* consists of an arithmetic-logic unit (ALU) and storage units (registers) that are connected by a data bus that is also connected to main memory.
	- Various CPU components perform sequenced operations according to signals provided by its control unit.
- Registers hold data that can be readily accessed by the CPU.
- They can be implemented using D flip-flops.
	- A 32-bit register requires 32 D flip-flops.
- The arithmetic-logic unit (ALU) carries out logical and arithmetic operations as directed by the control unit. 
- The control unit determines which actions to carry out according to the values in a program counter register and a status register.

---
## The Bus

- The CPU shares data with other system components by way of a data bus.
	- A bus is a set of wires that simultaneously convey a single bit along each line.
- Two types of buses are commonly found in computer systems: point-to-point, and multipoint buses.
- Each set of blue lines below is an example of a point-to-point bus.
![[{57C1807A-DA1A-484F-BD1E-68568059EC13}.png]]

- Buses consist of data lines, control lines, and address lines.
- Data lines convey bits from one device to another
- Control lines determine the direction of data flow, and when each device can access the bus.
- Address lines determine the location of the source or destination of the data.
- The address bus is used by the CPU to send addresses to the main memory for lookup.
- Memory uses the data bus to send back data from the desired address. The CPU also uses the data bus to send data to memory for updating the value at an address.
	- The CPU has a similar relationship to the 1/0 subsystem.
- All devices need the control bus.
![[{3A763CE9-14B1-41A2-A961-8B2783AF0E8B}.png]]
*Sample Computer Configuration*

- Because a multipoint bus is a shared resource, access to it is controlled through protocols, which are built into the hardware.
![[{52C04BE5-CC7B-49FA-94D9-E52C79EBE884}.png]]
*Multipoint Bus*

- What happens when more than one device wants to use the bus at the same time?
- Arbitration refers to the hardware algorithm (protocol) for resolving conflicts.
- **Daisy chain**: Permissions are passed from the highest-priority device to the lowest.
- **Centralized parallel**: Each device is directly connected to an arbitration circuit.
- **Distributed using self-detection**: Devices decide which gets the bus among themselves.
- **Distributed using collision-detection**: Any device can try to use the bus. If its data collides with the data of another device, it tries again.
