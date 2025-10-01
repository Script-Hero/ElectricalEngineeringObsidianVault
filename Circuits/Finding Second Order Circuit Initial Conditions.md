*To* find initial conditions we start with the physical state of the circuit, typically **initial currents in [[Inductors]]** and **initial voltages in [[Capacitors]]** because these things to do not change instantly when the switches are flipped.

Usually:
$$i(0)=a,\frac{di}{dt}(0)=b$$
or
$$v(0)=a,\frac{dv}{dt}=b$$

Where $a$ and $b$ are constants. 


## Examples
*From [[Finding Second Order Circuit Equation]]*
### Parallel RLC Circuit
![[parallel_rlc_circuit.png]]
We found the differential equation describing this circuit was $\frac{d^2V}{dt^2}+\frac 1 {RC}\frac{dV}{dt}+\frac{V(t)}{LC}=0$

Suppose we know the initial conditions $I_L(0)$ and $V_C(0)$
- Then finding the initial [[Voltage]] is trivial: $V(0)=V_C(0)$
- To find $\frac{dV}{dt}(0)$ we try to use the *capacitor [[Current]]* since $I_C(t)=C\frac{dV}{dt}$
	- Using [[KCL]] $I_C+I_L+I_R=0\rightarrow C\frac{dV}{dt}+I_L+\frac{V(t)}{R}=0$
	- $\frac{dV}{dt}(0)=-\frac{I_L(0)}{C}-\frac{V_C(0)}{RC}$

### Series RLC Circuit
![[series_rlc_example.png]]
We found the equation $\frac{d^2I}{dt^2}+\frac R L \frac{dI}{dt}+\frac{I(t)}{LC}=0$. To solve this one, we need to know $I(0)$ and $\frac{dI}{dt}(0)$

Suppose we know the initial conditions $I_L(0)$ and $V_C(0)$
- Finding the initial [[Current]] is trivial, $I(0)=I_L(0)$
- To find $\frac{dI}{dt}(0)$ we try to use the *inductor [[Voltage]]* since $V_L(t)=L\frac{dI}{dt}$
	- Using [[KVL]]: $V_C+V_L+V_R=0\rightarrow V_C+L\frac{dI}{dt}+RI(t)=0$
	- $\frac{dI}{dt}(0)=-\frac R L I_L(0)-\frac{V_C(0)} L$

