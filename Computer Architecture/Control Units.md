# ALU Control

The following ALUOp commands can [[Control]] the function of the ALU:

| ALU [[Control]] Line | ALU Function |
| ---------------- | ------------ |
| 0000             | AND          |
| 0001             | OR           |
| 0010             | add          |
| 0110             | subtract     |
| 0111             | pass input b |
| 1100             | NOR          |
- For LDUR and STUR instructions, we use the ALU to compute the memory address by addition.
- For R-type instructions, the ALU performs 1 of 4 actions (AND, OR, add, subtract) based on the 11-bit opcode field in the R-type instruction
- For CBZ, the ALU just passes the register input value

We generate the 4-bit ALU control signal using a small **control unit** that has:
- Inputs:
	- opcode field of the instruction
	- 2-bit control field called ALUOp:
		- $00$ = add, used for loads and stores
		- $01$ = pass input b, for CBZ
		- $10$ = to be determined by the operation encoded in the opcode field
- Outputs:
	- 4-bit signal that goes into the ALU Control Line

This multiple-stages of decoding, that is using multiple smaller application-specific control units, can reduce latency and increase the speed we can use for our clock cycles


| Instruction | ALUOp | Instruction Operation      | Opcode Field | Desired ALU action | ALU Control Input |
| ----------- | ----- | -------------------------- | ------------ | ------------------ | ----------------- |
| LDUR        | 00    | Load Register              | XXXXXXXXXXX  | add                | 0010              |
| STUR        | 00    | Store Register             | XXXXXXXXXXX  | add                | 0010              |
| CBZ         | 01    | Compare and Branch on Zero | XXXXXXXXXXX  | pass input b       | 0111              |
| R-type      | 10    | ADD                        | 10001011000  | add                | 0010              |
| R-type      | 10    | SUB                        | 11001011000  | subtract           | 0110              |
| R-type      | 10    | AND                        | 10001010000  | AND                | 0000              |
| R-type      | 10    | ORR                        | 10101010000  | OR                 | 0001              |
- We only care about the Opcode Field when the ALUOp is $10$

# Main Control
Note the structure of the 3 instruction classes:
![[instruction_classes_format.png]]
Where:
1. R-type instructions:
	1. Rm and Rn are source registers
	2. Rd is the destination register
	3. ALU function is in the opcode field and decoded by the ALU Controller
2. Load / Store Instructions:
	1. Opcode for load is $1986_\text{ten}$ and for store is $1984_\text{ten}$
	2. Rn is the base register that is added to the 9 bit address field to form the memory address
	3. For loads, Rt is the destination register for the stored value
	4. For stores, Rt is the source register that should be loaded into memory
3. Conditional branch on zero instructions:
	1. Opcode = $180_\text{ten}$
	2. Rt register is the source register being tested for zero
	3. 19-bit address field is sign-extended, shifted, and then added to the PC to compute the branch target address 

Some common observations about the instruction format that we use to construct the Datapath:
1. The opcode field is between 6 and 11 bits wide and found in bits 31:26 and 31:21
2. The first register operand is always in bit positions 9:5 (Rn) for both R-type instructions and for the base register for load and store instructions 
3. The other register operand is in 1 of 2 places:
	1. in bit positions 20:16 (Rm) for R-type instructions and it is in 4:0 (Rt) for register to be written by a load. 
	2. That is also the field that specifies the register to be tested for zero for CBZ instructions. 
	3. **Therefore, we need a multiplexor to select which field of the instruction is used to indicate the register number to be read** 
4. Another operand can also be a 19-bit offset for CBZ or a 9-bit offset for load and store
5. The destination register for R-type instructions (Rd) and for loads (Rt) is in bit position 4:0.

Using this information, we can add the Control unit, ALU Control unit, instruction labels, and extra multiplexor (for the Read Register 2 Number input of the register file) to the Datapath we've been constructing:
![[full_datapath.png]]
![[pipelined_datapath_with_control_signals.png]]
Where each control signal has the following role:

| Signal Name | Effect when Deasserted                                                          | Effect when Asserted                                                                                                          |
| ----------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Reg2Loc     | The register number for Read Register 2 comes from the Rm field (bits 20:16)    | The register number Read Register 2 comes from the Rt field (bits 4:0) (**Registers** unit)                                   |
| RegWrite    | None                                                                            | The register on the Write Register input is written with the the value on the Write data input (**Registers** unit)           |
| ALUSrc      | The second ALU operand comes from the second register file output (Read Data 2) | The second ALU operand is the sign-extended, lower 16 bits of the instruction (**ALU** unit)                                  |
| MemRead     | None                                                                            | Data memory contents designated by the Address input are put on the Read Data output (**Data Memory** unit)                   |
| MemWrite    | None                                                                            | Data memory contents designated by the address input are replaced by the value on the Write Data input (**Data Memory** unit) |
| MemtoReg    | The value fed to the register Write Data input comes from the ALU               | The value fed to the register Write Data input comes from Data Memory unit                                                    |
From this, we can create a truth table of the control lines based on the type of instruction:

| Instruction | Reg2Loc | ALUSrc | MemtoReg | RegWrite | MemRead | MemWrite | Branch | ALUOp1 | ALUOp0 |
| ----------- | ------- | ------ | -------- | -------- | ------- | -------- | ------ | ------ | ------ |
| R-Format    | 0       | 0      | 0        | 1        | 0       | 0        | 0      | 1      | 0      |
| LDUR        | X       | 1      | 1        | 1        | 1       | 0        | 0      | 0      | 0      |
| STUR        | 1       | 1      | X        | 0        | 0       | 1        | 0      | 0      | 0      |
| CBZ         | 1       | 0      | X        | 0        | 0       | 0        | 1      | 0      | 1      |

![[pipeline_control_signals.png]]
### Association with [[Pipelining]] Stages
1. **Instruction Fetch**
	1. No [[Control]] signals. We always read instruction [[Memory]] and write to the PC
2. **Instruction Decode / Register File Read**
	1. Reg2Loc: We need to select the correct register number for Read Register 2, selecting between either Rm (bits 20:16) or Rt (bits 4:0)
3. **Execution / Address Calculation**
	1. ALUOp: what operation we will execute with the ALU
	2. ALUSrc: if the second input to the ALU will be Read Data 2 or the sign-extended immediate
4. **[[Memory]] Access**
	1. Branch: set if the instruction is CBZ
	2. MemRead: set if the instruction is Load
	3. MemWrite: set if the instruction is store
5. **Write Back**
	1. MemtoReg: decides between sending the ALU result or [[Memory]] value to the register file
	2. RegWrite: which enables writing the chosen value



This table comes from the flow of information for each command:

### ADD X1, X2, X3
![[add_datapath_example.png]]
1. The instruction is fetched and the PC is incremented
2. Two [[Registers]], X2 and X3, are read from the register file; also, the main [[Control]] unit computes the setting of the [[Control]] lines during this step.
3. The ALU operates on the data read from the register file, using portions of the opcode to generate the ALU function 
4. The result from the ALU is written into the destination register X1 in the register file.

### LDUR X1, \[X2, offset]
![[ldur_example_datapath.png]]
1. An instruction is fetched from the instruction [[Memory]], and the PC is incremented.
2. A register (X2) value is read from the register file
3. The ALU computes the sum of the value read from the register file and the sign-extended 9 bits of the instruction (offset)
4. The sum from the ALU is used as the address for the data [[Memory]]
5. The data [[Memory]] from the [[Memory]] unit is written into the register file (X1)

### CBZ, X1, offset
![[cbz_example_datapath.png]]
1. An instruction is fetched from the instruction [[Memory]], and the PC is incremented.
2. The register, X1, is read from the register file using bits 4:0 of the instruction (Rt)
3. The ALU passes the data value read from the register file. The value of PC is added to the sign-extend, 19 bits of the instruction (offset) are shifted left by 2; the result is the branch target address
4. The Zero output signal from the ALU is used to decide which adder result to store in the PC (the PC + 4 address or the base_address + offset)

### B (Unconditional)
![[uncond_branch_datapath.png]]
To implement unconditional [[Branching]], we add an extra [[Control]] signal and an OR gate with the UncondBranch signal (the one we just added) and the output of (Branch AND AluZero) to the MUX, to switch the next instruction from (PC + 4) to the sign-extended lower 26 bits of the branch instruction.


# Full Control Signal Description
![[full_control_signal_description.png]]

