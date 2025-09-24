
$\hat y = w_0 + w_1\cdot x_1 + w_2 \cdot x_2 + \dots + w_d\cdot x_d$
- Where $\vec x$ is a single sample and $x_i$ is the ith feature of $\vec x$

In matrix notation, we can represent the linear regression model as:

- $X=\begin{bmatrix} x_1\\x_2\\\vdots\\x_N\end{bmatrix}$
	- Input features, a matrix of size $N\times(d+1)$ 
	- Here $x_1$ is the first sample, and $x_1$ is a vector of size $d+1$ ($x_0=1$ always)
- $y=\begin{bmatrix}y_1\\y_2\\\vdots\\y_N\end{bmatrix}$

We make predictions: $$\hat y = \begin{bmatrix}\hat y_1 \\ \hat y_2 \\ \vdots \\ \hat y_N\end{bmatrix}=\begin{bmatrix}w^Tx_1\\w^Tx_2\\\vdots\\w^Tx_N\end{bmatrix}=Xw$$

## Error
The linear regression algorithm gets the smallest possible $E_\text{in}$ in *one step*.

The [[In-Sample Error]] is $\frac 1 N \sum \limits_{n=1}^N(\hat{y_n}-y_n)^2$
- In matrix notation, this reduces to $E_\text{in}(w)=\frac 1 N (w^TX^TXw-2w^TX^Ty+y^Ty)$
- $\nabla_wE_\text{in}(w)=\frac 2 N (X^TXw-X^Ty)$
- To minimize $E_\text{in}(w)$ we set $\nabla_wE_\text{in}(w)=0$
	- $X^TXw=X^Ty$
	- If $X^TX$ is invertible then $w_\text{lin}=(X^TX)^{-1}X^Ty$


## Algorithm
1. Construct the matrix $X$ and the vector $y$ from the data set $(x_1,y_1),\dots,(x_N,y_N)$ where each $x$ contains the $x_0=1$ coordinate
2. Compute the inverse or pseudo-inverse $X^\dagger$ of the matrix $X$. If $X^TX$ is invertible:
	1. $X^\dagger=(X^TX)^{-1}X^T$
	2. **This is the *closed form solution***
3. Return $w_\text{lin}=X^\dagger y$

