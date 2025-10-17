![[diode.png]]
Simplest of [[Electronic Switches]]
- On / Off conditions determined by its [[Voltage]] and [[Current]]
- [[Current]] is only allowed to move in 1 direction
- When there is a sufficient positive [[Voltage]] ($V_d$) across the diode, the diode will conduct

## How to determine on/off state
1. Assume arbitrarily some On and Off states
2. Reconstruct the circuit using On state as "short" and Off state as "open"
	1. Retain the same [[Current]] and [[Voltage]] definitions when you replace the diode
3. Analyze the circuit
	1. Determine $i_d$ through each "short" and $V_d$ for each "open"
4. Check $V_d$ and $i_d$
	1. If $V_d>0$ for "open" then assumption is wrong. Go back to step 1 with the opposite guess
	2. If $i_d<0$ then assumption is wrong. Go back to step 1 with the opposite guess 