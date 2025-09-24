1. $$\text{CPU Time}=(\text{CPU clock cycles for program)}\cdot(\text{clock cycle time})$$
2. $$\text{Cycles per Instruction}=\frac{\text{Number of Cycles}}{\text{Instruction Count}}$$
	1. $$\text{Cycles per Instruction}=\sum\limits_{i=1}^n\text{Cycles per Instruction}_i\cdot\frac{\text{Instruction Count}_i}{\text{Instruction Count}}$$
3. $$\text{CPU Time}=\text{Instruction Count} \cdot \text{Cycles per Instruction} \cdot \text{Clock Cycle Time}$$
4. $$\text{Million Instructions per Second (MIPS)}=\frac{\text{Instruction Count}}{\text{Execution Time}}=\frac{\text{Clock Rate}}{\text{Cycles per Instruction}\cdot10^6}$$
5. $$\text{Million Floating Point Operations per Second (MFLOPS)}=\frac{\text{\# of Floating Point Operations}}{\text{Execution Time}\cdot10^6}$$
6. $$\text{Average Execution Time}=\frac 1 n\sum_i\text{Execution Time}_i$$
7. $$\text{Weighted Arithmetic Mean}=\sum_iw_i\cdot\text{Execution Time}_i$$
8. $$\text{Geometric Mean}=\sqrt[n]{\prod_i\frac{\text{Execution Time}_i}{\text{Execution Time}_{\text{ref}_i}}}$$
9. $$\text{Execution time after improvement}=\frac{\text{Exrecution time affected by improvement}}{\text{Amount of improvement}}+\text{Execution time unaffected}$$
	1. ![[execution_time_improvement.png]]


