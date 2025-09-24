If a circuit contains **more than 1 *independent* source** and only **linear components** 
- (linear meaning that if input $x_1$ produces output $y_1$ and input $x_2$ produces output $y_2$ then input $\alpha x_1 + \beta x_2$ produces output $\alpha y_1 + \beta y_2$) 

Then you can find the current or voltage across an element as the sum of the currents caused by each source.

## Methodology
1. Choose a power source
2. "Turn off" all other *independent* power sources by turning voltage sources to a short circuit and current sources to an open circuit
	1. Note that we must keep all *dependent* sources in the circuit still
3. Find the current (or voltage) across the element using any method
4. Repeat for all power sources
5. Sum the currents (or voltages) to find the value in the circuit
