The program goes through the following steps:

1. **Instruction Fetch**: the *instruction* is *read from memory* using the address in the PC and then is placed in the IF/ID pipeline register. This stage occurs before the instruction is even identified.
2. **Instruction Decode and Register Read**: The instruction in the IF / ID pipeline register supplies the register numbers for *reading two registers* and *extends the sign of the 16-bit immediate*. These three 32-bit values are all *stored in the ID/EX pipelining register*. The type of instruction is still not known at this point.
3. **Execute and Effective Address Calculation**: the effective address is placed in the EX/MEM pipeline register.
4. **Memory**: the data is then *written to memory*. Note that the register containing the data to be stored was read in an earlier stage and then stored in ID / EX. The only way to make the data available during the MEM stage is to place the data into the EX/MEM pipeline register in the EX stage, just as we stored the effective address into EX/MEM.
5. **Write Back**: Writes the final result back into the *register file*.

### Some things to note:
- If a stage is not needed for an instruction, you still have to take the time to go through it, because there is the previous instruction still in the stage after it which is going as fast as it can.
- There are intermediary registers that pass the data between stages, like ID / EX are the registers between the *Instruction Decode* and *Execution* stages

![[pipelined_datapath.png]]
![[datapath_stages_hd.png]]
- The [[Datapath]] separated by stage.
- Intermediary registers pass the data along

**Timing must be handled correctly, or else there will be [[Data Hazards]] **
