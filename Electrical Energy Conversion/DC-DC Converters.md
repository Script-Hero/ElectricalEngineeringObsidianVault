# Analysis 
1. Assume CCM (inductor [[Current]] is continuous) and [[Voltage]] output is steady in terms of average value
2. $\langle V_{ind}\rangle=0$
3. $\langle I_{cap}\rangle=0$
4. Draw circuit with switch closed and [[Diode]] off vs switch open and [[Diode]] on
# Fundamentals
![[switching waveform.png]]
[[Electronic Switches]] in a DC-DC converter are controlled by a "switching signal" to create desired **Average Behavior**
- Duty Cycle ($D$) is the fraction of the switching period ($T$) when the switch is closed
	- $\langle q(t)\rangle =\frac{DT} T =D$
	- $0\leq D\leq 1$
### Assumptions
- Circuit is in continuous conduction mode (CCM)
	- Inductor [[Current]] is continuous
- Circuit is in steady state operation in terms of average value
	- **Average output [[Voltage]] is considered to be constant at $V_o$**
- Components are ideal
### Things not to do
- Connect DC *[[Voltage]] source* across an [[Inductors]]
	- Average [[Voltage]] across an inductor over a cycle is zero ($\langle v_{L}(t)\rangle =0$)
	- Similar to how an inductor is a "short" at DC
- Connect DC *[[Current]] source* across a [[Capacitors]]
	- Average [[Current]] through a capacitor over a cycle is zero ($\langle i_C(t)\rangle=0$)
	- Similar to how a capacitor is "open" at DC
# Motivation
![[dc_dc_motivation.png]]
- Suppose we are delivering [[Power]] from a positive [[Voltage]] source to any given load
	- "Load" could mean the AC grid, battery, machine, etc
- Suppose the load is resistor $R$
- With no converter, we'd connect the load directly across the PV terminals
- Since $R$ is fixed, $(V_L,I_L)\neq(V_M,I_M)$
	- **Meaning we are not delivering maximum available [[Power]] to the load**
	- We need a DC-DC Converter to do this

# Topologies
- [[Buck Converter]]
- [[Boost Converter]]
- [[Buck-Boost Converter]]
## Key Components
1. Energy Storage Device
	1. Inductor or Capacitor
2. [[Electronic Switches]]
	1. FETs, [[Diodes]]
3. [[Control]]
	1. Digital, analog
