Type of [[DC-DC Converters]] used to both lower and raise the input [[Voltage]].

![[buck_boost_converter.png]]
![[buck_boost_signals.png]]
# Analysis
1. When active switch is closed:
	1. [[Diode]] is reverse biased, and therefore open: $v_L(t)=q(t)(V_{in})$
2. When active switch is open:
	1. Continuous Conduction Mode: There needs to be a path for inductor [[Current]] to flow, therefore the [[Diode]] is closed: $v_L(t)=(1-q(t))[-v_o(t)]$
3. Putting is all together with $\langle v_L(t)\rangle=0$:
	1. $V_L(t)=\langle q(t)(V_{in})+(1-q(t))(-v_o(t))\rangle=0$
	2. $DV_{in}-(1-D)V_o=0$
	3. $V_o=\frac{D}{1-D}V_{in}$
4. How much of the inductor [[Current]] changes?
	1. $V_L=L\frac{di}{dt}=L\frac{\Delta i}{\Delta t}\rightarrow\Delta i=\frac{V_L}{L}\Delta t$
	