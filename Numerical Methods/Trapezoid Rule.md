Type of [[Numerical Quadrature]] that approximates the area under the curve using trapezoids

$$
\int\limits_a^bf(x)dx\approx\frac{b-a}{2}[f(a)+f(b)]
$$
# Error and Accuracy
- $E[f]=-\frac{(b-a)h^2}{12}f''(\xi)$ where $\xi\in[a,b]$
- Order of accuracy $O(h^2)$
- Degree of precision 1
# Solving ODEs
The trapezoid rule is also an implicit [[Numerical Solutions of ODEs]] in the form:
$$
y^{(n+1)}=y^n+\frac{h}{2}[f(t^{(n)},y^{(n)})+f(t^{(n+1)},y^{(n+1)})]
$$
Which is a combination of the [[Forward Euler Method]] and the [[Backward Euler Method]]
