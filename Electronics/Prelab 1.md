
# Calculations

## Question 1
### Transfer function for Low Pass Filter
$$H_{LP}(s)=\frac{V_{LP}}{V_i}(s)=\frac{R_2}{R_1+R_2}\cdot\frac{1}{1+\frac{s}{\omega_L}}=\frac{R_2}{R_1+R_2}\cdot\frac{1}{1+\frac{s}{\frac{R_1+R_2}{R_1R_2C_1}}}$$
Where $\omega_L=\frac{R_1+R_2}{R_1R_2C_1}$ and $K_L=\frac{R_2}{R_1+R_2}$

### Transfer function for High Pass Filter
$$H_{HP}(s)=\frac{V_{HP}}{V_i}(s)=\frac{C_2}{C_2+C_3}\cdot\frac{s}{s+\omega_H}=\frac{C_2}{C_2+C_3}\cdot\frac{s}{s+\frac{1}{R_3(C_2+C_3)}}$$
Where $\omega_H=\frac{1}{R_3(C_2+C_3)}$ and $K_H=\frac{C_2}{C_2+C_3}$

## Question 2
$f_c=4\text{kHz}\rightarrow \omega_c=2\pi f_c = 2\pi \cdot 4000 \text{rad/s}$

### Low Pass
$K_L=\frac{R_2}{R_1+R_2}=0.6$ , selecting $R_1 = 10\text{k}\Omega$ then $R_2=15k\Omega$ . $\omega_L=\frac{R_1+R_2}{R_1R_2C_1}=\frac{1}{6000 C_1}=\omega_c=2\pi\cdot 4000\rightarrow C_1=6.63\text{nF}$ 

### High Pass
$K_H=\frac{C_2}{C_2+C_3}=0.6\rightarrow C_2 = 1.5C_3$ . Selecting $C_3=10 \text{nF}\rightarrow C_2=15 \text{nF}$ .
$\omega_H=\frac{1}{R_3(C_2+C_3)}=\frac{1}{R_3\cdot 25 \cdot 10^{-9}}=\omega_C=2\pi\cdot4000\rightarrow R_3=1.59\text{k}\Omega$ 


## Question 4
$$|H_{LP}|=\frac{K}{\sqrt{1+(f/f_c)^2}}$$
$$\angle H_{LP}=-\tan^{-1}(f/f_c)$$
and
$$|H_{HP}|=\frac{K(f/f_c)}{\sqrt{1+(f/f_c)^2}}$$
$$\angle H_{HP}=90\degree-\tan^{-1}(f/f_c)$$

For $V_i(t)=0.7\sin(2\pi \cdot 3000t)$:
- $|H_{LP}|=0.48$ and $\angle H_{LP}=-36.9\degree\rightarrow V_{LP}(t)=0.336\sin(2\pi \cdot 3000t - 0.644)\text{V}$
- $|H_{HP}|=0.360$ and $\angle H_{HP}=53.1\degree\rightarrow V_{HP}(t)=0.252\sin(2\pi\cdot3000t+0.927)\text{V}$


## Question 5
For $V_i(t)=0.8\sin(2\pi\cdot5000t)$:
- $|H_{LP}|=0.3748$ and $\angle H_{LP}=-51.3\degree\rightarrow V_{LP}(t)=0.3\sin(2\pi\cdot5000t-0.896)\text V$
- $|H_{HP}|=0.4685$ and $\angle H_{HP}=38.7\degree\rightarrow V_{HP}(t)=0.375\sin(2\pi\cdot5000t+0.675)\text V$
