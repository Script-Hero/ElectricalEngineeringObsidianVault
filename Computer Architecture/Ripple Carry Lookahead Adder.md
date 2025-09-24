For binary [[Addition and Subtraction]]. 

Delay time $\alpha f(n)$ where:
- $n$ is the number of bits
- $\alpha$ is the gate delay 

# Procedure
1. $g_i=a_i\cdot b_i$
	1. *generate*
2. $p_i=a_i+b_i$
	1. *propagate*
3. $g_i=1$ if the adder generates a $\text{Carry}_\text{out}$ independent of $\text{Carry}_\text{in}$
4. $p_i=1$ if the adder propagates a $\text{Carry}_\text{out}$ to $\text{Carry}_\text{in}$

## Example
1. $C_1=b_0c_0 + a_0c_0 + a_0b_0$
	1. $=(b_0+a_0)c_0+a_0b_0$
	2. $=p_0c_0+g_0$
2. $C_2=b_1c_1+a_1c_1+a_1b_1$
	1. $=(b_1+a_1)c_1+a_1b_1$
	2. $=p_1c_1+g_1$
	3. $=p_1(p_0c_0+g_0)+g_1$
	4. $=p_1p_0c_0+p_1g_0+g_1$
3. $\dots$
4. $C_8=p_7p_6\dots p_0c_0$
	1. $+p_7p_6\dots p_1g_0$
	2. $+p_7p_6\dots p_1g_0$
	3. $+p_7p_6\dots p_2g_1$
	4. $+p_7p_6\dots p_3g_2$
	5. $+\dots$
	6. $+p_7g_6$
	7. $+g_7$
### Benefits
- All the $p_i,g_i$ can be obtained simultaneously. 
- All the $C_i$ will be known after a short gate delay
- $C_i$ is not dependent on $C_{i-1}$

