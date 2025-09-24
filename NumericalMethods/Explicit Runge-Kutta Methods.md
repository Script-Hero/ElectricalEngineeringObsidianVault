A family of explicit iterative [[Numerical Solutions of ODEs]] with higher accuracy than basic methods.
# General Form
An $s$-stage explicit Runge-Katta method for solving $y'=f(t,y)$ is given by:
1. Compute intermediate stages of $k_i\forall i\in1,\dots,s$
	1. $k_1=f(t_n,y_n)$
	2. $k_2=f(t_n + c_2h, y_n + h(a_{21}k_1)$
	3. $k_3 = f(t_n + c_3h, y_n+h(a_{31}k_1+a_{32}k_2))$
	4. $\dots$
	5. $k_s=f(t_n+c_sh,y_n+h\sum\limits_{j=1}^{s-1}a_{sj}k_j$
2. Then update the solution:
	1. $y_{n+1}=y_n+h\sum\limits_{i=1}^sb_ik_i$
	2. Where $h$ is the step size

# Butcher Tableau
Compact way to represent the coefficients of a Runge-Kutta method, organizing the $a_{ij}$, $b_i$, and $c_i$ coefficients in a tabular format.

$$
\begin{array}
{c|cccc}
c_1 & a_{11} & a_{12} & \dots\\
c_2 & a_{21}& a_{22} & \dots\\
\vdots &\vdots &\vdots &\ddots \\
c_s& a_{s1}& a_{s2}& \dots\\
\hline
& b_1 &b_2 & \dots & b_s 
\end{array}
$$
- This *encodes* a method for solving a Runge-Kutta problem. 
- https://en.wikipedia.org/wiki/Runge%E2%80%93Kutta_methods
