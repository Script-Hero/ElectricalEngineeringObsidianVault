A **Linker** is a system program that contains independently assembled machine language programs and resolves all undefined labels into an executable file. 

It takes all the independently assembled machine language programs and "stiches" them together


## Steps
1. Place code and data modules symbolically in memroy
2. Determine the address of data and instruction labels
3. Place both the internal and external references

Uses relocation information and **symbol table** to resolve undefined labels.
- Example: branch address. Determine [[Memory]] locations needed. Get absolute references, true locations.

Produces **executable files**, containing no unresolved references.

**Symbol table**: a table that matches names of labels to the address of the [[Memory]] [[words]] that instructions occupy

The assembler turns the assembler language program into an **object file** which is a combination of machine language instructions, data, and information needed to place instructions properly in [[Memory]].

**Executable file**: A functional program in the format of an **object file** that contains no unresolved reference. Can contain symbol tables and debugging information, may contain relocation information.