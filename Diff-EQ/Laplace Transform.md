We're transforming $f(t)$, a function of time, to $F(s)$, a function of frequency.

### Example
Given $y'' + 3y' +2y = 0; y(0)=1; y'(0)=0$

We get $r^{2}+3r+2=0$ we get $r_{1}=-2, r_{2}=-1$, then find $y_{1}=C_{1}e^{-2t}+C_{2}e^{-t}$ and solve like normal

Orrrrr we can transform it using Laplace:
1. We multiply the whole equation by $e^{-st}$ and get $e^{-st}y'' +3e^{-st}y'+2e^{-st}=0$
2. Integrate each term by $\int_{0}^{\infty}$ 
3. If $Y(s)$ is the Laplace transform of $y(t)$
4. We get $(s^{2}Y(s)-s)+3(sY(s)-1)+2Y(s)=0$
5. $(s^{2}+3s +2)Y(s)=s+3 \rightarrow Y(s)=\frac{s+3}{s^{2}+3s +2}$
6. Now it's time for us to inverse Laplace!
7. First we find the poles in the denominator are $s=-2,s=-1$ 
8. Then we do a partial fraction decomposition and find $\frac{s+3}{s^{2}+3s +2}=\frac{A}{s+2}+\frac{B}{s+1}$
9. Solving fraction decomposition we find $\frac{-1}{s+2}+\frac{2}{s+1}$
10. Now we can inverse Laplace transform, and we find $y(t)=-e^{-2t}+2e^{-t}$


## Example 2
Given $y{''''}-y=0; y(0)=1; y'(0)=0; y''(0)=1; y'''(0)=0$
Transforms into $(s^{4}Y(s)-s^{3}-s)-Y(s)=0$
So $Y(s)=\frac{s^{3}+3}{s^{4} -1}=\frac{s}{s^{2}-1}$
We inverse Laplace transform to get back to our solved differential equation
$y(t)=\cosh(t)=\frac{e^{t}+e^{-t}}{2}$

