- We want to select $g\in H$ (the [[Perceptron Hypothesis Set]]) so that $g\approx f$
- Ideally, $g(x_n)=y_n$
	- Minimizes [[In-Sample Error]]

The idea behind the [[Learning Algorithm]] is to randomly initialize some weight vector $w$ and then try to improve it.

## Algorithm
1. $w(1)=0$
2. **for** iteration $t=1,2,3,\dots$
	1. the weight vector is $w(t)$
	2. From $(x_1,y_1),\dots,(x_N,y_N)$ pick any misclassified example
	3. Call the misclassified example $(x_*,y_*)$
		1. Meaning $\text{sign}(w(t)\cdot x_*)\neq y_*$
	4. Update the weight
		1. $w(t+1)=w(t)+y_*x_*$
		2. Note that $y_*$ is always $\pm1$
	5. $t\leftarrow t+1$

**"Incremental Learning" on a single example at a time.**

**If the data *can* be fit by a linear separator, then after some *finite* number of steps, PLA will find one.**
