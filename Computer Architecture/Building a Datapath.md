# Datapath Elements


## General Elements
### Program Counter (PC)
- Register that holds the address of the [[Current]] instruction 
### Program Counter Adder
- Increments the address held in the PC by 4
- Built from the ALU by wiring [[Control]] lines so that the [[Control]] always specifies the add operation
- We draw it as a little "add" block to specify it has permanently been made an adder and cannot perform any other ALU instructions
- Different from our regular general purpose ALU

![[access_instructions_path.png]]
- The PC is a register written to at the end of every clock cycle
	- Always writes $\rightarrow$ no write [[Control]] signal necessary
- The instruction [[Memory]] always reads, never writes
	- Can be treated as combinational not state element
#### To execute any instruction, we must start by fetching the instruction from memory. To prepare for executing the next instruction, we must also increment the program counter so that it points to the next instruction (4 bytes later)

## R-Type Elements

### Register File
- Contains all [[Registers]]
	- Any register can be read from or written to
- Required for all R-Type (Arithmetic-Logic Type) instructions, like ADD, SUB, ORR, etc. 
	- R-types require reading 2 [[Registers]], performing ALU operation on the contents of those [[Registers]], and then writing the result to a register 
- To read:
	- We need an input to specify the *register number* to read from
	- Need an output that will carry the word that has been read from the register file
	- No need to wait for clock, the register file is always outputting whatever the *register number* input is selecting, even if we don't need to use it at that time
- To write:
	- Need an input to specify the *register number* to write from
	- Need an input with the data (word) to be written
	- Writes are controlled by the *write [[Control]] signal* which must be asserted while the clock is edging
- In total requires:
	- 3 register number inputs (5 bits for $2^5=32$ different [[Registers]])
		- Read register 1
		- Read register 2
		- Write destination register
	- 1 write [[Control]] signal inputs


## LDUR and STUR Elements 
- Consider $\text{LDUR X1, [X2, offset\_value]}$ and $\text{STUR X1, [X2, offset\_value]}$
- These instructions compute a [[Memory]] address by adding the base register ($\text{X2}$ in these examples) to the **9-bit signed offset field** contained in the instruction
	- To add a 9 bit number (offset) to a 64 bit number (base register address) we must sign-extend the 9 bit number to a 64 bit number 
- If the instruction is a store, **the value to be stored must be read** from the register $\text{X1}$
- If the instruction is a load, **the value to be read from [[Memory]] must be written** into the register $\text{X1}$

## CBZ Elements
- $\text{CBZ}$ instruction has 2 inputs: the register that is being compared against zero, and a 19-bit offset
- For CBZ the offset field is shifted left 2 bits so that it is a word offset
	- Increases the effective range of the offset field by a factor of 4
	- To deal with this we must shift the offset field by 2
		- We can just concatenate $00$ to the branch offset for this
- Offset is sign extended and added to PC to calculate the destination of the branch
- We use the Zero signal from the ALU to test if the input register is equal to 0 (and therefore trigger [[Branching]])
### Data Memory Unit
- Read from or write to [[Memory]]
- Inputs are: *read [[Control]] signal*, *write [[Control]] signal*, *address input*, *data input bus*
### Sign Extend Unit
- Input is a 32-bit bus and output is a 64 bit bus
- Used to do a signed extension of either the 19 bit CBZ offset or 9 bit LDUR/STUR offset and convert it to a 64 bit number so we can add it to the other 64 bit [[Registers]] in our program

![[simple_datapath_unit.png]]
A [[Datapath]] for conditional [[Branching]]:
- Uses the ALU to evaluate the branch condition
- Separate adder to compute the branch target as the sum of the PC and the sign-extended 19 bits of the instruction (the branch displacement / offset)
	- Shifted left 2 bits
	- Note that there is no actual shift hardware needed because the shift amount is always 2 

![[r_type_datapath_.png]]
A [[Datapath]] for R-type instructions and [[Memory]] instructions:
- Sign extender used for the offset
- ALU used for address calculation (for LDUR and STUR)

We can combine these two Datapaths, to build **a [[Datapath]] for conditional [[Branching]], R-type instructions, and [[Memory]] instructions**:
![[combined_datapath.png]]