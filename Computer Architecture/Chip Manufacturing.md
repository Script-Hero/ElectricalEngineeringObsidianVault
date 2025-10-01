[[Integrated Circuit]] manufacturing beings with silicon ([[Semiconductor]]):
1. Silicon crystal ingot (5-8" diameter, 8" long)
2. Sliced into wafers (0.1" thick)
3. Chopped into dies (or chips)

**Defect:** Microscopic flaw in a wafer
- Any single microscopic flaw can cause failure
- Chopping wafers into dies allow us to disregard only those dies containing the flaws, rather than the whole wafer

**Yield:** Percentage of good dies from the total number of dies on the wafer.
- Since each wafer costs the same fewer dies means higher cost
- Twice the yield means half the cost

## Equations
1. $$\text{Cost per Die} = \frac{\text{Cost per Wafer}}{\text{Dies per Wafer} \cdot \text{Die Yield}}$$
2. $$\text{Dies per Wafer}=\frac{\text{Wafer Area}}{\text{Die Area}}$$
3. $$\text{Die Yield}=(1+\frac{\text{Defects per Unit Area}\cdot\text{Die Area}}{\alpha})^{-\alpha}$$ or $$\text{Die Yield}=\frac 1 {(1+\frac{\text{Die Area}\cdot\text{Defects per Unit Area}}{\alpha})^\alpha}$$
	- Where $\alpha$ is the number of critical processing steps in the manufacturing process
		- In the example problems, it looks like we use $\alpha=2$
	- For simple MOS, $\alpha=2$, higher for bipolar, etc

