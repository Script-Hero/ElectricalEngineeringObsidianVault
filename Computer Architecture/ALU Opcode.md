The 2-bit ALUOp [[Control]] bits the operation that ALU should perfrom. Under cetrain ALUOps, the ALU is not used, so the Opcode field is "don't cares".
![[aluop.png]]
The combination of the 2 ALUOp bits and the opcode field results in a 4 bit ALU [[Control]] signal called the Operation
![[alu_operation_table.png]]