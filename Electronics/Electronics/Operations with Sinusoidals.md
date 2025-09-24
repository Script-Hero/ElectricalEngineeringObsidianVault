## Complex Algebra for Sinusoids
We can represent $y(t)=A\cos(\omega t + \phi)$ as $Ae^{j(\omega t+\phi)}$
- Represented as $Ae^{j\omega t}e^{j\phi}$
- In rectangular form: $A[\cos(\omega t)+j\sin(\omega t)][\cos(\phi)+j\sin(\phi)]$
	- Split into time dependent and fixed time shift

### Convert Polar to Rectangular
Examples
1. $5e^{j\pi/6}=5\angle30\degree=4.33+j2.5$
2. $6+j8=\sqrt{6^2+8^2}\angle\arctan(\frac 8 6)=10\angle 53.13\degree=10e^{j(0.3273) \text{radians}}$

## Example
Consider $v_{sum}(t)=v_1(t)+v_2(t)=1\cos(\omega t +0\degree) + 1\cos(\omega t + 90\degree)=?$
![[adding_sinusoids.png]]
We use complex algebra to solve:
1. $1e^{j0\degree}+1e^{j90\degree}=1+j9+0+j1=1+j1=\sqrt{2}e^{j45\degree}$
2. $\sqrt{2}e^{j45\degree}=\sqrt{2}\cos(\omega t + 45\degree)$

We can visually solve for the frequency and period of the above signals:
1. $f=\frac 1 T =\frac 1 {4\text{ms}}=250\text{Hz}$ 
2. further, $\omega=2\pi f=2\pi250\text{rad/s}$

By superposition, for any desired $t$, $v_\text{sum}(t)=v_1(t)+v_2(t)$


