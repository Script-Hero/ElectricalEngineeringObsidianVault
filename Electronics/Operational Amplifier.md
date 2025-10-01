*These notes are from "[[Electronics]]" (ECEN 325) , see also [[Circuits/Operational Amplifier|Operational Amplifier]] from [[Circuits]] 1*

![[ideal-op-amp.png]]
An amplifier multiplies the the magnitude of the difference between 2 [[Voltage]] signals (in this simple example between $v_{in}$ and ground) by a constant factor $v_o=A_V\cdot v_{in}(t)$
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


# Differential Signals
![[single_vs_differential_signals.png]]
- As opposed to "single ended signals"
- **In a differentiating input circuit, the input [[Voltage]] is the difference between the 2 input voltages**
- The average of the 2 signals is the [[Common Mode Voltage]] and is important when considering op-amp characteristics
## Common Configurations
- [[Summing Amplifier]]
- [[Difference Amplifier]]
- [[Instrumentation Amplifier]]
### Using capacitors:
- [[Integrator Op Amp]]
- [[Differentiator Op Amp]]
- [[Sallen Key Topology]]