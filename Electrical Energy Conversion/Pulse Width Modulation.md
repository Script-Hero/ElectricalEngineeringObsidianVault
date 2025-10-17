![[pwm.png]]

Convenient way to [[Control]] [[Voltage]] for generating variable [[Voltage]] frequencies and magnitudes
- Vary timing of switch to modulate pulse width (duty cycle)
- Higher duty cycle, average output [[Voltage]] is larger
- Amplitude of the output [[Voltage]] is controlled with modulating waveforms
	- Harmonics are at higher frequencies than square waves
	- Easy to design filtering
- With some filtering, PWM offers more sine-like output than square wave switching schemes

**Requirements**
- Reference signal (modulating or [[Control]] signal) -- sinusoidal signal
- Carrier Signal - triangular wave that controls the switching frequency
- **Switching is done by comparing a sinusoidal reference signal and a triangular carrier signal**
![[pwm_with_carrier.png]]


