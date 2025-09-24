![[ideal-op-amp.png]]
An amplifier multiplies the the magnitude of the difference between 2 voltage signals (in this simple example between $v_{in}$ and ground) by a constant factor $v_o=A_V\cdot v_{in}(t)$
- This configuration is *open loop*

## Characteristics
- $A_V\rightarrow\infty$ (Infinite open-loop gain)
- Infinite input impedance
- Zero output impedance
- Infinite speed
- $V_\text{Inverting Input} = V_\text{Noninverting Input}$ (virtual short circuit)

## Feedback
The output of the op-amp is fed back to either the inverting or non-inverting input (called closed-loop gain).
- Positive feedback causes the output of the op-amp to grow until it hits saturation
	- Good for some comparators but not very useful for us
- Negative feedback causes the output of the op-amp to *stabilize*
- 