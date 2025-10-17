![[buck_converter.png]]
Type of [[DC-DC Converters]]

# Key Equations
1. $\Delta i_{S_{on}}=\Delta i_{S_{off}}$
2. $\frac{\langle V_{in}-\langle v_{o}\rangle\rangle}{L}DT=-\frac{\langle v_o\rangle}{L}(1-D)T$
3. $V_o=DV_{in}$
# Analysis
1. Draw the circuit with switch closed ("on") & again with switch open ("off")
	1. Specify [[Current]] directions!![[buck_converter_analysis.png]]
2. When active switch is closed:
	1. [[Diode]] is reverse biased, thus open
		1. $v_L(t)=q(t)[V_{in}-v_o(t)]$
3. When active switch is open:
	1. Continuous [[Current]] Mode: inductor [[Current]] needs a path, thus is closed
		1. $v_L(t)=(1-q(t))(-v_o(t))$
4. Putting it all together with $\langle v_L(t)\rangle=0$
	1. $\langle v_L(t)\rangle =\langle q(t)(V_{in}-v_o(t))+(1-q(t))(-v_o(t))\rangle=0$
	2. $D[V_{in}-V_o]-(1-D)V_o=0$
	3. $V_o=DV_{in}$
5. How much of the inductor [[Current]] changes?
	1. $v_L=L\frac{di}{dt}=L\frac{\Delta i}{\Delta t}\rightarrow\Delta i=\frac{v_L}{L}\Delta t$
	2. The increase in the inductor [[Current]] during $S_{on}$ should be the same as the the decrease during $S_{off}$
		1. $\because\langle v_L(t)\rangle=0$ in S-S operation 
6. With $L$ and $C$ being sufficiently large
	1. $L$ behaves like a [[Current]] source
	2. $C$ behaves like a [[Voltage]] source
	3. $\langle v_L(t)\rangle=0$
![[Pasted image 20251001013450.png]]

