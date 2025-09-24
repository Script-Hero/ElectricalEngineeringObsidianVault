An explicit one-step [[Numerical Solutions of ODEs]] defined as 
$$
y_{n+1}=y_n+hf(t_n,y_n)
$$
Where:
- $y_n$ is an approximation of the solution of the ODE at $t_n$ 
- $h$ is the step size
- $f(t,y)$ is the derivative function $\frac{dy}{dt}$
# Stability
To guarantee numerical stability:
$|1+h\lambda_i| < 1,\space\forall i$ 
- Where $\lambda_i$ is an eigenvalue
#### Complex Eigenvalues
For complex eigenvalues we take the *modulus*. For imaginary number $\lambda_i = a+ib$:
1. $|1+h\lambda_i|<1$
2. $\sqrt{(1+ha)^2+(hb)^2}<1$
3. Continue as normal