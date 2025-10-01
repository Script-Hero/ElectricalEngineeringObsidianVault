#Chapter5 

Type of [[Random Variable]] "typically used to model the number of occurrences of an [[Event]] in a fixed interval of time or space"
- [[Probability Mass Function]] given by $p_{X}(k)=\frac{\lambda ^ k}{k!}e^{-\lambda}$, $k=0,1,\dots$
	- ***Note*** that $k$ is the variable and $\lambda$ is the chance that it happens, you have to follow the unit of $\lambda$ 
		- For example, if the problem has you going through $n$ requests per second, and you want to find the [[Probability]] of $0$ requests after $2$ seconds, you would plug in $k=0$ (for the number of requests) and $\lambda=2n$ (for 2 seconds) 
*Examples*
- Calls received at a call center within an hour
- Visits to a website in a minute
- Number of radioactive particles that decay in a given time interval

### Relationship to [[Binomial Random Variable]]
- The *limit* of a [[Binomial Random Variable]] $\\lim_{ n \to \infty }p_{X_{n}}(k)=\frac{\lambda^k}{k!}e^{-\lambda}$ the Poisson PMF
