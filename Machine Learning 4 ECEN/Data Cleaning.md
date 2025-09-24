Real world datasets often have errors, ambiguity, incompleteness, inconsistency, and other quality issues
- 2 main stages: **error detection** and **repair**


## Missing Data
We can solve by:
- Removing entire feature from further analysis
- Removing rows (observation instances)
- Filling missing data with some value -- i.e. the previous reading, zero, the min, the max, the mean, the median

## Outliers
- A point that differs significantly from other observations
- Usually we remove outliers
	- Under the assumption that the outlier point is erroneous / does not represent the true data
	- If it's a natural part of the data you are studying, you should not remove it