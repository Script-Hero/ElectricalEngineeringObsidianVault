# Simple Resistive Load
![[half_wave_rectifier.png]]
![[half_wave_rectifier_waveform.png]]
- $V_o=V_{avg}=\frac 1 {2\pi}\int\limits_0^\pi V_m\sin(\omega t)d(\omega t)=\frac{V_m}{\pi}$ 
- $I_o=\frac{V_o}{R}=\frac{V_m}{\pi R}$

# Capacitor Filter Version

![[half_wave_rectifier_cap_filter.png]]
![[half_wave_rectifier_cap_waveform.png]]
- $V_o(\omega t)=\begin{cases}V_m\sin(\omega t),&\text{[[Diode]] on} \\ V_\theta e^{-(\omega t-\theta)/\omega RC},&\text{[[Diode]] off}\end{cases}$    
- Bigger $C$ means smaller $\Delta V_o$ 
