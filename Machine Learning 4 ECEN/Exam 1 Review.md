
**Expect ~25 problems, no more than 2 minutes per problem, 50 minute exam.**
- Problems won't be dependent on each other
- Don't get hung up on just one problem because there are so many
- Multiple choice exam on Canvas

---
*(Reverse order from the provided "Mock Midterm")*

1. [[k-Means Clustering]] problem on one dimensional dataset containing 5 points using $k=2$, Euclidian distance, and provided initial cluster assignments
	1. Trivial, took one iteration
2. Optimize given function with respect to $x$ using [[Gradient Descent]] and a given $\eta^{(0)}$ and $x^{(0)}$ by filling in table with $x^{(t)},f(x^{(t)}),\nabla_xf(x^{(t)})$ for $t=0,1,2$
	1. The given problem doesn't actually converge well because $\eta$ (the learning rate) is too high
	2. Part 2 of the question asks you how you can improve it, the answers are:
		1. Decreasing the step size (**Correct**)
		2. Running gradient descent for more iterations (**Incorrect**)
		3. Moving the initial value $x^{(0)}$ further from the origin (**Incorrect**)
		4. Negating the function and running Gradient *Ascent* (**Incorrect, ascent searches for a maximum**)
		5. None of the above (**Incorrect because 1. works**)
3. You are performing [[Polynomial Regression]] with least squares, as degree of polynomial increases, which of the following is commonly seen to go down at first but then go up?
	1. Validation Error is the correct answer
4. [[Gradient Descent]] computes all points [[Stochastic Gradient Descent]] only evaluates one point at a time
	1. The gradient computed in SGD is, in expectation, equal to the gradient computed in GD
5. In a [[Linear Regression]] model with only the bias, minimizing the sum of squared errors results in that parameter being (**not the median of $y_i$, incorrect**)
6. $\theta=$ the closed form solution to [[Linear Regression]] with $n=35$ and $m=5$ features, what are the dimensions of $X,y,\theta$? 
	1. $X=35\times6,y=35\times1,\theta=6\times1$
7. Run the [[Perceptron Learning Algorithm]] on a small dataset on pen and paper
8. You look at a [[Classification]] (classifier) by looking at train and test errors, test error is high, training error is close to zero
	1. **Called overfitting**
9. The "three doors, one is opened, do you switch?" question
	1. You always switch
10. What the fuck is a Gini Index? (from [[Classification Tree]])
	1. "Diversity" of a branch -- if the results from a training set has 300 positive examples and 100 negative examples reach terminal branch A, and you have 300 negative and 100 positive in branch B, then the Gini Index is $\frac 3 4 \cdot \frac 1 4 + \frac 1 4 \cdot \frac 3 4=\frac 3 8$ is the Gini Index
	2. Gini is a good measure of how "good" a tree is at reducing uncertainty
	3. Be able to compare *Gini Index* with *Misclassification Index*
11. Given 4 samples with 3 features of true/false data create a [[Classification Tree]] that predicts true/false $Y$ 

---
Student Choice Problems

1. Consider a binary [[Classification]] dataset draw a reasonable approximation of the [[Logistic Regression]] [[Probability]] estimate for $P(Y=1|x)$
	1. ![[log_reg_example.png]]
		1. *Note that the blue dots were provided*
2. Given a [[Two Random Variables]] table with a joint [[Probability Mass Function]], find the [[Probability]] of $P(X=1, Y=2)$ and the marginal [[Probability]] $P(Y=2)$
3. 