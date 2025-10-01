A Wheatstone Bridge is a circuit used to measure the value of an unknown resistor $R_x$ 

![[wheatstone_bridge.png]]
- (Where $R_3$ is a potentiometer)

The resistance of the potentiometer $R_3$ is varied until the ammeter (amp measuring device, the arrow in the center of the circuit) shows *no [[Current]] between nodes $a$ and $b$* (which equivalently means there is no [[Voltage]] drop either).

This implies:
- $I_1=I_3$
- $I_2=I_x$
- $R_1I_1=R_2I_2$
- $R_3I_3=R_xI_x$

From which we can solve for $R_x$:
$$
R_x=R_3\frac{I_3}{I_x}=R_3\frac{I_1}{I_2}=\frac{R_3R_2}{R_1}
$$

