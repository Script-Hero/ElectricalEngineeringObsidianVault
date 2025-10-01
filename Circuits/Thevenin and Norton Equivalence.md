If we are only interested in knowing the [[Voltage]] or [[Current]] between 2 nodes, we can reduce an arbitrarily complex circuit into one with a single **[[Voltage]] source *in series* with a resistor**.
![[thev_eq.png]]
- The "open circuit [[Voltage]]" $V_{OC}=V_{TH}$ and the "short circuit [[Current]]" $I_{SC}=\frac{V_{TH}}{R_{TH}}$ 

We can also do this with a **[[Current]] source *parallel* with a resistor**.

![[norton_eq.png]]
- $V_{OC}=I_NR_N,I_{SC}=I_N\rightarrow I_N=I_{SC},R_N=\frac{V_{OC}}{I_{SC}}=R_{TH}$

## Methods for Solving
### Method 1
Use [[Source Transformations]] and [[Equivalent Resistance]] combinations to reduce a circuit to its Thevenin or Norton equivalent

### Method 2
Find the open circuit [[Voltage]] and the short circuit [[Current]], then use: $$V_{TH}=V_{OC},I_N=I_{SC},R_{TH}=R_N=\frac{V_{OC}}{I_{SC}}$$
### Method 3
- For [[Circuits]] with no dependent sources, $R_{TH}$ can be found by disabling all independent sources (turning [[Voltage]] sources into short [[Circuits]] and [[Current]] sources into open [[Circuits]]) and computing the [[Equivalent Resistance]] across the load terminals
	- Note that this method only finds $R_{TH}$ and you have to use Method 2 to solve the rest of the circuit 
- For [[Circuits]] *with* a dependent source, disable all independent sources, then apply a "test source" to the load (either $V_T$ or $I_T$) and then solve for either $V_T$ or $I_T$ (whichever you didn't apply as the test source) to calculate $R_{TH}$
![[thev_nort_dep_sources.png]]