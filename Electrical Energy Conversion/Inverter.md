DC-AC [[Electrical Energy Conversion]] of desired magnitude and frequency
# Topologies
- [[Half-Bridge Inverter]]
- [[Full-Bridge Inverter]]
- [[Multi-Level Inverter]]
- [[Three-Phase Inverter]]

# Real-Life Nonidealities
- Real Switches
	- Cannot turn on and off instantaneously
	- A little bit of [[Voltage]] drop
	- ![[diode_nonidealities.png]]
- Shoot-through fauls
	- Due to overlap of switch ON times
	- Resulting in a short circuit across the DC [[Voltage]] source
	- Therefore switching transition times must be considered
- Blanking (Dead) time
	- Time delay between switching actions to prevent shoot-through faults

# With [[Pulse Width Modulation]]
**Requirements**
- Reference signal (modulating or [[Control]] signal) -- sinusoidal signal
- Carrier Signal - triangular wave that controls the switching frequency
- **Switching is done by comparing a sinusoidal reference signal and a triangular carrier signal**
## Bipolar Switching
![[pwm_with_carrier.png]]
![[bipolar_switching.png]]
- $v_o=+V_{dc}$ for $V_{sine}>V_{tri}$
	- On switches $S_1$ and $S_2$
- $v_o=-V_{dc}$ for $V_{sine}<V_{tri}$
	- On switches $S_3$ and $S_4$


# Applications
- Uninterruptible [[Power]] supplies (UPS)
- Adjustable-speed AC motor drives
- Running AC appliances from an automotive (car) 
- Photovoltaic solar panels to the grid or to houses
- Electric vehicle batteries to the grid