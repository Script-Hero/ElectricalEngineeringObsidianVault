## Joule's Law Definition
#### *Derivation*
$\Delta K = \frac{1}{2}mv^{2}=W_{net}$
$W_{E}=|-\Delta u| = q\Delta V$
$P = \frac{dW}{dt}=\frac{iVdt}{dt}=iV$
### Definition
$P=iV$ ; [[Power]] = [[Current]] times [[Voltage]]


## Voltage Drop
$\vec{E}=\rho \vec{j}$
$\Delta V = -\int \vec{E}d\vec{r}$
- Note that the [[Voltage]] drops *in the direction* of [[Current]] flow
- Electric [[Current]] flows from high [[Physics E&M/EXAM-1/Electric Potential|Electric Potential]] to low [[Physics E&M/EXAM-1/Electric Potential|Electric Potential]]

## Electromotive Force
- Batteries have some *internal resistance*
- $i=\frac{V}{R_{i}+R}$
- $V=V_{0}\frac{R}{R_{i}+R}$
	- Internal resistance + load resistance
- $P=V_{0}^2\frac{R}{(R_{i}+R)^{2}}$
- Maximum $P=\frac{V_{0}^2}{4R_{i}}$

## Resistor Circuit Simplification
- Different [[Voltage]] through each resistor but same [[Current]]
- **In series** $R_{eq}=R_{1}+R_{2}+R{3}+...$
- **In parallel** $\frac{1}{R_{eq}}=\frac{1}{R_{1}}+\frac{1}{R_2}+...$

## Kirchhoff's Rules
### Junction Rule
$\Sigma_{junction}i=0$ where $i$ is [[Current]]
### Loop Rule
$\Sigma_{loop}V=0$ where $V$ is [[Voltage]]
or $-\Delta V=0$
or $\oint \vec{E}\cdot d\vec{r}=0$

### Circuit Analysis
- Assign curents in each branch and charge on each [[Capacitors]]
- ***LABEL YOUR DIAGRAM!***
	- The way you label determines if your answer is positive or negative
	- *you can lose all points if you forget to label!* 
1. Use Kirchhoff's Junction Rule for each *independent* junction
2. Use Kirchhoff's Closed Loop Rule for each *independent* closed loop
3. Use these to set up a system of equations and solve it out
- Is easier to choose a bunch of small loops