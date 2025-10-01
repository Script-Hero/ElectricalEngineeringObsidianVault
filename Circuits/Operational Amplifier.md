![[opamp_description.png]]

An operational amplifier (op-amp) is an amplifier that produces an output which is proportional to the [[Voltage]] difference between the input terminals.
# Characteristics
1. **Linear Input-Output Response, High Gain**
	1. Open-loop gain is $A$ 
		1. $v_o=A(v_p-v_n)$ when there is no load
	2. Ideal Op-Amp is $A=\infty$
2. **High Input Resistance**
	1. $R_i$
	2. Ideal is $\infty\Omega$
3. **Low Output Resistance**
	1. $R_o$
	2. Ideal is $0\Omega$  
4. **[[Power]] Source**
	1. DC, $\pm V_{cc}$
	2. Can be whatever
5. **Virtual Short Circuit**
	1. If an op-amp is operating in linear mode, $v_p=v_n$
- [[Voltage]] can never exceed $\pm V_{cc}$


# Solving Using Characteristics
- *Solve* as in:
	- Find $v_o$ as a function of $v_s$
	- Find the linear (non-saturating) range of $v_s$
![[opamp_characteristics_example.png]]
1. Use the *infinite input resistance* condition ($i_n=0$) and [[KCL]] at the inverting input to find $i_n=i_s+i_f=0$
2. Use the *virtual short circuit* condition ($v_p=v_n$) and the fact that, in this example, the non-inverting input is connected to ground ($v_p=0$) to find: $v_n=0\rightarrow i_s=\frac{v_s}{16k\Omega}$ and $i_f=\frac{v_o}{80k\Omega}$
3. Using the results from step 2 in the [[KCL]] equation from step 1, we find $\frac{v_s}{16k\Omega}+\frac{v_o}{80k\Omega}=0\rightarrow v_o=-5v_s$
4. From the $\pm Vcc$ we know that $-15<v_o<10$ to stay in linear range, therefore $-15 < -5v_s < 10\rightarrow -2<v_s<3$ is the linear range of $v_s$

# Configurations
1. [[Comparator Op-Amp]]
2. [[Inverting Amplifier]]
3. [[Summing Amplifier]]
4. [[Non-Inverting Amplifier]]
5. [[Difference Amplifier]]