
![[datapath_w_forward_unit_and_stall_unit.png]]

The two pairs of hazard conditions are:
1. 
	1. EX/MEM.RegisterRd = ID/EX.RegisterRn1
	2. EX/MEM.RegisterRd = ID/EX.RegisterRm2
2. 
	1. MEM/WB.RegisterRd = ID/EX.RegisterRn1
	2. MEM/WB.RegisterRd = ID/EX.RegisterRm2


## Example

Consider a sequence of LEGv8 assembly with many dependencies:
```
SUB X2, X1,X3 // Register X2 written by SUB
AND X12,X2,X5 // 1st operand(X2) depends on SUB
OR X13,X6,X2 // 2nd operand(X2) depends on SUB
ADD X14,X2,X2 // 1st(X2) & 2nd(X2) depend on SUB
STUR X15,[X2,#100] // Base (X2) depends on SUB
```

The last 4 instructions are all dependent on the result in register X2 of the first instruction. 

Data hazards become apparent when we use a diagram:
![[data_hazard_pipeline_demonstration.png]]
- The register value for X2 is being forwarded backwards in time, which is not possible


We detect the following hazards:
- The first hazard in the provided example sequence is between:
```
SUB X2, X1,X3 // Register X2 written by SUB
AND X12,X2,X5 // 1st operand(X2) depends on SUB
```
- Where we're trying to read X2 in the AND before we're done writing it in the SUB. This hazard can be detected when the AND instruction is in the EX stage and the prior SUB instruction is in the MEM stage, so this is hazard 1a: EX/MEM.RegisterRd = ID/EX.RegisterRn1 = X2

- Between the SUB and ORR is a type 2b hazard: MEM/WB.RegisterRd = ID/EX.RegisterRm2 = X2

- The two dependencies between on SUB-ADD are not hazards because the register file supplies the proper data during the ID stage of ADD 

- There is no data hazard between SUB and STUR because STUR reads X2 the clock cycle *after* SUB writes X2.

# Rules for Detecting Hazards (Forwarding Unit)
If we can take the data from any pipeline register and deliver it to the ALU, we can forward the correct data. We do this by adding additional multiplexors. 

This forwarding control will be in the EX stage, because that is where the ALU forwarding multiplexors are found. Therefore we must pass the operand register numbers from ID via ID/EX to check the rules for a hazard. Before this, Rn and Rm were not included in ID/EX. 

![[forwarding_unit_datapath.png]]
![[detect_data_hazards.png]]

Note that the EX/MEM.RegisterRd field is the register destination for either an ALU instruction (which comes from the Rd field of the instruction) or a load (which comes from the Rt field, but we'll use the notation Rd in this section)
## EX Hazards:
There is a **EX Hazard** if all the following are true:
1. EX/MEM.RegWrite is asserted
2. EX/MEM.RegisterRd $\neq$ 31, because 31 is always XZR (Zero register)
3. EX/Mem.RegisterRd = ID/EX.RegisterRn1
The response is to set ForwardA = 10

The second case for a **EX Hazard** is if all the following are true:
1. EX/MEM.RegWrite is asserted
2. EX/MEM.RegisterRd $\neq$ 31, because 31 is always XZR (Zero register)
3. EX/Mem.RegisterRd = ID/EX.RegisterRm2
The response is to set ForwardB = 10

This case forwards the result from the previous instruction to either input of the ALU. If the previous instruction is going to write to the register file, and the write register number matches the read register number of the ALU's first or second input, and provided that that input is not XZR, then steer the multiplexor to pick the value instead from the pipeline register EX/MEM


## MEM Hazards:
There is a **MEM Hazard** if all the following are true:
1. MEM/WB.RegWrite is asserted
2. MEM/WB.RegisterRd $\neq$ 31 because X31 is always XZR
3. MEM/WB.RegisterRd = ID/EX.RegisterRn1
4. NOT (EX/MEM.RegWrite and (EX/MEM.RegisterRd $\neq$ 31) and (EX/MEM.RegisterRd $\neq$ ID/EX.RegisterRn1))
The response is to set ForwardA = 01

The second case for a **MEM Hazard** is if all the following are true:
1. MEM/WB.RegWrite is asserted
2. MEM/WB.RegisterRd $\neq$ 31
3. MEM/WB.RegisterRd = ID/EX.RegisterRm2
4. NOT (EX/MEM.RegWrite and (EX/MEM.RegisterRd $\neq$ 31) and (EX/MEM.RegisterRd $\neq$ ID/EX.RegisterRm2))
The response is to set ForwardB = 01

There is no hazard in the WB stage because we assume that the register file supplies the correct result if the instruction in the ID stage reads the same register written by the instruction in the WB stage. 

Rule 4 of both cases is added to resolve an issue where the result should be forwarded from the MEM stage because it is the more recent value.
- For example, in repeated additions:
```
ADD X1,X1,X2 
ADD X1,X1,X3 
ADD X1,X1,X4
...
```

# Stalls
One case where forwarding cannot save the day is when an instruction tries to read a register following a load instruction that writes the same register:
![[stalling_diagram.png]]

The data is still being read from memory in clock cycle 4 while the ALU is performing the operation for the following instruction. 

Something must stall the pipeline for the combination of the load followed by an instruction that reads its result. This requires an additional *hazard detection unit*.

The *hazard detection unit* operates during the ID stage so that it can insert the stall between the load and the instruction dependent on it with the following condition. If
1. ID/EX.MemRead is asserted
2. (ID/EX.RegisterRd = IF/ID.RegisterRn1) **OR** (ID/EX.RegisterRd = IF/ID.RegisterRm2)
Then stall the pipeline 1 clock cycle.
- Without forwarding, we need more than 1 clock cycle

Since RegisterRd is the register in instruction bits 4:0 for both load and R-type instructions, the first line tests to see if the instruction is a load (the only instruction type that uses MemRead is load instruction).

The second line (OR statement) checks if the destination register of the load is either of the source registers for the instruction in the ID stage. After the stall, forwarding can handle the dependence and execution proceeds.

If the instruction in the ID stage is stalled, then the instruction in the IF stage must also be stalled, or else we would lose the fetched instruction. Stalling these 2 processes is accomplished by preventing the PC from changing and the IF/ID register from changing. 

So what if everything after ID doing? **Nops**, instructions that do nothing.
- We achieve this by deasserting all 8 control signals in ID/EX pipeline register. These get propagated forward and achieve NOP in EX, MEM, and WB as they get passed to each of those stages.

![[nop_bubble_insertion.png]]

![[datapath_w_forward_unit_and_stall_unit.png]]