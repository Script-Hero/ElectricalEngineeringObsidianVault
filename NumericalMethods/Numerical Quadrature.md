- Approximates the definite integral of a function
- Uses a weighted sum of function values such that
$$
\int\limits_{a}^{b}f(x)dx=\sum\limits_{i=1}^{n}w_if(x_i)
$$

# Quadrature Rules

## Composite Quadrature Rules
#### Definition
Divide the integration interval $[a,b]$ into smaller subintervals and apply a simple quadrature rule on each subinterval.
#### Types
- [[Trapezoid Rule]]
- [[Simpson's Rule]]
- [[Gaussian Quadrature]]

#### Error
$E[f]=C\cdot h^p$ 
- $h$ is the width of each sub-interval
- $p$ is the order of accuracy of the quadrature rule
- $C$ is a constant depending on $f(x)$

Different quadrature rules have different error functions.

# Degree of Precision
The highest degree of polynomial for which a given quadrature rule gives an exact result. If a quadrature rule can integrate polynomials of degree $k$ or less exactly, its *degree of precision* is $k$.

## Evaluating degree of precision
For an unknown quadrature, you can determine the degree of precision by testing the provided quadrature on monomials ($f(x)=1,x,x^2,\dots$) to determine the highest degree it integrates exactly.

# Quadrature Error
The quadrature error is difference of the approximation and the true integral, $E[f]=\int\limits_{a}^{b}f(x)dx-\sum\limits_{i=1}^{n}w_if(x_i)$

### Interpolatory Quadrature
$$
E[f]=\frac{f^{(n)}(\xi)}{n!}\int\limits_a^b\prod\limits_{i=1}^{n}(x-x_i)dx
$$
Where
- $f^{(n)}(\xi)$ is the nth derivative of $f(x)$ evaluated at some point $\xi\in[a,b]$
- $\prod\limits_{i=1}^n(x-x_i)$ is the product of terms corresponding to the given interpolation points 

This is extremely similar to the [[Lagrange Interpolating Polynomial]] error.