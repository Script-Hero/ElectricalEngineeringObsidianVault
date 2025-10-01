$$P(F|E)=\frac{P(E\cap F)}{P(E)}=\frac{P(E|F)\cdot P(F)}{P(E)}$$

## Example
Suppose that there is a rare child cancer that occurs in one out of one million kids. There is a test for this disease which is 99.9 percent effective, meaning that if you have cancer you test positive with 99.9% [[Probability]] and if you do not have it you test negative with 99.9% [[Probability]].  **What is the [[Probability]] that you actually have cancer given that you test positive for it?**
1. $P(\text{Cancer} | \text{Test pos.})$
2. $=\frac{P(\text{Cancer} | \text{Test pos.})\cdot P(\text{Cancer})}{P(\text{Test pos.} | \text{Cancer})\cdot P(\text{Cancer})+P(\text{Test pos.} | \text{No Cancer})\cdot P(\text{No Cancer})}$
3. $=\frac{0.999\cdot10^{-6}}{0.999\cdot10^{-6}+10^{-3}\cdot(1-10^{-6})}$
4. $\approx \frac{10^{-6}}{10^{-6}+10^{-3}}$
5. $=\frac{1}{1001}$

**Conclusion: pretty damn small because the cancer is a 1-in-a-million occurrence.**
