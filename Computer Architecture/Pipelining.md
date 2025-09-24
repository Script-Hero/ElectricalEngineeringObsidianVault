LEGv8 instructions classically take 5 stages:
1. **IF**: Instruction Fetch
	1. Fetch instruction from memory
	2. Read instruction is placed in the IF/ID register
	3. PC address is incremented by 4 and then written back into the PC to get ready for the next clock cycle
	4. This incremented address is also saved into IF/ID in case needed later for an instruction (like CBZ)
2. **ID**: Instruction decode and register file read
	1. Read registers and decode the instruction
	2. Sign extend the immediate field
	3. Store the register numbers for the 2 registers, the sign extended immediate, and the incremented PC addressees in ID/EX register
3. **EX**: Execution or address calculation
	1. Execute the operation or calculate an address
4. **MEM**: Data memory access
	1. Access an operand in data memory (if necessary)
5. **WB**: Write Back
	1. Write the result into a register (if necessary)

![[pipelined_datapath_.png]]
![[traditional_multi_clock_pipeline_diagram.png]]
These 5 stages have information move from left to right, with 2 exceptions:
1. The write-back stage, which places the result back into the register file in the middle of the datapath
	1. Can lead to data hazards
2. The selection of the next value from the PC, choosing between the (PC+4) and the branch address from the MEM stage
	1. Can lead to control hazards

These reverse data movements do not affect the current instruction, only instructions later in the pipeline.

![[pipelining_by_module.png]]
- By imagining each instruction has its own datapath, we can visualize what is happening while pipelining

To send the value from one stage of the pipeline to the next, we store it in a register. Imagine a register on each of the dotted lines:
![[pipelined_datapath_with_registers.png]]
# Speedup
Pipelining is where once an instruction clears a stage, the next instruction can do that stage, even if the first instruction isn't done executing yet.
- Instruction A proceeds to step 2, allowing Instruction B to take step 1, even though instruction A has 3 more steps to go before it's done executing

![[pipelining_comparison.png]]
- Pipelining improves performance by *increasing instruction throughput*, in contrast to *decreasing the execution time of individual instructions*
- Throughput is an important metric, because real programs execute billions of instructions
$$\text{Time between instructions}_\text{pipelined}=\frac{\text{Time between instructions}_\text{non-pipelined}}{\text{Number of Pipe Stages}}$$

LEGv8 has some advantages for pipelining:
1. All instructions are the same length
2. Small number of types of instruction formats
3. Memory operands only appear in loads and stores
	1. Meaning we can use the execute stage to calculate the memory address and then access the memory in the following stage


# Pipeline Hazards
Situations in pipelining **where the next instruction cannot execute in the following clock cycle**.

## Structural Hazard
When the hardware cannot support the **combination of instructions we want to execute in the same clock cycle.** 

## Data Hazard
When the **pipeline must be stalled because one step must wait for another to complete**. For example:
```
ADD X19, X10, X1
SUB X2, X19 X3
```
The SUB requires the result of the ADD (both are using X19), so we have to wait for the Write stage of the ADD instruction. Besides waiting, one solution is called **forwarding** or **bypassing**, where extra hardware (bypass registers) are used to send data early. In this case, we would save and forward the sum from the ALU as soon as the ALU step completes.

![[data_forwarding.png]]
- Data forwarding visualization

Forwarding only works if the resource required by the second step is "forward in time". If this would require sending data "backward in time", the only solution is to wait. 

![[stall_and_forward.png]]
- Stalling and forwarding to prevent "backward in time" pipelining

#### Example
Given the following C code:
```
a = b + e;
c = b + f;
```
We get the generated LEGv8 code:
```
LDUR X1, [X0,#0] // Load b 
LDUR X2, [X0,#8] // Load e 
ADD X3, X1,X2 // b + e
STUR X3, [X0,#24] // Store a 
LDUR X4, [X0,#16] // Load f 
ADD X5, X1,X4 // b + f 
STUR X5, [X0,#32] // Store c
```
There is a data hazard in both ADD instructions because of their respective dependence on the previous LDUR instruction. Forwarding eliminates many other potential hazards, such as the dependence of the first ADD on the first LDUR and any hazards for storing instructions. Moving up the third LDUR instruction to become the third instruction eliminates the data hazard for both ADD instructions:
```
LDUR X1, [X0,#0] 
LDUR X2, [X0,#8] 
LDUR X4, [X0,#16] // NEW, moved
ADD X3, X1,X2 
STUR X3, [X0,#24] 
ADD X5, X1,X4 
STUR X5, [X0,#32]
```
On a pipelined processor, this will complete two clock cycles faster than the original version.

## Control Hazards
Comes from needing to make a decision based on the result of one instruction while others are executing. If we branch in instruction A, but instruction B is already fetched from the the Instruction Memory before we evaluate the branching logic, then we won't execute the right instruction. 

Two solutions:
1. Stall on every conditional branch
2. Try to predict the outcome of the branch
	1. Sometimes we always predict the branch is not taken 
	2. Sometimes we keep a record of what has been taken in the past to predict better in the future 