With [[Inductors]] and [[Capacitors]] in our circuits, we need to solve [[First Order Differential Equations]] 

## General Approach
1. Use [[KVL]] / [[KCL]] to find the differential equation which describes the circuit
2. Use the physical initial state of the circuit to develop a set of initial conditions necessary to solve the differential equation
3. Solve the differential equation together with the initial conditions

## Finding the Differential Equation for an RL Circuit
![[example_rl.png]]
- For the inductor, $v=L\frac{di}{dt}$
- For the resistor $v=-iR$ 
- Since the resistor and inductor are in parallel, the voltages across them are the same:
	- $v=-iR=L\frac{di}{dt}\rightarrow \frac{di}{dt}+\frac R L i=0$
- We can also rewrite the resistor equation $v=-iR\rightarrow\frac{dv}{dt}=-R\frac{di}{dt}$
- $\frac{di}{dt}=\frac v L = -\frac 1 R \frac {dv}{dt}\rightarrow \frac{dv}{dt}+\frac R L v = 0$
	- Note that this is the same equation that the current satisfied

## Finding the Differential Equation for an RC Circuit
![[rc_example.png]]
- For the capacitor $i=C\frac{dv}{dt}$
- For the resistor $v=-iR\rightarrow\frac{dv}{dt}=-R\frac{di}{dt}$
- Since the voltage across the resistor and the capacitor are the same:
	- $\frac{dv}{dt}=\frac i C=-R\frac{di}{dt}\rightarrow\frac{di}{dt}+\frac 1 {RC}i=0$
- *Not shown, but voltage leads to the same differential equation*

## Finding the DEQ for 1st Order Circuits **with Sources**
*Adding sources may result in non-homogeneous ODEs*
![[first_order_with_source.png]]
- For the capacitor $i_C=C\frac{dv}{dt}$
- For the resistor $v=i_RR$
- Using [[KCL]] $i_s=i_R+i_C=\frac V R + C \frac{dv}{dt}\rightarrow\frac{dv}{dt}+\frac v {RC}=\frac{i_s} C$

