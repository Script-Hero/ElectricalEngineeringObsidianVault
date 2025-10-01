Configuration of [[Circuits/Operational Amplifier]] circuit that causes the op-amp to saturate if the input [[Voltage]] exceeds a certain value.

# Theory
If the op-amp differential input $v_p-v_n$ exceeds a certain small threshold, $v_o$ saturates to $+V_{cc}$ and if it is below a small threshold $v_o$ saturates to $-V_{cc}$.
![[opamp_comparator.png]]


## Positive Feedback Comparator (Schmitt Trigger) (Inverting Comparator)
![[Schmitt Trigger.png]]
- When the differential input is small, the vanilla comparator will have floating / ambiguous output. 
- To fix, feedback from the output and a feedback resistor $R_f$ are connected to an input
	- Feedback on **$v_p$** increases output level
	- Feedback on $v_n$ decreases output level
- a **positive feedback** comparator is called a Schmitt Trigger and ignores small input variations ($v_p-v_n\approx 0$) in the range $V_{LT} < (v_p-v_n) < V_{UT}$ where $V_{LT}$ is the "lower trigger voltage" and $V_{UT}$ is the "upper trigger voltage"
	- $v_s$ (the comparison voltage) is connected to the negative pin
	- $v_p=\frac{R_i}{R_i+R_f}v_o$ due to the voltage divider between $R_i$ and $R_f$
	- So $v_{UT}=\frac{R_i}{R_i+R_f}V_{cc}$ 
	- $v_{LT}=\frac{R_i}{R_i+R_f}(-V_{cc})$
- While $v_{s}>V_{LT}$ the output $v_o=-V_{cc}$ but when $v_s=V_{LT}$ the output $v_o=+V_{cc}$
- The *hysteresis* or noise margin $\Delta V_{T}=V_{UT}-V_{LT}$ is what the Schmitt trigger ignores

##  Noninverting Schmitt Trigger
![[Noninverting Schmitt Trigger.png]]
 - Both $v_s$ (the comparison [[Voltage]]) and the feedback resistor $R_f$ are connected to the $v_p$ pin
 - $V_{UT}=\frac{R_i}{R_f}(+V_{cc})$ and $V_{LT}=\frac{R_i}{R_f}(-V_{cc})$
 - When $v_p$ goes from below $V_{UT}$ to above $V_{UT}$ the output becomes $+V_{cc}$
 - When $v_p$ goes from above $V_{LT}$ to below $V_{LT}$ the output becomes $-V_{cc}$
