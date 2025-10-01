
## Parallel RLC Circuit
![[parallel_rlc_circuit.png]]
Since the *[[Voltage]]*, $V$, is common to all three elements it is natural to find an equation for $V$.
1. Using [[KCL]]: $I_C+I_L+I_R=0$
2. $C\frac{dV}{dt}+ \frac 1 L \int{V(t)dt} +\frac{V(t)} R = 0$
3. After deriving we get $C\frac{d^2V}{dt} + \frac{V(t)} L + \frac 1 R \frac{dV}{dt}=0$
4. Dividing by $C$ and rearranging: $\frac{d^2V}{dt^2}+\frac 1 {RC}\frac{dV}{dt}+\frac{V(t)}{LC}=0$

We can also solve for the *[[Current]]* across a component, like $I_L$.
1. Using [[KCL]] $I_C + I_L + I_R=0$
2. $LC\frac{d^2I_L}{dt^2}+I_L+\frac L R \frac{dI_L}{dt}=0$
3. Dividing by $LC$ we get $\frac{d^2I_L}{dt^2}+\frac{I_L(t)}{LC}+\frac 1 {RC} \frac{dI_L}{dt}=0$

**In summary, we find that all currents and voltages in the *parallel* RLC circuit satisfies $\frac{d^2y}{dt^2}+\frac{1}{RC}\frac{dy}{dt}+\frac{y(t)}{LC}=0$**

## Series RLC Circuit
![[series_rlc_example.png]]
We follow the same procedure as the parallel case.
1. Using [[KVL]] $V_C+V_L+V_R=0$
2. $\frac 1 C \int I(t)dt + L\frac{dI}{dt}+RI(t)=0$
3. Derive for $\frac{I(t)}{C}+L\frac{d^2I}{dt^2}+R\frac{dI}{dt}=0$
4. Divide by $L$ and rearrange: $\frac{d^2I}{dt^2}+\frac R L \frac{dI}{dt}+\frac{I(t)}{LC}=0$

**In summary, all currents and voltages satisfy this second-order equation: $\frac{d^2y}{dt^2}+\frac R L \frac{dy}{dt} + \frac{y(t)}{LC}=0$ *Note that it is different from the parallel RLC case.***

## RLC with Sources
![[rlc_with_sources.png]]
When [[Power]] sources are involved the differential equations are often *non-homogeneous*.
1. Using [[KCL]]: $V_C+V_L+V_R=V_S$
2. Using the relations: $I=C\frac{dV_C}{dt}\rightarrow V_C=\frac 1 C \int I(t)dt$, $V_L=L\frac{dI}{dt}$, $V_R=IR$
3. **If $V_S(t)$ is a constant (DC Source) then $\frac{dV_S}{dt}=0$ and the equation is homogenous.**
4. $\frac 1 C \int I(t)dt+L\frac{dI}{dt}+RI(t)=V_S$
5. $\frac{d^2I}{dt^2}+\frac R L \frac{dI}{dt}+\frac{I(t)}{LC}=\frac 1 L \frac{dV_S}{dt}$
