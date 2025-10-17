![[boost_converter.png]]

![[boost_converter_analysis.png]]
![[boost_converter_signals.png]]
# Analysis
1. When active switch is open:
	1. $v_L(t)=(1-q(t))[V_{in}-v_o(t)]$ 
2. When active switch is closed:
	1. [[Diode]] is reverse biased, thus open: $v_L(t)=q(t)(V_{in})$
3. Putting it all together with $\langle v_L(t)\rangle=0$
	1. $\langle v_L(t)\rangle =\langle q(t)(V_{in})+(1-q(t))[V_{in}-v_o(t)]\rangle=0$
	2. $DV_{in}+(1-D)[V_{in}-V_o]=0$
	3. $DV_{in}+V_{in}-DV_{in}-V_o+DV_o=0$
	4. $V_o=\frac{V_{in}}{1-D}$
4. How much of the inductor [[Current]] changes?
	1. $V_L=L\frac{di}{dt}=L\frac{\Delta i}{\Delta t}\rightarrow \Delta i=\frac{V_L}{L}\Delta t$

With $L$ and $C$ being sufficiently large:
- $L$ behaves like a [[Current]] source
- $C$ behaves like a [[Voltage]] source
- Still $\langle v_L(t)\rangle=0$