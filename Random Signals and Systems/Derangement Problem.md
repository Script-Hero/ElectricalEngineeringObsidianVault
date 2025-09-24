#Chapter7 

Uses [[Linearity of Expectation]] to find the probability of [[Multiple Random Variables]], after being randomly arranged, appear (or do not appear) in their original positions.

#### Example Problem

$n$ people put their phone in a box, then each person picks one at random. How many got their original phone back?
1. Define $X_i$, the indicator variable, as $X_{i}=\begin{cases}1&\mbox{Person picked the right phone}\\ 0&\mbox{Otherwise}\end{cases}$
2. Since all phones start off with an equally likely chance to be picked at first, $P(\{X_{i}=1\})=\frac{1}{n}$
3. $X=\sum\limits_{i=1}^nX_{i}$
4. $E[X]=\sum\limits_{i=1}^nE[X_{i}]$
5. $E[X]=\sum\limits_{i=1}^n\frac{1}{n}=n \cdot\frac{1}{n}=1$
	1. $E[X_{i}]=1 \cdot\frac{1}{n}+0\cdot(1-\frac{1}{n})=\frac{1}{n}$
No matter the value of $n$, $E[X]$ is always 1.

