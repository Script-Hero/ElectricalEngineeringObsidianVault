A variation of [[Gradient Descent]] that considers only the error on one data point.
1. Pick a random data point
	1. i.e. $(x_*,y_*)$
2. Run an iteration of [[Gradient Descent]] on that data point
3. Update the weights
	1. $w(t+1)\leftarrow w(t)-\eta\nabla_w e(w,x_*,y_*)$

$$
E_\text{in}(w)=\frac 1 N \sum \limits_{n=1}^N\ln(1+e^{-1y_n\cdot w^Tx})=\frac 1 N \sum\limits_{n=1}^Ne(w,x_n,y_n)
$$

In the case of [[Logistic Regression]]:
$$w(t+1)\leftarrow w(t)+y_*x_*(\frac \eta {1+e^{y_*w^Tx_*}})$$

## Benefits
- The 'average' (over time) move is the same as [[Gradient Descent]] 
- Computation is $\frac 1 N$ cheaper per step
- Stochasticity helps escape local minima
- Simple
- Similar to [[Perceptron Learning Algorithm]]
