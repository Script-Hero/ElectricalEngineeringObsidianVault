Given:
- Input vector $x=[x_1,\dots,x_d]^T$
- Model weights weights $w=[w_0,\dots,w_d]$ 
	- $w_0$ is the bias term
	- $w\in R^{d+1}$

We can compute some output $o=\sum\limits_{i=1}^dw_ix_i$
- If $o>\text{threshhold}$ then the prediction is $1$
- If $o<\text{threshold}$ then the prediction is $0$
- $w_0$ can change the threshold by being the y-intercept

This can be written formally as $$h(x)=\text{sign}((\sum\limits_{i=1}^d w_i x_i)+w_0)$$
## Weight Importance
- If $|w_i|$ is large then the input $x_i$ (feature $i$) is important
- if $w_i>0$ then $x_i$ is *positively* correlated with a prediction of 1
- if $w_i<0$ then $x_i$ is *negatively* correlated with a prediction of $1$

