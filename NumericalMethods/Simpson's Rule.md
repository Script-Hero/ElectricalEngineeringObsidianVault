[[Numerical Quadrature]] that uses parabolic segments to approximate an integral.
$$
\int\limits_a^bf(x)dx\approx\frac{b-a}{6}[f(a)+4f(\frac{a+b}{2})+f(b)]
$$
# Error and Accuracy
- $E[f]=-\frac{(b-a)h^4}{180}f^{(4)}(\xi)$ with $\xi\in[a,b]$
- Order of accuracy $O(h^4)$
- Degree of precision = 3
