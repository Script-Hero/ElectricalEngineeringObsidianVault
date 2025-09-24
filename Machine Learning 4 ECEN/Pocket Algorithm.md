Method for maximizing fit on **non-separable data.**
- Meaning minimizing [[In-Sample Error]]
- Which hopefully minimizes [[Out-Of-Sample Error]]
	- See [[2 Step Approach to getting E_out approx 0]]
## Idea
- Run [[Perceptron Learning Algorithm]]
- At each step keep the best $E_\text{in}$ and $w$ so far.

## Algorithm
PLA but at each step keep the best $E_\text{in}$ and $w$ so far.
1. Set the pocket weight vector $\hat{w}$ to $w(0)$ of PLA 
2. **for** $t=0,\dots,T$ **do**
	1. Run PLA for one update to obtain $w(t+1)$
	2. Evaluate $E_\text{in}(w(t+1))$
	3. If $w(t+1)$ is better than $\hat{w}$ in terms of $E_\text{in}$, set $\hat w$ to $w(t+1)$ 
3. Return $\hat w$

