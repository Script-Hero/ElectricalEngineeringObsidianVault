1. The Program Counter
	1. Programs are stored in the [[Memory]], as same as data (data is 64-bit long, **instructions are 32-bit long**)
	2. Instructions are executed **in sequence** (if no branch). To indicate which instruction is to be executed, we have a **program counter** to record the address of the instruction, abbreviated as **PC**.
	3. PC is a register
		1. Contains address of instruction to be executed
		2. Incremented after each instruction PC = PC + 4
		3. Written over during a branch or jump
2. Procedure
	1. If we change instructions after the program is written, even just changing a single line, the compiler needs to recompile and the assembler reassembles the entire program. To avoid this, people use **procedure**
	2. Procedure is a **subset** of instructions, just like a subroutine in the program. Procedure can be **stored separately**, each is **unlikely to change**, so need not to be recompiled and reassembled
	3. We can **call** the procedure when coming to the time to execute it, i.e., **give** the starting **address** of stored procedure to the **Program Counter**. Jump can do this ("Jump" to a new address).
3. Recursive Procedure
	1. A procedure that can call itself either directly or indirectly
	2. Recursive procedures can rapidly fill up the stack!
4. The Stack
	1. The order we save the return address (1) (2) (3)
	2. But the order we use the address is (3) (2) (1)
	3. Stack is Last in, first out (LIFO) or First is, Last out (FILO)
		1. As opposed to First in First Out (FIFO) for queue 
	4. **Push**: add an item onto the stack
	5. **Pop**: remove an item off the stack
	6. ![[stack_illustration.png]]
	7. We have a pointer pointing to the top of the stack called the **Stack Pointer**
		1. ![[stack_pointer_illustration.png]]
5. Save return address
	1. After the procedure execution is complete we should return to the main program
	2. To do that we need to know where we left the main program (so we know where to return to)
		1. Meaning I need the address of the next instruction after the procedure call
	3. If you just branch, you cannot return to that address
		1. Instead we use BL, which saves the return address into X30
		2. Then when we're done in our procedure, we can do BR X30 to execute the next instruction in the main procedure
6. Passing parameters
	1. Convention useful for programmers
	2. Need a set of [[Registers]] to pass arguments / parameters to a procedure
	3. If a procedure calls another procedure, these arguments are *also* saved on the stack
7. Frame pointer vs Stack pointer
	1. The frame pointer (FP or X29) points to the first doubleword of the frame, often a saved argument register
	2. The stack pointer (SP or X28) points to the top of the stack and is adjusted to make room for all the saved [[Registers]] and [[Memory]]-resident local variables
	3. *If there are no local variables on the stack the compiler will save time by not setting and restoring the frame pointer*
	4. When a frame pointer is used, it is initialized using the address in the stack pointer on a call, and the stack pointer is restored using the frame pointer
	5. ![[frame_pointer_illustration.png]]
8. [[Memory]] usage
	1. The user address space is set to $2^{39}$ of the potential $2^{64}$ total address space given a 64-bit architecture. 
	2. The stack pointer is initialized to (illegible) and grows *down* towards the data segment. 
	3. At the other end, the program code ("text") starts at (illegible). 
	4. The static data starts immediately after the end of the text segment.
	5. Dynamic data, allocaled by malloc in C, grows up towards the stack in an area called the *heap*
	6. ![[memory_allocation_illustration.png]]