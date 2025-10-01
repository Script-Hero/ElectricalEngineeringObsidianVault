#Chapter5 

Type of [[Random Variable]] used to model the *number of independent trials needed to get the first success* in a sequence of [[Bernoulli Random Variable]] trials.

[[Probability Mass Function]] is $p_{X}(k)=(1-p)^{k-1}p$, $k=1,2,\dots$

Examples:
- Number of coin tosses until first heads
- Clicks on ad until the first customer purchases
- Number of items inspected before the first defective one is found

### Memoryless Property
Satisfies the *memoryless property* $P(X=k+j|X>k)=P(X=j)$
- Meaning that the [[Probability]] that the number of trials carried out before completion is $k+j$, given $k$ unsuccessful trials, is equal to the unconditioned [[Probability]] that the total number of trials is $j$
- "In english" this means that if you've been flipping a coin and waiting for heads (geometric trial) and you've already done $k$ flips, the [[Probability]] that you'll need $j$ more flips is the same as though you were starting fresh.
