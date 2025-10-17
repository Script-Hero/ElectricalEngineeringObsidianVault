**Harmonic**
- Multiple of the fundamental frequency
- Occurs due to non-linear loads causing [[Power]] quality issues

**Total Harmonic Distortion**
- Quantifies how non-sinusoidal (distorted) a waveform is
- Ratio of the RMS value of all the non-fundamental frequency terms over the fundamental frequency term

$$\text{THD}=\sqrt{\frac{I_{0,\text{rms}}^2+I_{2,\text{rms}}^2+I_{3,\text{rms}+\cdots}^2}{I_{1,\text{rms}}^2}}=\cdots=\sqrt{\frac{I_\text{rms}^2-I_{1,\text{rms}}^2}{I_{1,\text{rms}}^2}}\geq0$$

If a sinusoidal [[Voltage]] source is applied to a nonlinear load, the [[Current]] waveform will not be sinusoidal.

For example:
![[nonlinear_circuit.png]]
Causes the following electrical [[Current]] output harmonics:
![[thd_ouput_harmonics.png]]

# Importance
THD causes:
- Interference with communications
- Distorts source [[Voltage]]
- Heats up transformers, motors, generators, etc

How to reduce THD?
- Add filters
- Modify circuit's [[Frequency Response]] by filters, [[Inductors]], or [[Capacitors]]
- Reduce harmonic currents by the load