For every instruction, the first two steps are identical:
1. Send the **Program Counter** (PC) to the [[Memory]] that contains the code and fetch the instructions from that [[Memory]]
2. Read one or two [[Registers]], using fields of the instructions to select the [[Registers]] to read.
	1. For the $\text{LDUR}$ and $\text{CBZ}$ instructions, we need to read only one register
	2. All other instructions we need to read 2

After these first two steps, the actions required to complete the instruction depend on the instruction class. **For each of the three instruction classes** ([[Memory]]-reference, arithmetic-logical (R-type instructions), and branches) **the actions are largely the same regardless of the exact instruction**.

For example, all instruction classes except the unconditional branch use the arithmetic logic unit (ALU) after reading the [[Registers]].
- [[Memory]] reference use ALU for address calculation
- Arithmetic-logical (R-type instructions) use ALU for operation execution
- Conditional branches use ALU for comparison to 0

After using the ALU, actions required differ. 
- [[Memory]]-reference instruction will need to access [[Memory]] to either *read data for a load* or *write data for a store*
- Arithmetic-logical or load instruction must write the data from the ALU or [[Memory]] back into a register
- For conditional-branch, we may need to change the next instruction address based on comparison, otherwise the PC is increased by 4 to get the normal subsequent instruction

![[basic_datapath.png]]

**Multiplexors** are used to [[Control]] which of multiple inputs are sent to the different units:
- The top multiplexor determine whether the value sent to the PC is either (the [[Current]] PC + 4) or (the target branch address).
	- The input to this MUX is the Zero output from the ALU, which is used for comparison of a $\text{CBZ}$ instruction.

The **[[Control]] Unit** has the instruction as an input, and determines how to set the [[Control]] lines for the functional units and two of the multiplexors.

# Note that this is a simplified implementation. More control units and connections must be added. Additionally, everything happens during a single clock cycle, which is inefficient.