A square root approximation algorithm in quadratic time. 
$$
x_{n+1}=x_n-\frac{1}{2}\frac{x_n^2-S}{x_n}
$$
- Where $S$ is the value we want the square root of and $x_n$ starts off as an initial guess and is updated iteratively

# Heron Derivation 
Heron's Algorithm can be derived using [[Newton's Method]] as follows:

1. The desired value is $x=\sqrt{S}$ which is equivalent to $x-\sqrt S = 0\rightarrow f(x) = x^2 - S = 0$. 
	- It's important that $f(x)=0$ for Newton's Method
2. If $f(x) = x^2 -S$ then $f'(x)=2x$
3. Newton's Method states $x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}$
4. Heron's algorithm becomes $x_{n+1}=x_n-\frac{x_n^2-S}{2x_n}$


----


